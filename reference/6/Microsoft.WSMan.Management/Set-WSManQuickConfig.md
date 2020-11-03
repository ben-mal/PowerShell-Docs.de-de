---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: e8bc5bc248eafe479f366397aa947845e94e190c
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "93219831"
---
# <span data-ttu-id="074f3-103">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="074f3-103">Set-WSManQuickConfig</span></span>

## <span data-ttu-id="074f3-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="074f3-104">SYNOPSIS</span></span>
<span data-ttu-id="074f3-105">Konfiguriert den lokalen Computer für die Remoteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="074f3-105">Configures the local computer for remote management.</span></span>

## <span data-ttu-id="074f3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="074f3-106">SYNTAX</span></span>

### <span data-ttu-id="074f3-107">Alle</span><span class="sxs-lookup"><span data-stu-id="074f3-107">All</span></span>

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## <span data-ttu-id="074f3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="074f3-108">DESCRIPTION</span></span>

<span data-ttu-id="074f3-109">Das- `Set-WSManQuickConfig` Cmdlet konfiguriert den Computer für den Empfang von PowerShell-Remote Befehlen, die unter Verwendung der WS-Management (Web Services for Management)-Technologie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="074f3-109">The `Set-WSManQuickConfig` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the Web Services for Management (WS-Management) technology.</span></span>

<span data-ttu-id="074f3-110">`Set-WSManQuickConfig` führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="074f3-110">`Set-WSManQuickConfig` performs the following actions:</span></span>

- <span data-ttu-id="074f3-111">Überprüft, ob der WinRM-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="074f3-111">Checks whether the WinRM service is running.</span></span> <span data-ttu-id="074f3-112">Wenn der WinRM-Dienst nicht ausgeführt wird, wird der-Dienst gestartet.</span><span class="sxs-lookup"><span data-stu-id="074f3-112">If the WinRM service isn't running, the service is started.</span></span>
- <span data-ttu-id="074f3-113">Legt den Starttyp des WinRM-Diensts auf "Automatic" fest.</span><span class="sxs-lookup"><span data-stu-id="074f3-113">Sets the WinRM service startup type to automatic.</span></span>
- <span data-ttu-id="074f3-114">Erstellt einen Listener, um Anforderungen an eine beliebige IP-Adresse zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="074f3-114">Creates a listener to accept requests on any IP address.</span></span> <span data-ttu-id="074f3-115">Der Standard Transport ist " **http** ".</span><span class="sxs-lookup"><span data-stu-id="074f3-115">The default transport is **HTTP**.</span></span>
- <span data-ttu-id="074f3-116">Aktiviert eine Firewallausnahme für den WinRM-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="074f3-116">Enables a firewall exception for WinRM traffic.</span></span>

<span data-ttu-id="074f3-117">Starten Sie `Set-WSManQuickConfig` PowerShell mit der Option **als Administrator ausführen** , um auszuführen.</span><span class="sxs-lookup"><span data-stu-id="074f3-117">To run `Set-WSManQuickConfig`, start PowerShell with the **Run as Administrator** option.</span></span>

## <span data-ttu-id="074f3-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="074f3-118">EXAMPLES</span></span>

### <span data-ttu-id="074f3-119">Beispiel 1: Aktivieren der Remote Verwaltung des lokalen Computers über http</span><span class="sxs-lookup"><span data-stu-id="074f3-119">Example 1: Enable remote management of the local computer over HTTP</span></span>

<span data-ttu-id="074f3-120">In diesem Beispiel wird die erforderliche Konfiguration festgelegt, um die Remote Verwaltung des lokalen Computers zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="074f3-120">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="074f3-121">Standardmäßig erstellt dieser Befehl einen WS-Management Listener auf **http**.</span><span class="sxs-lookup"><span data-stu-id="074f3-121">By default, this command creates a WS-Management listener on **HTTP**.</span></span>

```powershell
Set-WSManQuickConfig
```

### <span data-ttu-id="074f3-122">Beispiel 2: Aktivieren der Remote Verwaltung des lokalen Computers über HTTPS</span><span class="sxs-lookup"><span data-stu-id="074f3-122">Example 2: Enable remote management of the local computer over HTTPS</span></span>

<span data-ttu-id="074f3-123">In diesem Beispiel wird die erforderliche Konfiguration festgelegt, um die Remote Verwaltung des lokalen Computers zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="074f3-123">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="074f3-124">Der **Parameter** "-Parameter" gibt an, dass **https** für die Kommunikation mit dem Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="074f3-124">The **UseSSL** parameter specifies that **HTTPS** is used to communicate with the computer.</span></span>

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> <span data-ttu-id="074f3-125">**Https** erfordert eine manuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="074f3-125">**HTTPS** requires manual configuration.</span></span> <span data-ttu-id="074f3-126">Weitere Informationen finden Sie in der Beschreibung **des Parameters** "" von "".</span><span class="sxs-lookup"><span data-stu-id="074f3-126">For more information, see the **UseSSL** parameter's description.</span></span>

