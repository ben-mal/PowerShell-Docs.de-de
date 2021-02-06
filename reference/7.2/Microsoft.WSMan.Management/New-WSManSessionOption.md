---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: e7d7f132eb82dc1a709a88cbdef525aa83d867e4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599437"
---
# <span data-ttu-id="44df4-102">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="44df4-102">New-WSManSessionOption</span></span>

## <span data-ttu-id="44df4-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="44df4-103">SYNOPSIS</span></span>
<span data-ttu-id="44df4-104">Erstellt eine Sitzungs Option-Hash Tabelle, die als Eingabeparameter für WS-Management Cmdlets verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="44df4-104">Creates session option hash table to use as input parameters for WS-Management cmdlets.</span></span>

## <span data-ttu-id="44df4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="44df4-105">SYNTAX</span></span>

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## <span data-ttu-id="44df4-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="44df4-106">DESCRIPTION</span></span>
<span data-ttu-id="44df4-107">Das **New-wsmansessionoption-** Cmdlet erstellt eine Hash Tabelle für WSMAN-Sitzungs Optionen, die an WSMAN-Cmdlets übergeben werden kann:</span><span class="sxs-lookup"><span data-stu-id="44df4-107">The **New-WSManSessionOption** cmdlet creates a WSMan Session option hash table which can be passed to WSMan cmdlets:</span></span>

- <span data-ttu-id="44df4-108">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="44df4-108">Get-WSManInstance</span></span>
- <span data-ttu-id="44df4-109">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="44df4-109">Set-WSManInstance</span></span>
- <span data-ttu-id="44df4-110">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="44df4-110">Invoke-WSManAction</span></span>
- <span data-ttu-id="44df4-111">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="44df4-111">Connect-WSMan</span></span>

## <span data-ttu-id="44df4-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="44df4-112">EXAMPLES</span></span>

### <span data-ttu-id="44df4-113">Beispiel 1: Erstellen einer Verbindung, die Verbindungsoptionen verwendet</span><span class="sxs-lookup"><span data-stu-id="44df4-113">Example 1: Create a connection that uses connection options</span></span>

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

<span data-ttu-id="44df4-114">In diesem Beispiel wird mithilfe der von **New-wsmansessionoption** definierten Verbindungsoptionen eine Verbindung mit dem Remote Computer Server01 erstellt.</span><span class="sxs-lookup"><span data-stu-id="44df4-114">This example creates a connection to the remote server01 computer by using the connection options that are defined by **New-WSManSessionOption**.</span></span>

<span data-ttu-id="44df4-115">Der erste Befehl verwendet " **New-wsmansessionoption** ", um einen Satz von Optionen für Verbindungseinstellungen in der $a Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="44df4-115">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="44df4-116">In diesem Fall wird durch die Sitzungsoptionen ein Verbindungstimeout von 30 Sekunden (30.000 Millisekunden) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="44df4-116">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="44df4-117">Der zweite Befehl verwendet den *sessionoption* -Parameter, um die Anmelde Informationen, die in der $a Variablen gespeichert sind, an **Connect-WSMAN** zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="44df4-117">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan**.</span></span>
<span data-ttu-id="44df4-118">Anschließend stellt **Connect-WSMAN** mithilfe der angegebenen Sitzungs Optionen eine Verbindung mit dem Remote Computer Server01 her.</span><span class="sxs-lookup"><span data-stu-id="44df4-118">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

<span data-ttu-id="44df4-119">**Connect-WSMAN** wird in der Regel im Kontext des WSMAN-Anbieters verwendet, um eine Verbindung mit einem Remote Computer herzustellen, in diesem Fall dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="44df4-119">**Connect-WSMan** is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="44df4-120">Sie können das Cmdlet jedoch verwenden, um Verbindungen mit Remotecomputern herzustellen, bevor Sie zum WSMan-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="44df4-120">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="44df4-121">Diese Verbindungen werden in der **Computername** -Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="44df4-121">Those connections appear in the **ComputerName** list.</span></span>

## <span data-ttu-id="44df4-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="44df4-122">PARAMETERS</span></span>

### <span data-ttu-id="44df4-123">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="44df4-123">-NoEncryption</span></span>
<span data-ttu-id="44df4-124">Gibt an, dass für die Verbindung keine Verschlüsselung für Remote Vorgänge über HTTP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="44df4-124">Indicates that the connection does not use encryption for remote operations over HTTP.</span></span>

<span data-ttu-id="44df4-125">Der unverschlüsselte Datenverkehr ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="44df4-125">By default, unencrypted traffic is not enabled.</span></span>
<span data-ttu-id="44df4-126">Er muss in der lokalen Konfiguration aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="44df4-126">It must be enabled in the local configuration.</span></span>

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

