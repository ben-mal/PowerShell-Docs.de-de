---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: 04d0b272995538e88fff2725eb8806c66d217460
ms.sourcegitcommit: 9a53e53e7a3ef9ac0a212c61005efff9e9902452
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "93219612"
---
# <span data-ttu-id="853c6-103">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="853c6-103">New-CimSession</span></span>

## <span data-ttu-id="853c6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="853c6-104">SYNOPSIS</span></span>

<span data-ttu-id="853c6-105">Erstellt eine CIM-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="853c6-105">Creates a CIM session.</span></span>

## <span data-ttu-id="853c6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="853c6-106">SYNTAX</span></span>

### <span data-ttu-id="853c6-107">"Kredentialparameterset" (Standard)</span><span class="sxs-lookup"><span data-stu-id="853c6-107">CredentialParameterSet (Default)</span></span>

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### <span data-ttu-id="853c6-108">Certifi-eprameterset</span><span class="sxs-lookup"><span data-stu-id="853c6-108">CertificatePrameterSet</span></span>

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## <span data-ttu-id="853c6-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="853c6-109">DESCRIPTION</span></span>

<span data-ttu-id="853c6-110">Das- `New-CimSession` Cmdlet erstellt eine CIM-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="853c6-110">The `New-CimSession` cmdlet creates a CIM session.</span></span> <span data-ttu-id="853c6-111">Eine CIM-Sitzung ist ein Client seitiges Objekt, das eine Verbindung mit einem lokalen Computer oder einem Remote Computer darstellt.</span><span class="sxs-lookup"><span data-stu-id="853c6-111">A CIM session is a client-side object representing a connection to a local computer or a remote computer.</span></span> <span data-ttu-id="853c6-112">Die CIM-Sitzung enthält Informationen über die Verbindung, z. b. **Computername** , das verwendete Protokoll oder verschiedene Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="853c6-112">The CIM session contains information about the connection, such as **ComputerName** , the protocol used, or various identifiers.</span></span>

<span data-ttu-id="853c6-113">Dieses Cmdlet gibt ein CIM-Sitzungs Objekt zurück, das von allen anderen CIM-Cmdlets verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="853c6-113">This cmdlet returns a CIM session object that can be used by all other CIM cmdlets.</span></span>

## <span data-ttu-id="853c6-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="853c6-114">EXAMPLES</span></span>

### <span data-ttu-id="853c6-115">Beispiel 1: Erstellen einer CIM-Sitzung mit Standardoptionen</span><span class="sxs-lookup"><span data-stu-id="853c6-115">Example 1: Create a CIM session with default options</span></span>

<span data-ttu-id="853c6-116">In diesem Beispiel wird eine lokale CIM-Sitzung mit Standardoptionen erstellt.</span><span class="sxs-lookup"><span data-stu-id="853c6-116">This example creates a local CIM session with default options.</span></span> <span data-ttu-id="853c6-117">Wenn **Computername** nicht angegeben ist, wird `New-CimSession` von eine DCOM-Sitzung auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="853c6-117">If **ComputerName** is not specified, `New-CimSession` creates a DCOM session to the local computer.</span></span>

```powershell
New-CimSession
```

### <span data-ttu-id="853c6-118">Beispiel 2: Erstellen einer CIM-Sitzung für einen bestimmten Computer</span><span class="sxs-lookup"><span data-stu-id="853c6-118">Example 2: Create a CIM session to a specific computer</span></span>

<span data-ttu-id="853c6-119">Dieses Beispiel erstellt eine CIM-Sitzung auf dem Computer, der von **Computername** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="853c6-119">This example creates a CIM session to the computer specified by **ComputerName**.</span></span>
<span data-ttu-id="853c6-120">Standardmäßig `New-CimSession` wird von eine WSMAN-Sitzung erstellt, wenn **Computername** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="853c6-120">By default, `New-CimSession` creates a WSMan session when **ComputerName** is specified.</span></span>

```powershell
New-CimSession -ComputerName Server01
```

### <span data-ttu-id="853c6-121">Beispiel 3: Erstellen einer CIM-Sitzung auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="853c6-121">Example 3: Create a CIM session to multiple computers</span></span>

