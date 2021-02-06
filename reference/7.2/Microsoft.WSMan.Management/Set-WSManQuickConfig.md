---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 10/02/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmanquickconfig?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManQuickConfig
ms.openlocfilehash: e5d50af0551a183b8e9e1995fbd722c331a48486
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598185"
---
# <span data-ttu-id="db3fa-102">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="db3fa-102">Set-WSManQuickConfig</span></span>

## <span data-ttu-id="db3fa-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="db3fa-103">SYNOPSIS</span></span>
<span data-ttu-id="db3fa-104">Konfiguriert den lokalen Computer für die Remoteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="db3fa-104">Configures the local computer for remote management.</span></span>

## <span data-ttu-id="db3fa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="db3fa-105">SYNTAX</span></span>

### <span data-ttu-id="db3fa-106">Alle</span><span class="sxs-lookup"><span data-stu-id="db3fa-106">All</span></span>

```
Set-WSManQuickConfig [-UseSSL] [-Force] [-SkipNetworkProfileCheck] [<CommonParameters>]
```

## <span data-ttu-id="db3fa-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="db3fa-107">DESCRIPTION</span></span>

<span data-ttu-id="db3fa-108">Das- `Set-WSManQuickConfig` Cmdlet konfiguriert den Computer für den Empfang von PowerShell-Remote Befehlen, die unter Verwendung der WS-Management (Web Services for Management)-Technologie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="db3fa-108">The `Set-WSManQuickConfig` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the Web Services for Management (WS-Management) technology.</span></span>

<span data-ttu-id="db3fa-109">`Set-WSManQuickConfig` führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="db3fa-109">`Set-WSManQuickConfig` performs the following actions:</span></span>

- <span data-ttu-id="db3fa-110">Überprüft, ob der WinRM-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="db3fa-110">Checks whether the WinRM service is running.</span></span> <span data-ttu-id="db3fa-111">Wenn der WinRM-Dienst nicht ausgeführt wird, wird der-Dienst gestartet.</span><span class="sxs-lookup"><span data-stu-id="db3fa-111">If the WinRM service isn't running, the service is started.</span></span>
- <span data-ttu-id="db3fa-112">Legt den Starttyp des WinRM-Diensts auf "Automatic" fest.</span><span class="sxs-lookup"><span data-stu-id="db3fa-112">Sets the WinRM service startup type to automatic.</span></span>
- <span data-ttu-id="db3fa-113">Erstellt einen Listener, um Anforderungen an eine beliebige IP-Adresse zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="db3fa-113">Creates a listener to accept requests on any IP address.</span></span> <span data-ttu-id="db3fa-114">Der Standard Transport ist " **http**".</span><span class="sxs-lookup"><span data-stu-id="db3fa-114">The default transport is **HTTP**.</span></span>
- <span data-ttu-id="db3fa-115">Aktiviert eine Firewallausnahme für den WinRM-Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="db3fa-115">Enables a firewall exception for WinRM traffic.</span></span>

<span data-ttu-id="db3fa-116">Starten Sie `Set-WSManQuickConfig` PowerShell mit der Option **als Administrator ausführen** , um auszuführen.</span><span class="sxs-lookup"><span data-stu-id="db3fa-116">To run `Set-WSManQuickConfig`, start PowerShell with the **Run as Administrator** option.</span></span>

## <span data-ttu-id="db3fa-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="db3fa-117">EXAMPLES</span></span>

### <span data-ttu-id="db3fa-118">Beispiel 1: Aktivieren der Remote Verwaltung des lokalen Computers über http</span><span class="sxs-lookup"><span data-stu-id="db3fa-118">Example 1: Enable remote management of the local computer over HTTP</span></span>

<span data-ttu-id="db3fa-119">In diesem Beispiel wird die erforderliche Konfiguration festgelegt, um die Remote Verwaltung des lokalen Computers zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="db3fa-119">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="db3fa-120">Standardmäßig erstellt dieser Befehl einen WS-Management Listener auf **http**.</span><span class="sxs-lookup"><span data-stu-id="db3fa-120">By default, this command creates a WS-Management listener on **HTTP**.</span></span>

```powershell
Set-WSManQuickConfig
```

### <span data-ttu-id="db3fa-121">Beispiel 2: Aktivieren der Remote Verwaltung des lokalen Computers über HTTPS</span><span class="sxs-lookup"><span data-stu-id="db3fa-121">Example 2: Enable remote management of the local computer over HTTPS</span></span>

<span data-ttu-id="db3fa-122">In diesem Beispiel wird die erforderliche Konfiguration festgelegt, um die Remote Verwaltung des lokalen Computers zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="db3fa-122">This example sets the required configuration to enable remote management of the local computer.</span></span> <span data-ttu-id="db3fa-123">Der **Parameter** "-Parameter" gibt an, dass **https** für die Kommunikation mit dem Computer verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="db3fa-123">The **UseSSL** parameter specifies that **HTTPS** is used to communicate with the computer.</span></span>

```powershell
Set-WSManQuickConfig -UseSSL
```

> [!NOTE]
> <span data-ttu-id="db3fa-124">**Https** erfordert eine manuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="db3fa-124">**HTTPS** requires manual configuration.</span></span> <span data-ttu-id="db3fa-125">Weitere Informationen finden Sie in der Beschreibung **des Parameters** "" von "".</span><span class="sxs-lookup"><span data-stu-id="db3fa-125">For more information, see the **UseSSL** parameter's description.</span></span>

## <span data-ttu-id="db3fa-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="db3fa-126">PARAMETERS</span></span>

### <span data-ttu-id="db3fa-127">-Force</span><span class="sxs-lookup"><span data-stu-id="db3fa-127">-Force</span></span>

