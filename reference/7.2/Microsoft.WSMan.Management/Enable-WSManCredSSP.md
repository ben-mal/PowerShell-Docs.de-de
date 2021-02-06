---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: bacafee683fa47d7be331b4e44d2ab75be5bdb23
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603143"
---
# <span data-ttu-id="098a2-102">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="098a2-102">Enable-WSManCredSSP</span></span>

## <span data-ttu-id="098a2-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="098a2-103">SYNOPSIS</span></span>
<span data-ttu-id="098a2-104">Aktiviert die Authentifizierung der Credential Security Support Provider (kredssp) auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="098a2-104">Enables Credential Security Support Provider (CredSSP) authentication on a computer.</span></span>

## <span data-ttu-id="098a2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="098a2-105">SYNTAX</span></span>

### <span data-ttu-id="098a2-106">Alle</span><span class="sxs-lookup"><span data-stu-id="098a2-106">All</span></span>

```
Enable-WSManCredSSP [[-DelegateComputer] <String[]>] [-Force] [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="098a2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="098a2-107">DESCRIPTION</span></span>

<span data-ttu-id="098a2-108">Das- `Enable-WSManCredSSP` Cmdlet aktiviert die Authentifizierung auf einem Client oder auf einem Server Computer.</span><span class="sxs-lookup"><span data-stu-id="098a2-108">The `Enable-WSManCredSSP` cmdlet enables CredSSP authentication on a client or on a server computer.</span></span>
<span data-ttu-id="098a2-109">Wenn die Authentifizierung mit der Authentifizierung verwendet wird, werden die Anmelde Informationen des Benutzers an einen Remote Computer übergeben, der authentifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="098a2-109">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span> <span data-ttu-id="098a2-110">Diese Art der Authentifizierung ist für Befehle vorgesehen, die eine Remote Sitzung aus einer anderen Remote Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="098a2-110">This type of authentication is designed for commands that create a remote session from another remote session.</span></span> <span data-ttu-id="098a2-111">Wenn Sie z. b. einen Hintergrund Auftrag auf einem Remote Computer ausführen möchten, verwenden Sie diese Art der Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="098a2-111">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="098a2-112">`Enable-WSManCredSSP` kann "kredssp" auf einem **Client** oder einem **Server** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="098a2-112">`Enable-WSManCredSSP` can enable CredSSP on a **Client** or a **Server**.</span></span> <span data-ttu-id="098a2-113">Geben Sie zum Aktivieren von "kredssp" auf einem Client im **Role** -Parameter " **Client** " an.</span><span class="sxs-lookup"><span data-stu-id="098a2-113">To enable CredSSP on a client, specify **Client** in the **Role** parameter.</span></span> <span data-ttu-id="098a2-114">Clients delegieren explizite Anmelde Informationen an einen Server, wenn die Server Authentifizierung erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="098a2-114">Clients delegate explicit credentials to a server when server authentication is achieved.</span></span> <span data-ttu-id="098a2-115">Geben Sie im **Role** -Parameter " **Server** " an, um "up" auf einem Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="098a2-115">To enable CredSSP on a server, specify **Server** in the **Role** parameter.</span></span> <span data-ttu-id="098a2-116">Ein Server fungiert als Delegat für Clients.</span><span class="sxs-lookup"><span data-stu-id="098a2-116">A server acts as a delegate for clients.</span></span> <span data-ttu-id="098a2-117">Weitere Informationen finden Sie im Abschnitt zu den Parametern unter **Rolle** .</span><span class="sxs-lookup"><span data-stu-id="098a2-117">For more details, see **Role** in the Parameters section.</span></span>

> [!CAUTION]
> <span data-ttu-id="098a2-118">Bei der-Authentifizierung werden die Anmelde Informationen des Benutzers vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="098a2-118">CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="098a2-119">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="098a2-119">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="098a2-120">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="098a2-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="098a2-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="098a2-121">EXAMPLES</span></span>

### <span data-ttu-id="098a2-122">Beispiel 1: Delegieren von Client Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="098a2-122">Example 1: Delegate client credentials</span></span>

<span data-ttu-id="098a2-123">In diesem Beispiel können die Client Anmelde Informationen mithilfe des voll qualifizierten Domänen Namens an einen Computer delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="098a2-123">This example allows the client credentials to be delegated to a computer by using the fully qualified domain name.</span></span>

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "Server02.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### <span data-ttu-id="098a2-124">Beispiel 2: Delegieren von Client Anmelde Informationen an alle Computer in einer Domäne</span><span class="sxs-lookup"><span data-stu-id="098a2-124">Example 2: Delegate client credentials to all computers in a domain</span></span>

<span data-ttu-id="098a2-125">In diesem Beispiel können die Client Anmelde Informationen an alle Computer in der **Fabrikam.com** -Domäne delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="098a2-125">This example allows the client credentials to be delegated to all the computers in the **fabrikam.com** domain.</span></span> <span data-ttu-id="098a2-126">Das Sternchen ()-Platzhalter Zeichen `*` gibt alle Computer an.</span><span class="sxs-lookup"><span data-stu-id="098a2-126">The asterisk (`*`) wildcard specifies all computers.</span></span>

> [!NOTE]
> <span data-ttu-id="098a2-127">Durch die Verwendung von Platzhaltern mit dem Parameter " **delegatecomputer** " kann "kredssp" auf mehr Computern als notwendig aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="098a2-127">Using wildcards with the **DelegateComputer** parameter can enable CredSSP on more computers than necessary.</span></span>

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "*.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### <span data-ttu-id="098a2-128">Beispiel 3: Delegieren von Client Anmelde Informationen an mehrere Computer</span><span class="sxs-lookup"><span data-stu-id="098a2-128">Example 3: Delegate client credentials to multiple computers</span></span>

<span data-ttu-id="098a2-129">In diesem Beispiel können die Client Anmelde Informationen an mehrere Computer delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="098a2-129">This example allows the client credentials to be delegated to multiple computers.</span></span>

```powershell
$servers = "server02.fabrikam.com", "server03.fabrikam.com", "server04.fabrikam.com"
Enable-WSManCredSSP -Role "Client" -DelegateComputer $servers
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

