---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2020
ms.locfileid: "93218039"
---
# <span data-ttu-id="c905d-103">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="c905d-103">Enable-PSRemoting</span></span>

## <span data-ttu-id="c905d-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c905d-104">SYNOPSIS</span></span>
<span data-ttu-id="c905d-105">Konfiguriert den Computer für den Empfang von Remotebefehlen.</span><span class="sxs-lookup"><span data-stu-id="c905d-105">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="c905d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c905d-106">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c905d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c905d-107">DESCRIPTION</span></span>

<span data-ttu-id="c905d-108">Das- `Enable-PSRemoting` Cmdlet konfiguriert den Computer für den Empfang von PowerShell-Remote Befehlen, die mithilfe der WS-Management-Technologie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c905d-108">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span>

<span data-ttu-id="c905d-109">PowerShell-Remoting ist unter Windows Server 2012 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c905d-109">PowerShell remoting is enabled by default on Windows Server 2012.</span></span> <span data-ttu-id="c905d-110">Sie können verwenden `Enable-PSRemoting` , um PowerShell-Remoting unter anderen unterstützten Versionen von Windows zu aktivieren und Remoting unter Windows Server 2012 wieder zu aktivieren, wenn es deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="c905d-110">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting on Windows Server 2012 if it becomes disabled.</span></span>

<span data-ttu-id="c905d-111">Sie müssen diesen Befehl nur einmal auf jedem Computer ausführen, der Befehle empfängt.</span><span class="sxs-lookup"><span data-stu-id="c905d-111">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="c905d-112">Sie müssen Sie nicht auf Computern ausführen, auf denen nur Befehle gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c905d-112">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="c905d-113">Da die Konfiguration Listener startet, ist es ratsam, Sie nur an der Stelle auszuführen, an der Sie benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c905d-113">Because the configuration starts listeners, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="c905d-114">Ab PowerShell 3,0 `Enable-PSRemoting` kann das Cmdlet PowerShell-Remoting unter Client Versionen von Windows aktivieren, wenn sich der Computer in einem öffentlichen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="c905d-114">Beginning in PowerShell 3.0, the `Enable-PSRemoting` cmdlet can enable PowerShell remoting on client versions of Windows when the computer is on a public network.</span></span> <span data-ttu-id="c905d-115">Weitere Informationen finden Sie in der Beschreibung des **SkipNetworkProfileCheck** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="c905d-115">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="c905d-116">Das- `Enable-PSRemoting` Cmdlet führt die folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="c905d-116">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="c905d-117">Führt das Cmdlet " [Set-wsmanquickconfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) " aus, mit dem die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="c905d-117">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="c905d-118">Startet den WinRM-Dienst.</span><span class="sxs-lookup"><span data-stu-id="c905d-118">Starts the WinRM service.</span></span>
  - <span data-ttu-id="c905d-119">Legt den Starttyp für den WinRM-Dienst auf "automatisch" fest.</span><span class="sxs-lookup"><span data-stu-id="c905d-119">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="c905d-120">Erstellt einen Listener, um Anforderungen an eine beliebige IP-Adresse zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="c905d-120">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="c905d-121">Aktiviert eine Firewallausnahme für die WS-Management-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="c905d-121">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="c905d-122">Registriert die Sitzungs Konfigurationen **Microsoft. PowerShell** und **Microsoft. PowerShell. Workflow** , sofern Sie nicht bereits registriert sind.</span><span class="sxs-lookup"><span data-stu-id="c905d-122">Registers the **Microsoft.PowerShell** and **Microsoft.PowerShell.Workflow** session configurations, if it they are not already registered.</span></span>
  - <span data-ttu-id="c905d-123">Registriert die **Microsoft. PowerShell32** -Sitzungs Konfiguration auf 64-Bit-Computern, sofern Sie noch nicht registriert ist.</span><span class="sxs-lookup"><span data-stu-id="c905d-123">Registers the **Microsoft.PowerShell32** session configuration on 64-bit computers, if it is not already registered.</span></span>
  - <span data-ttu-id="c905d-124">Aktiviert alle Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="c905d-124">Enables all session configurations.</span></span>
  - <span data-ttu-id="c905d-125">Ändert die Sicherheits Beschreibung aller Sitzungs Konfigurationen, um den Remote Zugriff zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c905d-125">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="c905d-126">Startet den WinRM-Dienst neu, damit die vorangehenden Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c905d-126">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="c905d-127">Um dieses Cmdlet auf der Windows-Plattform auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="c905d-127">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="c905d-128">Dies gilt nicht für Linux-oder MacOS-Versionen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c905d-128">This does not apply to Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="c905d-129">Verwenden Sie auf Systemen, die sowohl PowerShell 3,0 als auch PowerShell 2,0 haben, nicht PowerShell 2,0, um die `Enable-PSRemoting` `Disable-PSRemoting` Cmdlets und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c905d-129">On systems that have both PowerShell 3.0 and PowerShell 2.0, do not use PowerShell 2.0 to run the `Enable-PSRemoting` and `Disable-PSRemoting` cmdlets.</span></span> <span data-ttu-id="c905d-130">Die Befehle scheinen erfolgreich ausgeführt zu werden, das Remoting ist jedoch nicht ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c905d-130">The commands might appear to succeed, but the remoting is not configured correctly.</span></span> <span data-ttu-id="c905d-131">Bei Remote Befehlen und späteren versuchen, das Remoting zu aktivieren und zu deaktivieren, treten wahrscheinlich Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c905d-131">Remote commands and later attempts to enable and disable remoting, are likely to fail.</span></span>

