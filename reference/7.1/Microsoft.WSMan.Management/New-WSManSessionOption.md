---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmansessionoption?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManSessionOption
ms.openlocfilehash: c0730daaed26fac1e8e8023532f201233fd90013
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215791"
---
# <span data-ttu-id="bc3f2-103">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="bc3f2-103">New-WSManSessionOption</span></span>

## <span data-ttu-id="bc3f2-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bc3f2-104">SYNOPSIS</span></span>
<span data-ttu-id="bc3f2-105">Erstellt eine Sitzungs Option-Hash Tabelle, die als Eingabeparameter für WS-Management Cmdlets verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-105">Creates session option hash table to use as input parameters for WS-Management cmdlets.</span></span>

## <span data-ttu-id="bc3f2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bc3f2-106">SYNTAX</span></span>

```
New-WSManSessionOption [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <ProxyAuthentication>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-SPNPort <Int32>]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [<CommonParameters>]
```

## <span data-ttu-id="bc3f2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bc3f2-107">DESCRIPTION</span></span>
<span data-ttu-id="bc3f2-108">Das **New-wsmansessionoption-** Cmdlet erstellt eine Hash Tabelle für WSMAN-Sitzungs Optionen, die an WSMAN-Cmdlets übergeben werden kann:</span><span class="sxs-lookup"><span data-stu-id="bc3f2-108">The **New-WSManSessionOption** cmdlet creates a WSMan Session option hash table which can be passed to WSMan cmdlets:</span></span>

- <span data-ttu-id="bc3f2-109">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc3f2-109">Get-WSManInstance</span></span>
- <span data-ttu-id="bc3f2-110">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc3f2-110">Set-WSManInstance</span></span>
- <span data-ttu-id="bc3f2-111">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="bc3f2-111">Invoke-WSManAction</span></span>
- <span data-ttu-id="bc3f2-112">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="bc3f2-112">Connect-WSMan</span></span>

## <span data-ttu-id="bc3f2-113">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bc3f2-113">EXAMPLES</span></span>

### <span data-ttu-id="bc3f2-114">Beispiel 1: Erstellen einer Verbindung, die Verbindungsoptionen verwendet</span><span class="sxs-lookup"><span data-stu-id="bc3f2-114">Example 1: Create a connection that uses connection options</span></span>

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

<span data-ttu-id="bc3f2-115">In diesem Beispiel wird mithilfe der von **New-wsmansessionoption** definierten Verbindungsoptionen eine Verbindung mit dem Remote Computer Server01 erstellt.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-115">This example creates a connection to the remote server01 computer by using the connection options that are defined by **New-WSManSessionOption** .</span></span>

<span data-ttu-id="bc3f2-116">Der erste Befehl verwendet " **New-wsmansessionoption** ", um einen Satz von Optionen für Verbindungseinstellungen in der $a Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-116">The first command uses **New-WSManSessionOption** to store a set of connection setting options in the $a variable.</span></span>
<span data-ttu-id="bc3f2-117">In diesem Fall wird durch die Sitzungsoptionen ein Verbindungstimeout von 30 Sekunden (30.000 Millisekunden) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-117">In this case, the session options set a connection time out of 30 seconds (30,000 milliseconds).</span></span>

<span data-ttu-id="bc3f2-118">Der zweite Befehl verwendet den *sessionoption* -Parameter, um die Anmelde Informationen, die in der $a Variablen gespeichert sind, an **Connect-WSMAN** zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-118">The second command uses the *SessionOption* parameter to pass the credentials that are stored in the $a variable to **Connect-WSMan** .</span></span>
<span data-ttu-id="bc3f2-119">Anschließend stellt **Connect-WSMAN** mithilfe der angegebenen Sitzungs Optionen eine Verbindung mit dem Remote Computer Server01 her.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-119">Then, **Connect-WSMan** connects to the remote server01 computer by using the specified session options.</span></span>

<span data-ttu-id="bc3f2-120">**Connect-WSMAN** wird in der Regel im Kontext des WSMAN-Anbieters verwendet, um eine Verbindung mit einem Remote Computer herzustellen, in diesem Fall dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-120">**Connect-WSMan** is generally used in the context of the WSMan provider to connect to a remote computer, in this case the server01 computer.</span></span>
<span data-ttu-id="bc3f2-121">Sie können das Cmdlet jedoch verwenden, um Verbindungen mit Remotecomputern herzustellen, bevor Sie zum WSMan-Anbieter wechseln.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-121">However, you can use the cmdlet to establish connections to remote computers before you change to the WSMan provider.</span></span>
<span data-ttu-id="bc3f2-122">Diese Verbindungen werden in der **Computername** -Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-122">Those connections appear in the **ComputerName** list.</span></span>

## <span data-ttu-id="bc3f2-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bc3f2-123">PARAMETERS</span></span>