<span data-ttu-id="098a2-130">Die- `$servers` Variable enthält eine Liste von Servernamen.</span><span class="sxs-lookup"><span data-stu-id="098a2-130">The `$servers` variable contains a list of server names.</span></span> <span data-ttu-id="098a2-131">`Enable-WSManCredSSP` verwendet den **Role** -Parameter, um die **Client** Rolle anzugeben.</span><span class="sxs-lookup"><span data-stu-id="098a2-131">`Enable-WSManCredSSP` uses the **Role** parameter to specify the **Client** role.</span></span> <span data-ttu-id="098a2-132">Der **delegatecomputer** Ruft die Computernamen aus der `$servers` Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="098a2-132">The **DelegateComputer** gets the computer names from the `$servers` variable.</span></span>

### <span data-ttu-id="098a2-133">Beispiel 4: zulassen, dass ein Computer als Delegat fungiert</span><span class="sxs-lookup"><span data-stu-id="098a2-133">Example 4: Allow a computer to act as a delegate</span></span>

<span data-ttu-id="098a2-134">In diesem Beispiel kann ein Computer als Delegat für einen anderen fungieren.</span><span class="sxs-lookup"><span data-stu-id="098a2-134">This example allows a computer to act as a delegate for another.</span></span> <span data-ttu-id="098a2-135">Das `Enable-WSManCredSSP` -Cmdlet, wie in den vorherigen Beispielen gezeigt, aktiviert nur die Authentifizierung auf dem Client und gibt die Remote Computer an, die in seinem Auftrag agieren können.</span><span class="sxs-lookup"><span data-stu-id="098a2-135">The `Enable-WSManCredSSP` cmdlet, shown in the earlier examples, only enables CredSSP authentication on the client, and specifies the remote computers that can act on its behalf.</span></span> <span data-ttu-id="098a2-136">Damit der Remote Computer als Delegat für den Client fungieren kann, muss das Element "kredssp" im **Dienst** Knoten von WSMan auf "true" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="098a2-136">In order for the remote computer to act as a delegate for the client, the CredSSP item in the **Service** node of WSMan must be set to true.</span></span> <span data-ttu-id="098a2-137">In diesem Beispiel wird das Element "kredssp" im **Dienst** Knoten von WSMan auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="098a2-137">This example sets the CredSSP item in the **Service** node of WSMan to true.</span></span>

```powershell
Enable-WSManCredSSP -Role "Server"
```

