---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: 0b4ec4902df2b2e93def549586e3f6cde70fadee
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218383"
---
# <span data-ttu-id="fb67a-103">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fb67a-103">Enable-WSManCredSSP</span></span>

## <span data-ttu-id="fb67a-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fb67a-104">SYNOPSIS</span></span>
<span data-ttu-id="fb67a-105">Aktiviert die Authentifizierung der Credential Security Support Provider (kredssp) auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="fb67a-105">Enables Credential Security Support Provider (CredSSP) authentication on a computer.</span></span>

## <span data-ttu-id="fb67a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fb67a-106">SYNTAX</span></span>

### <span data-ttu-id="fb67a-107">Alle</span><span class="sxs-lookup"><span data-stu-id="fb67a-107">All</span></span>

```
Enable-WSManCredSSP [-Role] <String> [[-DelegateComputer] <String[]>] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="fb67a-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fb67a-108">DESCRIPTION</span></span>

<span data-ttu-id="fb67a-109">Das- `Enable-WSManCredSSP` Cmdlet aktiviert die Authentifizierung auf einem Client oder auf einem Server Computer.</span><span class="sxs-lookup"><span data-stu-id="fb67a-109">The `Enable-WSManCredSSP` cmdlet enables CredSSP authentication on a client or on a server computer.</span></span>
<span data-ttu-id="fb67a-110">Wenn die Authentifizierung mit der Authentifizierung verwendet wird, werden die Anmelde Informationen des Benutzers an einen Remote Computer übergeben, der authentifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb67a-110">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span> <span data-ttu-id="fb67a-111">Diese Art der Authentifizierung ist für Befehle vorgesehen, die eine Remote Sitzung aus einer anderen Remote Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb67a-111">This type of authentication is designed for commands that create a remote session from another remote session.</span></span> <span data-ttu-id="fb67a-112">Wenn Sie z. b. einen Hintergrund Auftrag auf einem Remote Computer ausführen möchten, verwenden Sie diese Art der Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fb67a-112">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="fb67a-113">`Enable-WSManCredSSP` kann "kredssp" auf einem **Client** oder einem **Server** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb67a-113">`Enable-WSManCredSSP` can enable CredSSP on a **Client** or a **Server**.</span></span> <span data-ttu-id="fb67a-114">Geben Sie zum Aktivieren von "kredssp" auf einem Client im **Role** -Parameter " **Client** " an.</span><span class="sxs-lookup"><span data-stu-id="fb67a-114">To enable CredSSP on a client, specify **Client** in the **Role** parameter.</span></span> <span data-ttu-id="fb67a-115">Clients delegieren explizite Anmelde Informationen an einen Server, wenn die Server Authentifizierung erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="fb67a-115">Clients delegate explicit credentials to a server when server authentication is achieved.</span></span> <span data-ttu-id="fb67a-116">Geben Sie im **Role** -Parameter " **Server** " an, um "up" auf einem Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb67a-116">To enable CredSSP on a server, specify **Server** in the **Role** parameter.</span></span> <span data-ttu-id="fb67a-117">Ein Server fungiert als Delegat für Clients.</span><span class="sxs-lookup"><span data-stu-id="fb67a-117">A server acts as a delegate for clients.</span></span> <span data-ttu-id="fb67a-118">Weitere Informationen finden Sie im Abschnitt zu den Parametern unter **Rolle** .</span><span class="sxs-lookup"><span data-stu-id="fb67a-118">For more details, see **Role** in the Parameters section.</span></span>

> [!CAUTION]
> <span data-ttu-id="fb67a-119">Bei der-Authentifizierung werden die Anmelde Informationen des Benutzers vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="fb67a-119">CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span> <span data-ttu-id="fb67a-120">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="fb67a-120">This practice increases the security risk of the remote operation.</span></span> <span data-ttu-id="fb67a-121">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-121">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="fb67a-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fb67a-122">EXAMPLES</span></span>

### <span data-ttu-id="fb67a-123">Beispiel 1: Delegieren von Client Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="fb67a-123">Example 1: Delegate client credentials</span></span>

<span data-ttu-id="fb67a-124">In diesem Beispiel können die Client Anmelde Informationen mithilfe des voll qualifizierten Domänen Namens an einen Computer delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-124">This example allows the client credentials to be delegated to a computer by using the fully qualified domain name.</span></span>

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

### <span data-ttu-id="fb67a-125">Beispiel 2: Delegieren von Client Anmelde Informationen an alle Computer in einer Domäne</span><span class="sxs-lookup"><span data-stu-id="fb67a-125">Example 2: Delegate client credentials to all computers in a domain</span></span>

<span data-ttu-id="fb67a-126">In diesem Beispiel können die Client Anmelde Informationen an alle Computer in der **Fabrikam.com** -Domäne delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-126">This example allows the client credentials to be delegated to all the computers in the **fabrikam.com** domain.</span></span> <span data-ttu-id="fb67a-127">Das Sternchen ()-Platzhalter Zeichen `*` gibt alle Computer an.</span><span class="sxs-lookup"><span data-stu-id="fb67a-127">The asterisk (`*`) wildcard specifies all computers.</span></span>

> [!NOTE]
> <span data-ttu-id="fb67a-128">Durch die Verwendung von Platzhaltern mit dem Parameter " **delegatecomputer** " kann "kredssp" auf mehr Computern als notwendig aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-128">Using wildcards with the **DelegateComputer** parameter can enable CredSSP on more computers than necessary.</span></span>

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

### <span data-ttu-id="fb67a-129">Beispiel 3: Delegieren von Client Anmelde Informationen an mehrere Computer</span><span class="sxs-lookup"><span data-stu-id="fb67a-129">Example 3: Delegate client credentials to multiple computers</span></span>

<span data-ttu-id="fb67a-130">In diesem Beispiel können die Client Anmelde Informationen an mehrere Computer delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-130">This example allows the client credentials to be delegated to multiple computers.</span></span>

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

<span data-ttu-id="fb67a-131">Die- `$servers` Variable enthält eine Liste von Servernamen.</span><span class="sxs-lookup"><span data-stu-id="fb67a-131">The `$servers` variable contains a list of server names.</span></span> <span data-ttu-id="fb67a-132">`Enable-WSManCredSSP` verwendet den **Role** -Parameter, um die **Client** Rolle anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb67a-132">`Enable-WSManCredSSP` uses the **Role** parameter to specify the **Client** role.</span></span> <span data-ttu-id="fb67a-133">Der **delegatecomputer** Ruft die Computernamen aus der `$servers` Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="fb67a-133">The **DelegateComputer** gets the computer names from the `$servers` variable.</span></span>

### <span data-ttu-id="fb67a-134">Beispiel 4: zulassen, dass ein Computer als Delegat fungiert</span><span class="sxs-lookup"><span data-stu-id="fb67a-134">Example 4: Allow a computer to act as a delegate</span></span>

<span data-ttu-id="fb67a-135">In diesem Beispiel kann ein Computer als Delegat für einen anderen fungieren.</span><span class="sxs-lookup"><span data-stu-id="fb67a-135">This example allows a computer to act as a delegate for another.</span></span> <span data-ttu-id="fb67a-136">Das `Enable-WSManCredSSP` -Cmdlet, wie in den vorherigen Beispielen gezeigt, aktiviert nur die Authentifizierung auf dem Client und gibt die Remote Computer an, die in seinem Auftrag agieren können.</span><span class="sxs-lookup"><span data-stu-id="fb67a-136">The `Enable-WSManCredSSP` cmdlet, shown in the earlier examples, only enables CredSSP authentication on the client, and specifies the remote computers that can act on its behalf.</span></span> <span data-ttu-id="fb67a-137">Damit der Remote Computer als Delegat für den Client fungieren kann, muss das Element "kredssp" im **Dienst** Knoten von WSMan auf "true" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-137">In order for the remote computer to act as a delegate for the client, the CredSSP item in the **Service** node of WSMan must be set to true.</span></span> <span data-ttu-id="fb67a-138">In diesem Beispiel wird das Element "kredssp" im **Dienst** Knoten von WSMan auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fb67a-138">This example sets the CredSSP item in the **Service** node of WSMan to true.</span></span>

```powershell
Enable-WSManCredSSP -Role "Server"
```

### <span data-ttu-id="fb67a-139">Beispiel 5: zulassen, dass ein Computer mithilfe von Set-Item als Delegat fungiert</span><span class="sxs-lookup"><span data-stu-id="fb67a-139">Example 5: Allow a computer to act as a delegate by using Set-Item</span></span>

<span data-ttu-id="fb67a-140">In diesem Beispiel kann ein Computer als Delegat für einen anderen Computer fungieren.</span><span class="sxs-lookup"><span data-stu-id="fb67a-140">This example allows a computer to act as a delegate for another computer.</span></span> <span data-ttu-id="fb67a-141">Die `Enable-WSManCredSSP` in den vorherigen Beispielen gezeigten Befehle aktivieren die-Authentifizierung nur auf dem Client Computer und geben die Remote Computer an, die im Namen des Client Computers agieren können.</span><span class="sxs-lookup"><span data-stu-id="fb67a-141">The `Enable-WSManCredSSP` commands, shown in the earlier examples, enable CredSSP authentication only on the client computer, and they specify the remote computers that can act on behalf of the client computer.</span></span> <span data-ttu-id="fb67a-142">Damit der Remotecomputer als Delegat für den Clientcomputer fungieren kann, muss das CredSSP-Element im Dienstverzeichnis des WSMan-Anbieters auf „True“ festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-142">For the remote computer to act as a delegate for the client computer, the CredSSP item in the Service directory of the WSMan provider must be set to true.</span></span>

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

<span data-ttu-id="fb67a-143">`Connect-WSMan` erstellt eine Verbindung mit dem Remote Computer Server02.</span><span class="sxs-lookup"><span data-stu-id="fb67a-143">`Connect-WSMan` creates a connection to the remote computer, server02.</span></span> <span data-ttu-id="fb67a-144">`Set-Item` verwendet den **path** -Parameter, um den Speicherort des **WSMAN** -Anbieters anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb67a-144">`Set-Item` uses the **Path** parameter to specify the **WSMan** provider's location.</span></span> <span data-ttu-id="fb67a-145">Mit dem **value** -Parameter wird die **Dienst** Einstellung auf true festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fb67a-145">The **Value** parameter sets the **Service** setting to true.</span></span>

## <span data-ttu-id="fb67a-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fb67a-146">PARAMETERS</span></span>

### <span data-ttu-id="fb67a-147">-Delegatecomputer</span><span class="sxs-lookup"><span data-stu-id="fb67a-147">-DelegateComputer</span></span>

<span data-ttu-id="fb67a-148">Gibt Server an, an die Client Anmelde Informationen delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-148">Specifies servers to which client credentials are delegated.</span></span> <span data-ttu-id="fb67a-149">Die bewährte Vorgehensweise besteht darin, vollständig qualifizierte Domänen Namen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-149">The best practice is to use fully qualified domain names.</span></span>

<span data-ttu-id="fb67a-150">Platzhalter werden akzeptiert, können aber auch auf mehr Computern als notwendig aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="fb67a-150">Wildcards are accepted, but can enable CredSSP on more computers than necessary.</span></span>

<span data-ttu-id="fb67a-151">Wenn der **Role** -Parameter " **Client** " ist, müssen Sie diesen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="fb67a-151">If the **Role** parameter is **Client** , you must specify this parameter.</span></span> <span data-ttu-id="fb67a-152">Wenn **Role** **Server** ist, geben Sie diesen Parameter nicht an.</span><span class="sxs-lookup"><span data-stu-id="fb67a-152">If **Role** is **Server** , don't specify this parameter.</span></span>

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

### <span data-ttu-id="fb67a-153">-Force</span><span class="sxs-lookup"><span data-stu-id="fb67a-153">-Force</span></span>

<span data-ttu-id="fb67a-154">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fb67a-154">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="fb67a-155">-Rolle</span><span class="sxs-lookup"><span data-stu-id="fb67a-155">-Role</span></span>

<span data-ttu-id="fb67a-156">Gibt an, ob "kredssp" als Client oder als Server aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb67a-156">Specifies whether to enable CredSSP as a client or as a server.</span></span> <span data-ttu-id="fb67a-157">Die zulässigen Werte für diesen Parameter sind: **Client** und **Server**.</span><span class="sxs-lookup"><span data-stu-id="fb67a-157">The acceptable values for this parameter are: **Client** and **Server**.</span></span>

<span data-ttu-id="fb67a-158">Wenn Sie den- **Client** angeben, werden die folgenden Aktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb67a-158">If you specify **Client** , the following actions are performed.</span></span> <span data-ttu-id="fb67a-159">Diese Einstellungen ermöglichen es dem Client, nach erfolgreicher Serverauthentifizierung explizite Anmeldeinformationen an einen Server zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="fb67a-159">These settings allow the client to delegate explicit credentials to a server when server authentication is achieved.</span></span>

- <span data-ttu-id="fb67a-160">Aktiviert "kredssp" auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="fb67a-160">Enables CredSSP on the client.</span></span>
- <span data-ttu-id="fb67a-161">Legt die WS-Management Einstellung `\<localhost|computername\>\Client\Auth\CredSSP` auf "true" fest.</span><span class="sxs-lookup"><span data-stu-id="fb67a-161">Sets the WS-Management setting `\<localhost|computername\>\Client\Auth\CredSSP` to true.</span></span>
- <span data-ttu-id="fb67a-162">Legt die Windows-kredssp-Richtlinie **allowfreshanmelde** Informationen auf dem Client auf **WSMAN/** Delegat fest.</span><span class="sxs-lookup"><span data-stu-id="fb67a-162">Sets the Windows CredSSP policy **AllowFreshCredentials** to **WSMan/Delegate** on the client.</span></span>

<span data-ttu-id="fb67a-163">Wenn Sie den **Server** angeben, werden die folgenden Aktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fb67a-163">If you specify **Server** , the following actions are performed.</span></span> <span data-ttu-id="fb67a-164">Durch diese Richtlinieneinstellung kann der Server als Delegat für Clients fungieren.</span><span class="sxs-lookup"><span data-stu-id="fb67a-164">This policy setting allows the server to act as a delegate for clients.</span></span>

- <span data-ttu-id="fb67a-165">Aktiviert die auf dem Server erstellten kredssp.</span><span class="sxs-lookup"><span data-stu-id="fb67a-165">Enables CredSSP on the server.</span></span>
- <span data-ttu-id="fb67a-166">Legt die WS-Management Einstellung `\<localhost|computername\>\Service\Auth\CredSSP` auf "true" fest.</span><span class="sxs-lookup"><span data-stu-id="fb67a-166">Sets the WS-Management setting `\<localhost|computername\>\Service\Auth\CredSSP` to true.</span></span>

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

### <span data-ttu-id="fb67a-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fb67a-167">CommonParameters</span></span>

<span data-ttu-id="fb67a-168">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fb67a-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fb67a-169">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fb67a-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fb67a-170">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fb67a-170">INPUTS</span></span>

### <span data-ttu-id="fb67a-171">Keine</span><span class="sxs-lookup"><span data-stu-id="fb67a-171">None</span></span>

<span data-ttu-id="fb67a-172">Dieses Cmdlet akzeptiert keine Eingaben.</span><span class="sxs-lookup"><span data-stu-id="fb67a-172">This cmdlet doesn't accept any input.</span></span>

## <span data-ttu-id="fb67a-173">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fb67a-173">OUTPUTS</span></span>

### <span data-ttu-id="fb67a-174">System.Xml.Xml-Element</span><span class="sxs-lookup"><span data-stu-id="fb67a-174">System.Xml.XmlElement</span></span>

<span data-ttu-id="fb67a-175">Wenn die kredssp-Authentifizierung erfolgreich aktiviert wurde, generiert dieses Cmdlet ein **XmlElement** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="fb67a-175">If CredSSP authentication is successfully enabled, this cmdlet generates an **XMLElement** object.</span></span>

## <span data-ttu-id="fb67a-176">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fb67a-176">NOTES</span></span>

<span data-ttu-id="fb67a-177">Verwenden Sie zum Deaktivieren der dedssp-Authentifizierung das `Disable-WSManCredSSP` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fb67a-177">To disable CredSSP authentication, use the `Disable-WSManCredSSP` cmdlet.</span></span>

## <span data-ttu-id="fb67a-178">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fb67a-178">RELATED LINKS</span></span>

[<span data-ttu-id="fb67a-179">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="fb67a-179">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="fb67a-180">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fb67a-180">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="fb67a-181">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="fb67a-181">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="fb67a-182">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="fb67a-182">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="fb67a-183">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fb67a-183">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="fb67a-184">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="fb67a-184">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="fb67a-185">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fb67a-185">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="fb67a-186">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="fb67a-186">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="fb67a-187">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fb67a-187">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="fb67a-188">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="fb67a-188">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="fb67a-189">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="fb67a-189">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="fb67a-190">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="fb67a-190">Test-WSMan</span></span>](Test-WSMan.md)