### <span data-ttu-id="bc3f2-124">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="bc3f2-124">-NoEncryption</span></span>
<span data-ttu-id="bc3f2-125">Gibt an, dass für die Verbindung keine Verschlüsselung für Remote Vorgänge über HTTP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-125">Indicates that the connection does not use encryption for remote operations over HTTP.</span></span>

<span data-ttu-id="bc3f2-126">Der unverschlüsselte Datenverkehr ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-126">By default, unencrypted traffic is not enabled.</span></span>
<span data-ttu-id="bc3f2-127">Er muss in der lokalen Konfiguration aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-127">It must be enabled in the local configuration.</span></span>

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

### <span data-ttu-id="bc3f2-128">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="bc3f2-128">-OperationTimeout</span></span>
<span data-ttu-id="bc3f2-129">Gibt das Timeout (in Millisekunden) für den WS-Management Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-129">Specifies the time-out, in milliseconds, for the WS-Management operation.</span></span>

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

### <span data-ttu-id="bc3f2-130">-Proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="bc3f2-130">-ProxyAccessType</span></span>
<span data-ttu-id="bc3f2-131">Gibt den Mechanismus an, mit dem der Proxyserver gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-131">Specifies the mechanism by which the proxy server is located.</span></span>
<span data-ttu-id="bc3f2-132">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="bc3f2-132">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bc3f2-133">ProxyIEConfig.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-133">ProxyIEConfig.</span></span>
<span data-ttu-id="bc3f2-134">Verwenden Sie die Internet Explorer-Proxykonfiguration für den aktuellen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-134">Use the Internet Explorer proxy configuration for the current user.</span></span>
- <span data-ttu-id="bc3f2-135">ProxyWinHttpConfig.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-135">ProxyWinHttpConfig.</span></span>
<span data-ttu-id="bc3f2-136">Der WSMAN-Client verwendet die Proxy Einstellungen, die für WinHTTP konfiguriert wurden, mithilfe des ProxyCfg.exe Hilfsprogramms.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-136">The WSMan client uses the proxy settings configured for WinHTTP, using the ProxyCfg.exe utility.</span></span>
- <span data-ttu-id="bc3f2-137">ProxyAutoDetect.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-137">ProxyAutoDetect.</span></span>
<span data-ttu-id="bc3f2-138">Erzwingen Sie die automatische Erkennung eines Proxy Servers.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-138">Force auto-detection of a proxy server.</span></span>
- <span data-ttu-id="bc3f2-139">Proxynoproxyserver.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-139">ProxyNoProxyServer.</span></span>
<span data-ttu-id="bc3f2-140">Verwenden Sie keinen Proxy Server.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-140">Do not use a proxy server.</span></span>
<span data-ttu-id="bc3f2-141">Alle Hostnamen werden lokal aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-141">Resolve all host names locally.</span></span>

<span data-ttu-id="bc3f2-142">Der Standardwert ist proxyieconfig.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-142">The default value is ProxyIEConfig.</span></span>

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

### <span data-ttu-id="bc3f2-143">-Proxy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bc3f2-143">-ProxyAuthentication</span></span>
<span data-ttu-id="bc3f2-144">Gibt die Authentifizierungsmethode an, die auf dem Proxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-144">Specifies the authentication method to use at the proxy.</span></span>
<span data-ttu-id="bc3f2-145">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="bc3f2-145">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bc3f2-146">Standard.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-146">Basic.</span></span>
<span data-ttu-id="bc3f2-147">„Basic“ ist ein Schema, bei dem der Benutzername und das Kennwort im Klartext an den Server oder Proxy gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-147">Basic is a scheme in which the user name and password are sent in clear-text to the server or proxy.</span></span>
- <span data-ttu-id="bc3f2-148">Digest.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-148">Digest.</span></span>
<span data-ttu-id="bc3f2-149">„Digest“ ist ein Abfrage/Rückmeldung-Schema, bei dem eine vom Server angegebene Datenzeichenfolge für die Abfrage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-149">Digest is a challenge-response scheme that uses a server-specified data string for the challenge.</span></span>
- <span data-ttu-id="bc3f2-150">Negotiate</span><span class="sxs-lookup"><span data-stu-id="bc3f2-150">Negotiate.</span></span>
<span data-ttu-id="bc3f2-151">„Negotiate“ ist ein Abfrage/Rückmeldung-Schema, bei dem das für die Authentifizierung zu verwendende Schema mit dem Server oder Proxy ausgehandelt wird.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-151">Negotiate is a challenge-response scheme that negotiates with the server or proxy to determine which scheme to use for authentication.</span></span>
<span data-ttu-id="bc3f2-152">Beispiele sind das Kerberos-Protokoll und NTLM.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-152">Examples are the Kerberos protocol and NTLM.</span></span>

<span data-ttu-id="bc3f2-153">Der Standardwert ist "aushandeln".</span><span class="sxs-lookup"><span data-stu-id="bc3f2-153">The default value is Negotiate.</span></span>

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