### <span data-ttu-id="098a2-138">Beispiel 5: zulassen, dass ein Computer mithilfe von Set-Item als Delegat fungiert</span><span class="sxs-lookup"><span data-stu-id="098a2-138">Example 5: Allow a computer to act as a delegate by using Set-Item</span></span>

<span data-ttu-id="098a2-139">In diesem Beispiel kann ein Computer als Delegat für einen anderen Computer fungieren.</span><span class="sxs-lookup"><span data-stu-id="098a2-139">This example allows a computer to act as a delegate for another computer.</span></span> <span data-ttu-id="098a2-140">Die `Enable-WSManCredSSP` in den vorherigen Beispielen gezeigten Befehle aktivieren die-Authentifizierung nur auf dem Client Computer und geben die Remote Computer an, die im Namen des Client Computers agieren können.</span><span class="sxs-lookup"><span data-stu-id="098a2-140">The `Enable-WSManCredSSP` commands, shown in the earlier examples, enable CredSSP authentication only on the client computer, and they specify the remote computers that can act on behalf of the client computer.</span></span> <span data-ttu-id="098a2-141">Damit der Remotecomputer als Delegat für den Clientcomputer fungieren kann, muss das CredSSP-Element im Dienstverzeichnis des WSMan-Anbieters auf „True“ festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="098a2-141">For the remote computer to act as a delegate for the client computer, the CredSSP item in the Service directory of the WSMan provider must be set to true.</span></span>

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

<span data-ttu-id="098a2-142">`Connect-WSMan` erstellt eine Verbindung mit dem Remote Computer Server02.</span><span class="sxs-lookup"><span data-stu-id="098a2-142">`Connect-WSMan` creates a connection to the remote computer, server02.</span></span> <span data-ttu-id="098a2-143">`Set-Item` verwendet den **path** -Parameter, um den Speicherort des **WSMAN** -Anbieters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="098a2-143">`Set-Item` uses the **Path** parameter to specify the **WSMan** provider's location.</span></span> <span data-ttu-id="098a2-144">Mit dem **value** -Parameter wird die **Dienst** Einstellung auf true festgelegt.</span><span class="sxs-lookup"><span data-stu-id="098a2-144">The **Value** parameter sets the **Service** setting to true.</span></span>

## <span data-ttu-id="098a2-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="098a2-145">PARAMETERS</span></span>

### <span data-ttu-id="098a2-146">-Delegatecomputer</span><span class="sxs-lookup"><span data-stu-id="098a2-146">-DelegateComputer</span></span>

<span data-ttu-id="098a2-147">Gibt Server an, an die Client Anmelde Informationen delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="098a2-147">Specifies servers to which client credentials are delegated.</span></span> <span data-ttu-id="098a2-148">Die bewährte Vorgehensweise besteht darin, vollständig qualifizierte Domänen Namen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="098a2-148">The best practice is to use fully qualified domain names.</span></span>

<span data-ttu-id="098a2-149">Platzhalter werden akzeptiert, können aber auch auf mehr Computern als notwendig aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="098a2-149">Wildcards are accepted, but can enable CredSSP on more computers than necessary.</span></span>

<span data-ttu-id="098a2-150">Wenn der **Role** -Parameter " **Client**" ist, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="098a2-150">If the **Role** parameter is **Client**, you must specify this parameter.</span></span> <span data-ttu-id="098a2-151">Wenn **Role** **Server** ist, geben Sie diesen Parameter nicht an.</span><span class="sxs-lookup"><span data-stu-id="098a2-151">If **Role** is **Server**, don't specify this parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="098a2-152">-Force</span><span class="sxs-lookup"><span data-stu-id="098a2-152">-Force</span></span>

<span data-ttu-id="098a2-153">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="098a2-153">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="098a2-154">-Rolle</span><span class="sxs-lookup"><span data-stu-id="098a2-154">-Role</span></span>

<span data-ttu-id="098a2-155">Gibt an, ob "kredssp" als Client oder als Server aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="098a2-155">Specifies whether to enable CredSSP as a client or as a server.</span></span> <span data-ttu-id="098a2-156">Die zulässigen Werte für diesen Parameter sind: **Client** und **Server**.</span><span class="sxs-lookup"><span data-stu-id="098a2-156">The acceptable values for this parameter are: **Client** and **Server**.</span></span>