<span data-ttu-id="db3fa-128">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="db3fa-128">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="db3fa-129">-Skipnetworkprofilecheck</span><span class="sxs-lookup"><span data-stu-id="db3fa-129">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="db3fa-130">Konfiguriert Windows-Client Versionen für Remoting, wenn sich der Computer in einem öffentlichen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="db3fa-130">Configures Windows client versions for remoting when the computer is on a public network.</span></span> <span data-ttu-id="db3fa-131">Dieser Parameter aktiviert eine Firewallregel für öffentliche Netzwerke, die den Remotezugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="db3fa-131">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="db3fa-132">Dieser Parameter hat keine Auswirkung auf Serverversionen von Windows, die standardmäßig über eine Firewallregel für das lokale Subnetz für öffentliche Netzwerke verfügen.</span><span class="sxs-lookup"><span data-stu-id="db3fa-132">This parameter has no effect on server versions of Windows, that by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="db3fa-133">Wenn die Firewallregel für das lokale Subnetz in der Server Version von Windows deaktiviert ist, wird `Enable-PSRemoting` Sie unabhängig vom Wert dieses Parameters erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="db3fa-133">If the local subnet firewall rule is disabled on the server version of Windows, `Enable-PSRemoting` re-enables it, regardless of this parameter's value.</span></span>

<span data-ttu-id="db3fa-134">Verwenden Sie das `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul, um die Einschränkung für das lokale Subnetz zu entfernen und den Remote Zugriff von allen Standorten in öffentlichen Netzwerken aus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="db3fa-134">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="db3fa-135">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="db3fa-135">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="db3fa-136">-US-</span><span class="sxs-lookup"><span data-stu-id="db3fa-136">-UseSSL</span></span>

<span data-ttu-id="db3fa-137">Gibt an, dass das Secure Sockets Layer (SSL)-Protokoll verwendet wird, um eine Verbindung mit dem Remote Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="db3fa-137">Specifies that the Secure Sockets Layer (SSL) protocol is used to establish a connection to the remote computer.</span></span> <span data-ttu-id="db3fa-138">Standardmäßig wird SSL nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="db3fa-138">By default, SSL isn't used.</span></span>

<span data-ttu-id="db3fa-139">WS-Management verschlüsselt alle PowerShell-Inhalte, die über das Netzwerk übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="db3fa-139">WS-Management encrypts all the PowerShell content that is transmitted over the network.</span></span> <span data-ttu-id="db3fa-140">Mit **dem Parameter "** Parameter" können Sie den zusätzlichen Schutz von HTTPS anstelle von http angeben.</span><span class="sxs-lookup"><span data-stu-id="db3fa-140">The **UseSSL** parameter lets you specify the additional protection of HTTPS instead of HTTP.</span></span> <span data-ttu-id="db3fa-141">Wenn Sie diesen Parameter verwenden und SSL an dem für die Verbindung verwendeten Port nicht verfügbar ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="db3fa-141">If you use this parameter and SSL isn't available on the port that's used for the connection, the command fails.</span></span>

<span data-ttu-id="db3fa-142">**Https** erfordert die manuelle Konfiguration von WinRM-und Firewallregeln.</span><span class="sxs-lookup"><span data-stu-id="db3fa-142">**HTTPS** requires manual configuration of WinRM and firewall rules.</span></span> <span data-ttu-id="db3fa-143">Weitere Informationen finden Sie unter Gewusst [wie: Konfigurieren von WinRM für HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span><span class="sxs-lookup"><span data-stu-id="db3fa-143">For more information, see [How To: Configure WINRM for HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https).</span></span>

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

### <span data-ttu-id="db3fa-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="db3fa-144">CommonParameters</span></span>

<span data-ttu-id="db3fa-145">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="db3fa-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="db3fa-146">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="db3fa-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="db3fa-147">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="db3fa-147">INPUTS</span></span>

### <span data-ttu-id="db3fa-148">Keine</span><span class="sxs-lookup"><span data-stu-id="db3fa-148">None</span></span>

<span data-ttu-id="db3fa-149">Dieses Cmdlet akzeptiert keine Eingaben.</span><span class="sxs-lookup"><span data-stu-id="db3fa-149">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="db3fa-150">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="db3fa-150">OUTPUTS</span></span>

### <span data-ttu-id="db3fa-151">Keine</span><span class="sxs-lookup"><span data-stu-id="db3fa-151">None</span></span>

<span data-ttu-id="db3fa-152">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="db3fa-152">This cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="db3fa-153">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="db3fa-153">NOTES</span></span>

## <span data-ttu-id="db3fa-154">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="db3fa-154">RELATED LINKS</span></span>

[<span data-ttu-id="db3fa-155">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="db3fa-155">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="db3fa-156">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="db3fa-156">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="db3fa-157">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="db3fa-157">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="db3fa-158">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="db3fa-158">Enable-PSRemoting</span></span>](../Microsoft.PowerShell.Core/Enable-PSRemoting.md)

[<span data-ttu-id="db3fa-159">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="db3fa-159">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="db3fa-160">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="db3fa-160">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="db3fa-161">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="db3fa-161">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="db3fa-162">Gewusst wie: Konfigurieren von WinRM für HTTPS</span><span class="sxs-lookup"><span data-stu-id="db3fa-162">How To: Configure WINRM for HTTPS</span></span>](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https)

[<span data-ttu-id="db3fa-163">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="db3fa-163">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="db3fa-164">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="db3fa-164">New-PSSession</span></span>](../Microsoft.PowerShell.Core/New-PSSession.md)

[<span data-ttu-id="db3fa-165">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="db3fa-165">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="db3fa-166">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="db3fa-166">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="db3fa-167">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="db3fa-167">Test-WSMan</span></span>](Test-WSMan.md)