### <span data-ttu-id="44df4-127">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="44df4-127">-OperationTimeout</span></span>
<span data-ttu-id="44df4-128">Gibt das Timeout (in Millisekunden) für den WS-Management Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="44df4-128">Specifies the time-out, in milliseconds, for the WS-Management operation.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44df4-129">-Proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="44df4-129">-ProxyAccessType</span></span>
<span data-ttu-id="44df4-130">Gibt den Mechanismus an, mit dem der Proxyserver gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="44df4-130">Specifies the mechanism by which the proxy server is located.</span></span>
<span data-ttu-id="44df4-131">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="44df4-131">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="44df4-132">ProxyIEConfig.</span><span class="sxs-lookup"><span data-stu-id="44df4-132">ProxyIEConfig.</span></span>
<span data-ttu-id="44df4-133">Verwenden Sie die Internet Explorer-Proxykonfiguration für den aktuellen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="44df4-133">Use the Internet Explorer proxy configuration for the current user.</span></span>
- <span data-ttu-id="44df4-134">ProxyWinHttpConfig.</span><span class="sxs-lookup"><span data-stu-id="44df4-134">ProxyWinHttpConfig.</span></span>
<span data-ttu-id="44df4-135">Der WSMAN-Client verwendet die Proxy Einstellungen, die für WinHTTP konfiguriert wurden, mithilfe des ProxyCfg.exe Hilfsprogramms.</span><span class="sxs-lookup"><span data-stu-id="44df4-135">The WSMan client uses the proxy settings configured for WinHTTP, using the ProxyCfg.exe utility.</span></span>
- <span data-ttu-id="44df4-136">ProxyAutoDetect.</span><span class="sxs-lookup"><span data-stu-id="44df4-136">ProxyAutoDetect.</span></span>
<span data-ttu-id="44df4-137">Erzwingen Sie die automatische Erkennung eines Proxy Servers.</span><span class="sxs-lookup"><span data-stu-id="44df4-137">Force auto-detection of a proxy server.</span></span>
- <span data-ttu-id="44df4-138">Proxynoproxyserver.</span><span class="sxs-lookup"><span data-stu-id="44df4-138">ProxyNoProxyServer.</span></span>
<span data-ttu-id="44df4-139">Verwenden Sie keinen Proxy Server.</span><span class="sxs-lookup"><span data-stu-id="44df4-139">Do not use a proxy server.</span></span>
<span data-ttu-id="44df4-140">Alle Hostnamen werden lokal aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="44df4-140">Resolve all host names locally.</span></span>

<span data-ttu-id="44df4-141">Der Standardwert ist proxyieconfig.</span><span class="sxs-lookup"><span data-stu-id="44df4-141">The default value is ProxyIEConfig.</span></span>

```yaml
Type: Microsoft.WSMan.Management.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: ProxyIEConfig, ProxyWinHttpConfig, ProxyAutoDetect, ProxyNoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44df4-142">-Proxy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="44df4-142">-ProxyAuthentication</span></span>
<span data-ttu-id="44df4-143">Gibt die Authentifizierungsmethode an, die auf dem Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="44df4-143">Specifies the authentication method to use at the proxy.</span></span>
<span data-ttu-id="44df4-144">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="44df4-144">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="44df4-145">Standard.</span><span class="sxs-lookup"><span data-stu-id="44df4-145">Basic.</span></span>
<span data-ttu-id="44df4-146">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="44df4-146">Basic is a scheme in which the user name and password are sent in clear-text to the server or proxy.</span></span>
- <span data-ttu-id="44df4-147">Digest.</span><span class="sxs-lookup"><span data-stu-id="44df4-147">Digest.</span></span>
<span data-ttu-id="44df4-148">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="44df4-148">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="44df4-149">Negotiate</span><span class="sxs-lookup"><span data-stu-id="44df4-149">Negotiate.</span></span>
<span data-ttu-id="44df4-150">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="44df4-150">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine which scheme to use for authentication.</span></span>
<span data-ttu-id="44df4-151">Beispiele sind das Kerberos-Protokoll und NTLM.</span><span class="sxs-lookup"><span data-stu-id="44df4-151">Examples are the Kerberos protocol and NTLM.</span></span>

<span data-ttu-id="44df4-152">Der Standardwert ist "aushandeln".</span><span class="sxs-lookup"><span data-stu-id="44df4-152">The default value is Negotiate.</span></span>

```yaml
Type: Microsoft.WSMan.Management.ProxyAuthentication
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic, Digest

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44df4-153">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="44df4-153">-ProxyCredential</span></span>
<span data-ttu-id="44df4-154">Gibt ein Benutzerkonto an, das über die Berechtigung verfügt, Zugriff über einen zwischenweb Proxy zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="44df4-154">Specifies a user account that has permission to gain access through an intermediate Web proxy.</span></span>

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