## <span data-ttu-id="c905d-132">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c905d-132">EXAMPLES</span></span>

### <span data-ttu-id="c905d-133">Beispiel 1: Konfigurieren eines Computers für den Empfang von Remote Befehlen</span><span class="sxs-lookup"><span data-stu-id="c905d-133">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="c905d-134">Mit diesem Befehl wird der Computer für den Empfang von Remotebefehlen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c905d-134">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

### <span data-ttu-id="c905d-135">Beispiel 2: Konfigurieren eines Computers für den Empfang von Remote Befehlen ohne Bestätigungsaufforderung</span><span class="sxs-lookup"><span data-stu-id="c905d-135">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="c905d-136">Mit diesem Befehl wird der Computer für den Empfang von Remotebefehlen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c905d-136">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="c905d-137">Der **Force** -Parameter unterdrückt die Eingabe Aufforderungen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="c905d-137">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

### <span data-ttu-id="c905d-138">Beispiel 3: zulassen des Remote Zugriffs auf Clients</span><span class="sxs-lookup"><span data-stu-id="c905d-138">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="c905d-139">In diesem Beispiel wird gezeigt, wie der Remote Zugriff aus öffentlichen Netzwerken unter Client Versionen des Windows-Betriebssystems zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="c905d-139">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="c905d-140">Der Name der Firewallregel kann sich für unterschiedliche Windows-Versionen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c905d-140">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="c905d-141">Verwenden `Get-NetFirewallRule` Sie, um eine Liste der Regeln anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c905d-141">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="c905d-142">Vor dem Aktivieren der Firewallregel können Sie die Sicherheitseinstellungen in der Regel anzeigen, um zu überprüfen, ob die Konfiguration für Ihre Umgebung geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="c905d-142">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

<span data-ttu-id="c905d-143">Standardmäßig `Enable-PSRemoting` erstellt Netzwerk Regeln, die den Remote Zugriff über private Netzwerke und Domänen Netzwerke ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c905d-143">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="c905d-144">Der Befehl verwendet den **SkipNetworkProfileCheck** -Parameter, um Remotezugriff aus öffentlichen Netzwerken im gleichen lokalen Subnetz zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="c905d-144">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="c905d-145">Der Befehl gibt den **Force** -Parameter an, um Bestätigungsmeldungen zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="c905d-145">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="c905d-146">Der **skipnetworkprofilecheck** -Parameter wirkt sich nicht auf Serverversionen des Windows-Betriebssystems aus, die standardmäßig den Remote Zugriff von öffentlichen Netzwerken im gleichen lokalen Subnetz zulassen.</span><span class="sxs-lookup"><span data-stu-id="c905d-146">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="c905d-147">Das- `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul fügt eine Firewallregel hinzu, die den Remote Zugriff aus öffentlichen Netzwerken von einem beliebigen Remote Standort aus zulässt.</span><span class="sxs-lookup"><span data-stu-id="c905d-147">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="c905d-148">Dies gilt auch für Standorte in unterschiedlichen Subnetzen.</span><span class="sxs-lookup"><span data-stu-id="c905d-148">This includes locations in different subnets.</span></span>