<span data-ttu-id="853c6-122">Dieses Beispiel erstellt eine CIM-Sitzung für jeden Computer, der von **Computername** angegeben wird, in der durch Trennzeichen getrennten Liste.</span><span class="sxs-lookup"><span data-stu-id="853c6-122">This example creates a CIM session to each of the computers specified by **ComputerName** , in the comma separated list.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### <span data-ttu-id="853c6-123">Beispiel 4: Erstellen einer CIM-Sitzung mit einem anzeigen Amen</span><span class="sxs-lookup"><span data-stu-id="853c6-123">Example 4: Create a CIM session with a friendly name</span></span>

<span data-ttu-id="853c6-124">In diesem Beispiel wird eine Remote-CIM-Sitzung für jeden Computer, der in **Computername** angegeben ist, in der durch Trennzeichen getrennten Liste erstellt und den neuen Sitzungen ein Anzeige Name zugewiesen, indem der **Name** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="853c6-124">This example creates a remote CIM session to each of the computers specified by **ComputerName** , in the comma separated list, and assigns a friendly name to the new sessions, by specifying **Name**.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

<span data-ttu-id="853c6-125">Sie können den anzeigen Amen einer CIM-Sitzung verwenden, um in anderen CIM-Cmdlets auf die Sitzung zu verweisen, z. b. " [Get-cimsession](Get-CimSession.md)".</span><span class="sxs-lookup"><span data-stu-id="853c6-125">You can use the friendly name of a CIM session to refer to the session in other CIM cmdlets, for example, [Get-CimSession](Get-CimSession.md).</span></span>

### <span data-ttu-id="853c6-126">Beispiel 5: Erstellen einer CIM-Sitzung auf einem Computer mithilfe eines PSCredential-Objekts</span><span class="sxs-lookup"><span data-stu-id="853c6-126">Example 5: Create a CIM session to a computer using a PSCredential object</span></span>

<span data-ttu-id="853c6-127">In diesem Beispiel wird eine CIM-Sitzung auf dem Computer **namens** erstellt, der das von " **Credential** " angegebene **PSCredential** -Objekt verwendet, und der durch die **Authentifizierung** angegebene Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="853c6-127">This example creates a CIM session to the computer specified by **ComputerName** , using the **PSCredential** object specified by **Credential** , and the authentication type specified by **Authentication**.</span></span>

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