### <span data-ttu-id="44df4-155">-Skipcacheck</span><span class="sxs-lookup"><span data-stu-id="44df4-155">-SkipCACheck</span></span>
<span data-ttu-id="44df4-156">Gibt an, dass der Client beim Herstellen einer Verbindung über HTTPS nicht überprüft, ob das Serverzertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certification Authority, ca) signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="44df4-156">Specifies that, when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>
<span data-ttu-id="44df4-157">Verwenden Sie diese Option nur, wenn der Remote Computer von einer anderen Methode als vertrauenswürdig eingestuft wird, z. b. wenn der Remote Computer Teil eines physisch sicheren und isolierten Netzwerks ist oder der Remote Computer in der WS-Management Konfiguration als vertrauenswürdiger Host aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="44df4-157">Use this option only when the remote computer is trusted by another method, for example, if the remote computer is part of a network that is physically secure and isolated or the remote computer is listed as a trusted host in the WS-Management configuration.</span></span>

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

### <span data-ttu-id="44df4-158">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="44df4-158">-SkipCNCheck</span></span>
<span data-ttu-id="44df4-159">Gibt an, dass der allgemeine Name des Zertifikats (Common Name, CN) des Servers nicht mit dem Hostnamen des Servers identisch sein muss.</span><span class="sxs-lookup"><span data-stu-id="44df4-159">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="44df4-160">Diese Option wird nur bei Remotevorgängen über HTTPS eingesetzt</span><span class="sxs-lookup"><span data-stu-id="44df4-160">This is used only in remote operations using HTTPS.</span></span>
<span data-ttu-id="44df4-161">und sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44df4-161">This option should only be used for trusted computers.</span></span>

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

### <span data-ttu-id="44df4-162">-Skiprevocationcheck</span><span class="sxs-lookup"><span data-stu-id="44df4-162">-SkipRevocationCheck</span></span>
<span data-ttu-id="44df4-163">Gibt an, dass die Verbindung den Sperr Status für das Serverzertifikat nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="44df4-163">Indicates that the connection does not validate the revocation status on the server certificate.</span></span>

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

### <span data-ttu-id="44df4-164">-Spnport</span><span class="sxs-lookup"><span data-stu-id="44df4-164">-SPNPort</span></span>
<span data-ttu-id="44df4-165">Gibt eine Portnummer an, die an den Verbindungs Dienst Prinzipal Namen (SPN) des Remote Servers angehängt werden soll.</span><span class="sxs-lookup"><span data-stu-id="44df4-165">Specifies a port number to append to the connection Service Principal Name (SPN) of the remote server.</span></span>
<span data-ttu-id="44df4-166">Ein SPN wird verwendet, wenn der Authentifizierungsmechanismus „Kerberos“ oder „Negotiate“ lautet.</span><span class="sxs-lookup"><span data-stu-id="44df4-166">An SPN is used when the authentication mechanism is Kerberos or Negotiate.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="44df4-167">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="44df4-167">-UseUTF16</span></span>
<span data-ttu-id="44df4-168">Gibt an, dass die Verbindung die Anforderung im UTF16-Format anstatt im UTF8-Format codiert.</span><span class="sxs-lookup"><span data-stu-id="44df4-168">Indicates that the connection encodes the request in UTF16 format instead of UTF8 format.</span></span>
<span data-ttu-id="44df4-169">Standardmäßig wird die UTF8-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="44df4-169">The default is UTF8 encoding.</span></span>

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

### <span data-ttu-id="44df4-170">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="44df4-170">CommonParameters</span></span>
<span data-ttu-id="44df4-171">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="44df4-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="44df4-172">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="44df4-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="44df4-173">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="44df4-173">INPUTS</span></span>

## <span data-ttu-id="44df4-174">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="44df4-174">OUTPUTS</span></span>

### <span data-ttu-id="44df4-175">SessionOption</span><span class="sxs-lookup"><span data-stu-id="44df4-175">SessionOption</span></span>

## <span data-ttu-id="44df4-176">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="44df4-176">NOTES</span></span>

## <span data-ttu-id="44df4-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="44df4-177">RELATED LINKS</span></span>

[<span data-ttu-id="44df4-178">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="44df4-178">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="44df4-179">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="44df4-179">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="44df4-180">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="44df4-180">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="44df4-181">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="44df4-181">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="44df4-182">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="44df4-182">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="44df4-183">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="44df4-183">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="44df4-184">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="44df4-184">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="44df4-185">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="44df4-185">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="44df4-186">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="44df4-186">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="44df4-187">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="44df4-187">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="44df4-188">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="44df4-188">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="44df4-189">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="44df4-189">Test-WSMan</span></span>](Test-WSMan.md)