<span data-ttu-id="098a2-157">Wenn Sie den- **Client** angeben, werden die folgenden Aktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="098a2-157">If you specify **Client**, the following actions are performed.</span></span> <span data-ttu-id="098a2-158">Diese Einstellungen ermöglichen es dem Client, nach erfolgreicher Serverauthentifizierung explizite Anmeldeinformationen an einen Server zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="098a2-158">These settings allow the client to delegate explicit credentials to a server when server authentication is achieved.</span></span>

- <span data-ttu-id="098a2-159">Aktiviert "kredssp" auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="098a2-159">Enables CredSSP on the client.</span></span>
- <span data-ttu-id="098a2-160">Legt die WS-Management Einstellung `\<localhost|computername\>\Client\Auth\CredSSP` auf "true" fest.</span><span class="sxs-lookup"><span data-stu-id="098a2-160">Sets the WS-Management setting `\<localhost|computername\>\Client\Auth\CredSSP` to true.</span></span>
- <span data-ttu-id="098a2-161">Legt die Windows-kredssp-Richtlinie **allowfreshanmelde** Informationen auf dem Client auf **WSMAN/** Delegat fest.</span><span class="sxs-lookup"><span data-stu-id="098a2-161">Sets the Windows CredSSP policy **AllowFreshCredentials** to **WSMan/Delegate** on the client.</span></span>

<span data-ttu-id="098a2-162">Wenn Sie den **Server** angeben, werden die folgenden Aktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="098a2-162">If you specify **Server**, the following actions are performed.</span></span> <span data-ttu-id="098a2-163">Durch diese Richtlinieneinstellung kann der Server als Delegat für Clients fungieren.</span><span class="sxs-lookup"><span data-stu-id="098a2-163">This policy setting allows the server to act as a delegate for clients.</span></span>

- <span data-ttu-id="098a2-164">Aktiviert die auf dem Server erstellten kredssp.</span><span class="sxs-lookup"><span data-stu-id="098a2-164">Enables CredSSP on the server.</span></span>
- <span data-ttu-id="098a2-165">Legt die WS-Management Einstellung `\<localhost|computername\>\Service\Auth\CredSSP` auf "true" fest.</span><span class="sxs-lookup"><span data-stu-id="098a2-165">Sets the WS-Management setting `\<localhost|computername\>\Service\Auth\CredSSP` to true.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="098a2-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="098a2-166">CommonParameters</span></span>

<span data-ttu-id="098a2-167">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="098a2-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="098a2-168">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="098a2-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="098a2-169">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="098a2-169">INPUTS</span></span>

### <span data-ttu-id="098a2-170">Keine</span><span class="sxs-lookup"><span data-stu-id="098a2-170">None</span></span>

<span data-ttu-id="098a2-171">Dieses Cmdlet akzeptiert keine Eingaben.</span><span class="sxs-lookup"><span data-stu-id="098a2-171">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="098a2-172">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="098a2-172">OUTPUTS</span></span>

### <span data-ttu-id="098a2-173">System.Xml.Xml-Element</span><span class="sxs-lookup"><span data-stu-id="098a2-173">System.Xml.XmlElement</span></span>

<span data-ttu-id="098a2-174">Wenn die kredssp-Authentifizierung erfolgreich aktiviert wurde, generiert dieses Cmdlet ein **XmlElement** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="098a2-174">If CredSSP authentication is successfully enabled, this cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="098a2-175">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="098a2-175">NOTES</span></span>

<span data-ttu-id="098a2-176">Verwenden Sie zum Deaktivieren der dedssp-Authentifizierung das `Disable-WSManCredSSP` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="098a2-176">To disable CredSSP authentication, use the `Disable-WSManCredSSP` cmdlet.</span></span>

## <span data-ttu-id="098a2-177">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="098a2-177">RELATED LINKS</span></span>

[<span data-ttu-id="098a2-178">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="098a2-178">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="098a2-179">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="098a2-179">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="098a2-180">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="098a2-180">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="098a2-181">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="098a2-181">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="098a2-182">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="098a2-182">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="098a2-183">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="098a2-183">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="098a2-184">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="098a2-184">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="098a2-185">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="098a2-185">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="098a2-186">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="098a2-186">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="098a2-187">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="098a2-187">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="098a2-188">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="098a2-188">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="098a2-189">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="098a2-189">Test-WSMan</span></span>](Test-WSMan.md)