> [!NOTE]
> <span data-ttu-id="c905d-149">Der Name der Firewallregel kann je nach Windows-Version unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="c905d-149">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="c905d-150">Verwenden `Get-NetFirewallRule` Sie das Cmdlet, um die Namen der Regeln auf dem System aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="c905d-150">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="c905d-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c905d-151">PARAMETERS</span></span>

### <span data-ttu-id="c905d-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c905d-152">-Confirm</span></span>

<span data-ttu-id="c905d-153">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="c905d-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c905d-154">-Force</span><span class="sxs-lookup"><span data-stu-id="c905d-154">-Force</span></span>

<span data-ttu-id="c905d-155">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c905d-155">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c905d-156">-Skipnetworkprofilecheck</span><span class="sxs-lookup"><span data-stu-id="c905d-156">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="c905d-157">Gibt an, dass dieses Cmdlet Remoting unter Client Versionen des Windows-Betriebssystems aktiviert, wenn sich der Computer in einem öffentlichen Netzwerk befindet.</span><span class="sxs-lookup"><span data-stu-id="c905d-157">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="c905d-158">Dieser Parameter aktiviert eine Firewallregel für öffentliche Netzwerke, die den Remotezugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="c905d-158">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="c905d-159">Dieser Parameter wirkt sich nicht auf Serverversionen des Windows-Betriebssystems aus, die standardmäßig über eine Firewallregel für ein lokales Subnetz für öffentliche Netzwerke verfügen.</span><span class="sxs-lookup"><span data-stu-id="c905d-159">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="c905d-160">Wenn die Firewallregel für das lokale Subnetz für eine Server Version deaktiviert ist, wird `Enable-PSRemoting` Sie unabhängig vom Wert dieses Parameters erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c905d-160">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="c905d-161">Verwenden Sie das `Set-NetFirewallRule` Cmdlet im **Netsecurity** -Modul, um die Einschränkung für das lokale Subnetz zu entfernen und den Remote Zugriff von allen Standorten in öffentlichen Netzwerken aus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c905d-161">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="c905d-162">Dieser Parameter wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c905d-162">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c905d-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c905d-163">-WhatIf</span></span>

<span data-ttu-id="c905d-164">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c905d-164">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c905d-165">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c905d-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c905d-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c905d-166">CommonParameters</span></span>

<span data-ttu-id="c905d-167">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c905d-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c905d-168">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c905d-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c905d-169">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c905d-169">INPUTS</span></span>

### <span data-ttu-id="c905d-170">Keine</span><span class="sxs-lookup"><span data-stu-id="c905d-170">None</span></span>

<span data-ttu-id="c905d-171">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="c905d-171">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="c905d-172">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c905d-172">OUTPUTS</span></span>

### <span data-ttu-id="c905d-173">System.String</span><span class="sxs-lookup"><span data-stu-id="c905d-173">System.String</span></span>

<span data-ttu-id="c905d-174">Dieses Cmdlet gibt Zeichen folgen zurück, die die Ergebnisse beschreiben.</span><span class="sxs-lookup"><span data-stu-id="c905d-174">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="c905d-175">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c905d-175">NOTES</span></span>