## <span data-ttu-id="074f3-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="074f3-127">PARAMETERS</span></span>

### <span data-ttu-id="074f3-128">-Force</span><span class="sxs-lookup"><span data-stu-id="074f3-128">-Force</span></span>

<span data-ttu-id="074f3-129">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="074f3-129">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="074f3-130">-Skipnetworkprofilecheck</span><span class="sxs-lookup"><span data-stu-id="074f3-130">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="074f3-131">Konfiguriert Windows-Client Versionen für Remoting, wenn sich der Computer in einem öffentlichen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="074f3-131">Configures Windows client versions for remoting when the computer is on a public network.</span></span> <span data-ttu-id="074f3-132">Dieser Parameter aktiviert eine Firewallregel für öffentliche Netzwerke, die den Remotezugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="074f3-132">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="074f3-133">Dieser Parameter hat keine Auswirkung auf Serverversionen von Windows, die standardmäßig über eine Firewallregel für das lokale Subnetz für öffentliche Netzwerke verfügen.</span><span class="sxs-lookup"><span data-stu-id="074f3-133">This parameter has no effect on server versions of Windows, that by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="074f3-134">Wenn die Firewallregel für das lokale Subnetz in der Server Version von Windows deaktiviert ist, wird `Enable-PSRemoting` Sie unabhängig vom Wert dieses Parameters erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="074f3-134">If the local subnet firewall rule is disabled on the server version of Windows, `Enable-PSRemoting` re-enables it, regardless of this parameter's value.</span></span>

<span data-ttu-id="074f3-135">Verwenden Sie das `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul, um die Einschränkung für das lokale Subnetz zu entfernen und den Remote Zugriff von allen Standorten in öffentlichen Netzwerken aus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="074f3-135">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="074f3-136">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="074f3-136">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="074f3-137">-US-</span><span class="sxs-lookup"><span data-stu-id="074f3-137">-UseSSL</span></span>

<span data-ttu-id="074f3-138">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="074f3-138">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span> <span data-ttu-id="074f3-139">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="074f3-139">By default, SSL isn't used.</span></span>

<span data-ttu-id="074f3-140">WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="074f3-140">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="074f3-141">Mit **dem Parameter "** Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="074f3-141">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="074f3-142">Wenn Sie diesen Parameter verwenden und SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="074f3-142">If you use this parameter and SSL isn't available on the port that's used for the connection, the command fails.</span></span>

<span data-ttu-id="074f3-143">**Https** erfordert die manuelle Konfiguration von WinRM-und Firewallregeln.</span><span class="sxs-lookup"><span data-stu-id="074f3-143">**HTTPS** requires manual configuration of WinRM and firewall rules.</span></span> <span data-ttu-id="074f3-144">Weitere Informationen finden Sie unter Gewusst [wie: Konfigurieren von WinRM für HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span><span class="sxs-lookup"><span data-stu-id="074f3-144">For more information, see [How To: Configure WINRM for HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span></span>

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

### <span data-ttu-id="074f3-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="074f3-145">CommonParameters</span></span>

<span data-ttu-id="074f3-146">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="074f3-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="074f3-147">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="074f3-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="074f3-148">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="074f3-148">INPUTS</span></span>

### <span data-ttu-id="074f3-149">Keine</span><span class="sxs-lookup"><span data-stu-id="074f3-149">None</span></span>

<span data-ttu-id="074f3-150">Dieses Cmdlet akzeptiert keine Eingaben.</span><span class="sxs-lookup"><span data-stu-id="074f3-150">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="074f3-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="074f3-151">OUTPUTS</span></span>

### <span data-ttu-id="074f3-152">Keine</span><span class="sxs-lookup"><span data-stu-id="074f3-152">None</span></span>

<span data-ttu-id="074f3-153">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="074f3-153">This cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="074f3-154">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="074f3-154">NOTES</span></span>

## <span data-ttu-id="074f3-155">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="074f3-155">RELATED LINKS</span></span>

[<span data-ttu-id="074f3-156">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="074f3-156">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="074f3-157">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="074f3-157">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="074f3-158">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="074f3-158">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="074f3-159">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="074f3-159">Enable-PSRemoting</span></span>](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[<span data-ttu-id="074f3-160">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="074f3-160">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="074f3-161">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="074f3-161">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="074f3-162">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="074f3-162">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="074f3-163">Gewusst wie: Konfigurieren von WinRM für HTTPS</span><span class="sxs-lookup"><span data-stu-id="074f3-163">How To: Configure WINRM for HTTPS</span></span>](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[<span data-ttu-id="074f3-164">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="074f3-164">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="074f3-165">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="074f3-165">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="074f3-166">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="074f3-166">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="074f3-167">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="074f3-167">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="074f3-168">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="074f3-168">Test-WSMan</span></span>](Test-WSMan.md)