<span data-ttu-id="853c6-128">Sie können ein **PSCredential** -Objekt mit dem [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="853c6-128">You can create a **PSCredential** object using the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

### <span data-ttu-id="853c6-129">Beispiel 6: Erstellen einer CIM-Sitzung auf einem Computer mit einem bestimmten Port</span><span class="sxs-lookup"><span data-stu-id="853c6-129">Example 6: Create a CIM session to a computer using a specific port</span></span>

<span data-ttu-id="853c6-130">Dieses Beispiel erstellt eine CIM-Sitzung auf dem Computer, der von **Computername** unter Verwendung des durch den **Port** angegebenen TCP-Ports angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="853c6-130">This example creates a CIM session to the computer specified by **ComputerName** using the TCP port specified by **Port**.</span></span>

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### <span data-ttu-id="853c6-131">Beispiel 7: Erstellen einer CIM-Sitzung mithilfe von DCOM</span><span class="sxs-lookup"><span data-stu-id="853c6-131">Example 7: Create a CIM session using DCOM</span></span>

<span data-ttu-id="853c6-132">Dieses Beispiel erstellt eine CIM-Sitzung unter Verwendung des verteilten com-Protokolls (DCOM) anstelle von WSMAN.</span><span class="sxs-lookup"><span data-stu-id="853c6-132">This example creates a CIM session using the Distributed COM (DCOM) protocol instead of WSMan.</span></span>

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## <span data-ttu-id="853c6-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="853c6-133">PARAMETERS</span></span>

### <span data-ttu-id="853c6-134">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="853c6-134">-Authentication</span></span>

<span data-ttu-id="853c6-135">Gibt den für die Anmelde Informationen des Benutzers verwendeten Authentifizierungstyp an.</span><span class="sxs-lookup"><span data-stu-id="853c6-135">Specifies the authentication type used for the user's credentials.</span></span> <span data-ttu-id="853c6-136">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="853c6-136">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="853c6-137">Standard</span><span class="sxs-lookup"><span data-stu-id="853c6-137">Default</span></span>
- <span data-ttu-id="853c6-138">Digest</span><span class="sxs-lookup"><span data-stu-id="853c6-138">Digest</span></span>
- <span data-ttu-id="853c6-139">Aushandeln</span><span class="sxs-lookup"><span data-stu-id="853c6-139">Negotiate</span></span>
- <span data-ttu-id="853c6-140">Basic</span><span class="sxs-lookup"><span data-stu-id="853c6-140">Basic</span></span>
- <span data-ttu-id="853c6-141">Kerberos</span><span class="sxs-lookup"><span data-stu-id="853c6-141">Kerberos</span></span>
- <span data-ttu-id="853c6-142">Quot ntlmdomain</span><span class="sxs-lookup"><span data-stu-id="853c6-142">NtlmDomain</span></span>
- <span data-ttu-id="853c6-143">CredSsp</span><span class="sxs-lookup"><span data-stu-id="853c6-143">CredSsp</span></span>

<span data-ttu-id="853c6-144">Der Authentifizierungstyp **ntlmdomain** kann nicht für die Verbindung mit dem lokalen Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="853c6-144">You cannot use the **NtlmDomain** authentication type for connection to the local computer.</span></span> <span data-ttu-id="853c6-145">Die **kredssp** -Authentifizierung ist nur in Windows Vista, Windows Server 2008 und neueren Versionen von Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="853c6-145">**CredSSP** authentication is available only in Windows Vista, Windows Server 2008, and later versions of Windows.</span></span>

> [!CAUTION]
> <span data-ttu-id="853c6-146">Die Authentifizierung des Sicherheits Diensts für Anmelde Informationen (Security Service Provider, kredssp) ist für Befehle konzipiert, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. auf eine Remote Netzwerkfreigabe.</span><span class="sxs-lookup"><span data-stu-id="853c6-146">Credential Security Service Provider (CredSSP) authentication is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="853c6-147">Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="853c6-147">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="853c6-148">Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="853c6-148">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: CredentialParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="853c6-149">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="853c6-149">-CertificateThumbprint</span></span>

<span data-ttu-id="853c6-150">Gibt das digitale Zertifikat für öffentliche Schlüssel (X. 509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="853c6-150">Specifies the digital public key certificate (X.509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="853c6-151">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="853c6-151">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="853c6-152">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="853c6-152">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="853c6-153">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="853c6-153">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="853c6-154">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie das- [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) Cmdlet oder das-Cmdlet im PowerShell-Zertifikat Anbieter.</span><span class="sxs-lookup"><span data-stu-id="853c6-154">To get a certificate thumbprint, use the [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) or [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) cmdlets in the PowerShell Certificate Provider.</span></span>

<span data-ttu-id="853c6-155">Weitere Informationen finden Sie unter [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="853c6-155">For more information, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

```yaml
Type: System.String
Parameter Sets: CertificatePrameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="853c6-156">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="853c6-156">-ComputerName</span></span>

<span data-ttu-id="853c6-157">Gibt den Namen des Computers an, auf dem die CIM-Sitzung erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="853c6-157">Specifies the name of the computer to which to create the CIM session.</span></span> <span data-ttu-id="853c6-158">Geben Sie entweder einen einzelnen Computernamen oder mehrere Computernamen durch Kommas getrennt an.</span><span class="sxs-lookup"><span data-stu-id="853c6-158">Specify either a single computer name, or multiple computer names separated by a comma.</span></span>

<span data-ttu-id="853c6-159">Wenn **Computername** nicht angegeben ist, wird eine CIM-Sitzung zum lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="853c6-159">If **ComputerName** is not specified, a CIM session to the local computer is created.</span></span> <span data-ttu-id="853c6-160">Sie können den Wert für Computername in einem der folgenden Formate angeben:</span><span class="sxs-lookup"><span data-stu-id="853c6-160">You can specify the value for computer name in one of the following formats:</span></span>

- <span data-ttu-id="853c6-161">Mindestens ein NetBIOS-Name</span><span class="sxs-lookup"><span data-stu-id="853c6-161">One or more NetBIOS names</span></span>
- <span data-ttu-id="853c6-162">Mindestens eine IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="853c6-162">One or more IP addresses</span></span>
- <span data-ttu-id="853c6-163">Mindestens ein voll qualifizierter Domänen Name.</span><span class="sxs-lookup"><span data-stu-id="853c6-163">One or more fully qualified domain names.</span></span>

<span data-ttu-id="853c6-164">Wenn sich der Computer in einer anderen Domäne als der Benutzer befindet, müssen Sie den voll qualifizierten Domänen Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="853c6-164">If the computer is in a different domain than the user, you must specify the fully qualified domain name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="853c6-165">-Credential</span><span class="sxs-lookup"><span data-stu-id="853c6-165">-Credential</span></span>

<span data-ttu-id="853c6-166">Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt.</span><span class="sxs-lookup"><span data-stu-id="853c6-166">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="853c6-167">Wenn **Credential** nicht angegeben ist, wird das aktuelle Benutzerkonto verwendet.</span><span class="sxs-lookup"><span data-stu-id="853c6-167">If **Credential** is not specified, the current user account is used.</span></span>

<span data-ttu-id="853c6-168">Geben Sie den Wert für die Anmelde Informationen in einem der folgenden **Formate an:**</span><span class="sxs-lookup"><span data-stu-id="853c6-168">Specify the value for **Credential** using one of the following formats:</span></span>

- <span data-ttu-id="853c6-169">Ein Benutzername: "USER01"</span><span class="sxs-lookup"><span data-stu-id="853c6-169">A user name: "User01"</span></span>
- <span data-ttu-id="853c6-170">Ein Domänen Name und ein Benutzername: "Domain01\User01"</span><span class="sxs-lookup"><span data-stu-id="853c6-170">A domain name and a user name: "Domain01\User01"</span></span>
- <span data-ttu-id="853c6-171">Ein Benutzer Prinzipal Name: " User@Domain.com "</span><span class="sxs-lookup"><span data-stu-id="853c6-171">A user principal name: "User@Domain.com"</span></span>
- <span data-ttu-id="853c6-172">Ein PSCredential-Objekt, z. b. ein vom Cmdlet zurück gegebenes Objekt [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) .</span><span class="sxs-lookup"><span data-stu-id="853c6-172">A PSCredential object, such as one returned by the [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) cmdlet.</span></span>

<span data-ttu-id="853c6-173">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="853c6-173">When you type a user name, you are prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="853c6-174">-Name</span><span class="sxs-lookup"><span data-stu-id="853c6-174">-Name</span></span>

<span data-ttu-id="853c6-175">Gibt einen anzeigen Amen für die CIM-Sitzung an.</span><span class="sxs-lookup"><span data-stu-id="853c6-175">Specifies a friendly name for the CIM session.</span></span>

<span data-ttu-id="853c6-176">Sie können den Namen verwenden, um auf die CIM-Sitzung zu verweisen, wenn Sie andere Cmdlets verwenden, z [`Get-CimSession`](Get-CimSession.md) . b. das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="853c6-176">You can use the name to refer to the CIM session when using other cmdlets, such as the [`Get-CimSession`](Get-CimSession.md) cmdlet.</span></span>
<span data-ttu-id="853c6-177">Der Name muss für den Computer oder die aktuelle Sitzung nicht eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="853c6-177">The name is not required to be unique to the computer or the current session.</span></span>

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

### <span data-ttu-id="853c6-178">-Operationtimeoutsec</span><span class="sxs-lookup"><span data-stu-id="853c6-178">-OperationTimeoutSec</span></span>

<span data-ttu-id="853c6-179">Die Dauer, für die das Cmdlet auf eine Antwort vom Server wartet.</span><span class="sxs-lookup"><span data-stu-id="853c6-179">Duration for which the cmdlet waits for a response from the server.</span></span>

<span data-ttu-id="853c6-180">Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="853c6-180">By default, the value of this parameter is 0, which means that the cmdlet uses the default timeout value for the server.</span></span>

<span data-ttu-id="853c6-181">Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="853c6-181">If the **OperationTimeoutSec** parameter is set to a value less than the robust connection retry timeout of 3 minutes, network failures that last more than the value of the **OperationTimeoutSec** parameter are not recoverable, because the operation on the server times out before the client can reconnect.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="853c6-182">-Port</span><span class="sxs-lookup"><span data-stu-id="853c6-182">-Port</span></span>

<span data-ttu-id="853c6-183">Gibt den Netzwerkport an dem für diese Verbindung verwendeten Remotecomputer an.</span><span class="sxs-lookup"><span data-stu-id="853c6-183">Specifies the network port on the remote computer that is used for this connection.</span></span>
<span data-ttu-id="853c6-184">Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.</span><span class="sxs-lookup"><span data-stu-id="853c6-184">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span>
<span data-ttu-id="853c6-185">Die Standardports sind 5985 (der WinRM-Port für HTTP) und 5986 (der WinRM-Port für HTTPS).</span><span class="sxs-lookup"><span data-stu-id="853c6-185">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span>

<span data-ttu-id="853c6-186">Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="853c6-186">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>
<span data-ttu-id="853c6-187">Verwenden Sie die folgenden Befehle, um den Listener zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="853c6-187">Use the following commands to configure the listener:</span></span>

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

<span data-ttu-id="853c6-188">Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="853c6-188">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="853c6-189">Die Porteinstellung im Befehl gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="853c6-189">The port setting in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="853c6-190">Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="853c6-190">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="853c6-191">-Sessionoption</span><span class="sxs-lookup"><span data-stu-id="853c6-191">-SessionOption</span></span>

<span data-ttu-id="853c6-192">Legt Erweiterte Optionen für die neue CIM-Sitzung fest.</span><span class="sxs-lookup"><span data-stu-id="853c6-192">Sets advanced options for the new CIM session.</span></span> <span data-ttu-id="853c6-193">Geben Sie den Namen eines **cimsessionoption** -Objekts ein, das mit dem [`New-CimSessionOption`](New-CimSessionOption.md) Cmdlet erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="853c6-193">Enter the name of a **CimSessionOption** object created using the [`New-CimSessionOption`](New-CimSessionOption.md) cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.Options.CimSessionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="853c6-194">-Skiptestconnection</span><span class="sxs-lookup"><span data-stu-id="853c6-194">-SkipTestConnection</span></span>

<span data-ttu-id="853c6-195">Standardmäßig stellt das `New-CimSession` Cmdlet aus zwei Gründen eine Verbindung mit einem Remote WS-Management-Endpunkt her: um zu überprüfen, ob der Remote Server die mit dem **Port** -Parameter angegebene Portnummer überwacht und die angegebenen Konto Anmelde Informationen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="853c6-195">By default, the `New-CimSession` cmdlet establishes a connection with a remote WS-Management endpoint for two reasons: to verify that the remote server is listening on the port number that is specified using the **Port** parameter, and to verify the specified account credentials.</span></span> <span data-ttu-id="853c6-196">Die Überprüfung erfolgt mit einem Standard WS-Identity Vorgang.</span><span class="sxs-lookup"><span data-stu-id="853c6-196">The verification is accomplished using a standard WS-Identity operation.</span></span> <span data-ttu-id="853c6-197">Sie können den Switch-Parameter **skiptestconnection** hinzufügen, wenn der Remote WS-Management-Endpunkt WS-Identifizierungs Server nicht verwenden kann, oder um die Daten Übertragungszeit zu verringern.</span><span class="sxs-lookup"><span data-stu-id="853c6-197">You can add the **SkipTestConnection** switch parameter if the remote WS-Management endpoint cannot use WS-Identify, or to reduce some data transmission time.</span></span>

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

### <span data-ttu-id="853c6-198">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="853c6-198">CommonParameters</span></span>

<span data-ttu-id="853c6-199">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="853c6-199">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="853c6-200">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="853c6-200">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="853c6-201">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="853c6-201">INPUTS</span></span>

### <span data-ttu-id="853c6-202">Keine</span><span class="sxs-lookup"><span data-stu-id="853c6-202">None</span></span>

<span data-ttu-id="853c6-203">Dieses Cmdlet akzeptiert keine Eingaben.</span><span class="sxs-lookup"><span data-stu-id="853c6-203">This cmdlet accepts no inputs.</span></span>

## <span data-ttu-id="853c6-204">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="853c6-204">OUTPUTS</span></span>

### <span data-ttu-id="853c6-205">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="853c6-205">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="853c6-206">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="853c6-206">NOTES</span></span>

## <span data-ttu-id="853c6-207">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="853c6-207">RELATED LINKS</span></span>

[<span data-ttu-id="853c6-208">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="853c6-208">Get-ChildItem</span></span>](../Microsoft.Powershell.Management/Get-ChildItem.md)

[<span data-ttu-id="853c6-209">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="853c6-209">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="853c6-210">Get-Item</span><span class="sxs-lookup"><span data-stu-id="853c6-210">Get-Item</span></span>](../Microsoft.Powershell.Management/Get-Item.md)

[<span data-ttu-id="853c6-211">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="853c6-211">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="853c6-212">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="853c6-212">Remove-CimSession</span></span>](Remove-CimSession.md)

[<span data-ttu-id="853c6-213">New-CimSessionOption</span><span class="sxs-lookup"><span data-stu-id="853c6-213">New-CimSessionOption</span></span>](New-CimSessionOption.md)

[<span data-ttu-id="853c6-214">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="853c6-214">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)