<span data-ttu-id="c905d-176">In PowerShell 3,0 `Enable-PSRemoting` erstellt die folgenden Firewallausnahmen für die WS-Management-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="c905d-176">In PowerShell 3.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="c905d-177">Unter Serverversionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt Firewallregeln für private Netzwerke und Domänen Netzwerke, die Remote Zugriff zulassen, und erstellt eine Firewallregel für öffentliche Netzwerke, die den Remote Zugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="c905d-177">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="c905d-178">Unter Client Versionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt in PowerShell 3,0 Firewallregeln für private Netzwerke und Domänen Netzwerke, die uneingeschränkten Remote Zugriff zulassen.</span><span class="sxs-lookup"><span data-stu-id="c905d-178">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 3.0 creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="c905d-179">Um eine Firewallregel für öffentliche Netzwerke zu erstellen, die Remotezugriff aus dem gleichen lokalen Subnetz zulässt, verwenden Sie den **SkipNetworkProfileCheck** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="c905d-179">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="c905d-180">Wenn Sie auf Client-oder Serverversionen des Windows-Betriebssystems eine Firewallregel für öffentliche Netzwerke erstellen möchten, die die Einschränkung des lokalen Subnetzes entfernt und den Remote Zugriff zulässt, verwenden `Set-NetFirewallRule` Sie das Cmdlet im Netsecurity-Modul, um den folgenden Befehl auszuführen: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="c905d-180">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="c905d-181">In PowerShell 2,0 `Enable-PSRemoting` erstellt die folgenden Firewallausnahmen für die WS-Management-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="c905d-181">In PowerShell 2.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="c905d-182">Unter Serverversionen des Windows-Betriebssystems werden Firewallregeln für alle Netzwerke erstellt, die Remote Zugriff zulassen.</span><span class="sxs-lookup"><span data-stu-id="c905d-182">On server versions of the Windows operating system, it creates firewall rules for all networks that allow remote access.</span></span>

<span data-ttu-id="c905d-183">Unter Client Versionen des Windows-Betriebssystems `Enable-PSRemoting` erstellt in PowerShell 2,0 eine Firewallausnahme nur für Domänen-und private Netzwerk Orte.</span><span class="sxs-lookup"><span data-stu-id="c905d-183">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 2.0 creates a firewall exception only for domain and private network locations.</span></span> <span data-ttu-id="c905d-184">Um Sicherheitsrisiken zu minimieren, `Enable-PSRemoting` erstellt keine Firewallregel für öffentliche Netzwerke in Client Versionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="c905d-184">To minimize security risks, `Enable-PSRemoting` does not create a firewall rule for public networks on client versions of Windows.</span></span> <span data-ttu-id="c905d-185">Wenn der aktuelle Netzwerkort öffentlich ist, wird `Enable-PSRemoting` die folgende Meldung zurückgegeben: der Status der Firewall kann nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="c905d-185">When the current network location is public, `Enable-PSRemoting` returns the following message: Unable to check the status of the firewall.</span></span>

<span data-ttu-id="c905d-186">Ab PowerShell 3,0 `Enable-PSRemoting` aktiviert alle Sitzungs Konfigurationen, indem der Wert der **aktivierten** -Eigenschaft aller Sitzungs Konfigurationen auf festgelegt wird `$True` .</span><span class="sxs-lookup"><span data-stu-id="c905d-186">Starting in PowerShell 3.0, `Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="c905d-187">Entfernt in PowerShell 2,0 `Enable-PSRemoting` die **Deny_All** Einstellung aus der Sicherheits Beschreibung der Sitzungs Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="c905d-187">In PowerShell 2.0, `Enable-PSRemoting` removes the **Deny_All** setting from the security descriptor of session configurations.</span></span> <span data-ttu-id="c905d-188">Entfernt in PowerShell 3,0 `Enable-PSRemoting` die Einstellungen für **Deny_All** und **Network_Deny_All** .</span><span class="sxs-lookup"><span data-stu-id="c905d-188">In PowerShell 3.0, `Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="c905d-189">Dies ermöglicht den Remote Zugriff auf Sitzungs Konfigurationen, die für die lokale Verwendung reserviert wurden.</span><span class="sxs-lookup"><span data-stu-id="c905d-189">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="c905d-190">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c905d-190">RELATED LINKS</span></span>

[<span data-ttu-id="c905d-191">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c905d-191">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="c905d-192">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c905d-192">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="c905d-193">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c905d-193">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="c905d-194">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c905d-194">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="c905d-195">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="c905d-195">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="c905d-196">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="c905d-196">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="c905d-197">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="c905d-197">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="c905d-198">about_Remote</span><span class="sxs-lookup"><span data-stu-id="c905d-198">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="c905d-199">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="c905d-199">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)