### <span data-ttu-id="bc3f2-154">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="bc3f2-154">-ProxyCredential</span></span>
<span data-ttu-id="bc3f2-155">Gibt ein Benutzerkonto an, das über die Berechtigung verfügt, Zugriff über einen zwischenweb Proxy zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-155">Specifies a user account that has permission to gain access through an intermediate Web proxy.</span></span>

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

### <span data-ttu-id="bc3f2-156">-Skipcacheck</span><span class="sxs-lookup"><span data-stu-id="bc3f2-156">-SkipCACheck</span></span>
<span data-ttu-id="bc3f2-157">Gibt an, dass der Client beim Herstellen einer Verbindung über HTTPS nicht überprüft, ob das Serverzertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certification Authority, ca) signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-157">Specifies that, when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>
<span data-ttu-id="bc3f2-158">Verwenden Sie diese Option nur, wenn der Remote Computer von einer anderen Methode als vertrauenswürdig eingestuft wird, z. b. wenn der Remote Computer Teil eines physisch sicheren und isolierten Netzwerks ist oder der Remote Computer in der WS-Management Konfiguration als vertrauenswürdiger Host aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-158">Use this option only when the remote computer is trusted by another method, for example, if the remote computer is part of a network that is physically secure and isolated or the remote computer is listed as a trusted host in the WS-Management configuration.</span></span>

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

### <span data-ttu-id="bc3f2-159">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="bc3f2-159">-SkipCNCheck</span></span>
<span data-ttu-id="bc3f2-160">Gibt an, dass der allgemeine Name des Zertifikats (Common Name, CN) des Servers nicht mit dem Hostnamen des Servers identisch sein muss.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-160">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span>
<span data-ttu-id="bc3f2-161">Diese Option wird nur bei Remotevorgängen über HTTPS eingesetzt</span><span class="sxs-lookup"><span data-stu-id="bc3f2-161">This is used only in remote operations using HTTPS.</span></span>
<span data-ttu-id="bc3f2-162">und sollte nur für vertrauenswürdige Computer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-162">This option should only be used for trusted computers.</span></span>

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

### <span data-ttu-id="bc3f2-163">-Skiprevocationcheck</span><span class="sxs-lookup"><span data-stu-id="bc3f2-163">-SkipRevocationCheck</span></span>
<span data-ttu-id="bc3f2-164">Gibt an, dass die Verbindung den Sperr Status für das Serverzertifikat nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-164">Indicates that the connection does not validate the revocation status on the server certificate.</span></span>

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

### <span data-ttu-id="bc3f2-165">-Spnport</span><span class="sxs-lookup"><span data-stu-id="bc3f2-165">-SPNPort</span></span>
<span data-ttu-id="bc3f2-166">Gibt eine Portnummer an, die an den Verbindungs Dienst Prinzipal Namen (SPN) des Remote Servers angehängt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-166">Specifies a port number to append to the connection Service Principal Name (SPN) of the remote server.</span></span>
<span data-ttu-id="bc3f2-167">Ein SPN wird verwendet, wenn der Authentifizierungsmechanismus „Kerberos“ oder „Negotiate“ lautet.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-167">An SPN is used when the authentication mechanism is Kerberos or Negotiate.</span></span>

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

### <span data-ttu-id="bc3f2-168">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="bc3f2-168">-UseUTF16</span></span>
<span data-ttu-id="bc3f2-169">Gibt an, dass die Verbindung die Anforderung im UTF16-Format anstatt im UTF8-Format codiert.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-169">Indicates that the connection encodes the request in UTF16 format instead of UTF8 format.</span></span>
<span data-ttu-id="bc3f2-170">Standardmäßig wird die UTF8-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-170">The default is UTF8 encoding.</span></span>

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

### <span data-ttu-id="bc3f2-171">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bc3f2-171">CommonParameters</span></span>
<span data-ttu-id="bc3f2-172">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bc3f2-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bc3f2-173">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bc3f2-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bc3f2-174">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bc3f2-174">INPUTS</span></span>

## <span data-ttu-id="bc3f2-175">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bc3f2-175">OUTPUTS</span></span>

### <span data-ttu-id="bc3f2-176">SessionOption</span><span class="sxs-lookup"><span data-stu-id="bc3f2-176">SessionOption</span></span>

## <span data-ttu-id="bc3f2-177">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bc3f2-177">NOTES</span></span>

## <span data-ttu-id="bc3f2-178">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bc3f2-178">RELATED LINKS</span></span>

[<span data-ttu-id="bc3f2-179">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="bc3f2-179">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="bc3f2-180">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="bc3f2-180">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="bc3f2-181">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="bc3f2-181">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="bc3f2-182">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="bc3f2-182">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="bc3f2-183">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="bc3f2-183">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="bc3f2-184">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc3f2-184">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="bc3f2-185">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="bc3f2-185">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="bc3f2-186">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc3f2-186">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="bc3f2-187">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc3f2-187">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="bc3f2-188">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc3f2-188">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="bc3f2-189">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="bc3f2-189">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="bc3f2-190">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="bc3f2-190">Test-WSMan</span></span>](Test-WSMan.md)

