---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: 6b6cf6b4056dd5907f6a43cd9cf6d491bc7512b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212540"
---
# <span data-ttu-id="8644e-103">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="8644e-103">Disable-WSManCredSSP</span></span>

## <span data-ttu-id="8644e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8644e-104">SYNOPSIS</span></span>
<span data-ttu-id="8644e-105">Deaktiviert die kredssp-Authentifizierung auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="8644e-105">Disables CredSSP authentication on a computer.</span></span>

## <span data-ttu-id="8644e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8644e-106">SYNTAX</span></span>

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="8644e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8644e-107">DESCRIPTION</span></span>
<span data-ttu-id="8644e-108">Das Cmdlet " **Disab-wsmankredssp** " deaktiviert die Authentifizierung der Credential Security Support Provider-Authentifizierung (-Authentifizierung) auf einem Client oder auf einem Server Computer.</span><span class="sxs-lookup"><span data-stu-id="8644e-108">The **Disable-WSManCredSSP** cmdlet disables Credential Security Support Provider (CredSSP) authentication on a client or on a server computer.</span></span>
<span data-ttu-id="8644e-109">Wenn die Authentifizierung mit der Authentifizierung verwendet wird, werden die Anmelde Informationen des Benutzers an einen Remote Computer übergeben, der authentifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8644e-109">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span>

<span data-ttu-id="8644e-110">Verwenden Sie dieses Cmdlet zum Deaktivieren von "dedssp" auf dem Client, indem Sie im *Role* -Parameter "Client" angeben.</span><span class="sxs-lookup"><span data-stu-id="8644e-110">Use this cmdlet to disable CredSSP on the client by specifying Client in the *Role* parameter.</span></span>
<span data-ttu-id="8644e-111">Dieses Cmdlet führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="8644e-111">This cmdlet performs the following actions:</span></span>

- <span data-ttu-id="8644e-112">Deaktiviert "kredssp" auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="8644e-112">Disables CredSSP on the client.</span></span> <span data-ttu-id="8644e-113">Mit diesem Cmdlet wird die WS-Management Einstellung **\<localhost|computername\> \client\auth\kredssp** auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8644e-113">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="8644e-114">Entfernt alle WSMAN/\*-Einstellungen aus der Windows-kredssp-Richtlinie **allowfreshanmelde** Informationen auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="8644e-114">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="8644e-115">Verwenden Sie dieses Cmdlet zum Deaktivieren von "dedssp" auf dem Server, indem Sie den Server in der *Rolle* angeben.</span><span class="sxs-lookup"><span data-stu-id="8644e-115">Use this cmdlet to disable CredSSP on the server by specifying Server in *Role* .</span></span>
<span data-ttu-id="8644e-116">Dieses Cmdlet führt die folgende Aktion aus:</span><span class="sxs-lookup"><span data-stu-id="8644e-116">This cmdlet performs the following action:</span></span>

- <span data-ttu-id="8644e-117">Deaktiviert "kredssp" auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="8644e-117">Disables CredSSP on the server.</span></span> <span data-ttu-id="8644e-118">Mit diesem Cmdlet wird die WS-Management Einstellung **\<localhost|computername\> \service\auth\kredssp** auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8644e-118">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

<span data-ttu-id="8644e-119">Vorsicht: die Benutzer Anmelde Informationen werden von der kredssp-Authentifizierung vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="8644e-119">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="8644e-120">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="8644e-120">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="8644e-121">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8644e-121">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="8644e-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8644e-122">EXAMPLES</span></span>

### <span data-ttu-id="8644e-123">Beispiel 1: Deaktivieren von "kredssp" auf einem Client</span><span class="sxs-lookup"><span data-stu-id="8644e-123">Example 1: Disable CredSSP on a client</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Client
```

<span data-ttu-id="8644e-124">Dieser Befehl deaktiviert CredSSP auf dem Client, wodurch die Delegierung an Server verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="8644e-124">This command disables CredSSP on the client, which prevents delegation to servers.</span></span>

### <span data-ttu-id="8644e-125">Beispiel 2: Deaktivieren von "kredssp" auf einem Server</span><span class="sxs-lookup"><span data-stu-id="8644e-125">Example 2: Disable CredSSP on a server</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Server
```

<span data-ttu-id="8644e-126">Dieser Befehl deaktiviert CredSSP auf dem Server, wodurch die Delegierung von Clients verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="8644e-126">This command disables CredSSP on the server, which prevents delegation from clients.</span></span>

## <span data-ttu-id="8644e-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8644e-127">PARAMETERS</span></span>

### <span data-ttu-id="8644e-128">-Rolle</span><span class="sxs-lookup"><span data-stu-id="8644e-128">-Role</span></span>
<span data-ttu-id="8644e-129">Gibt an, ob "kredssp" als Client oder als Server deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8644e-129">Specifies whether to disable CredSSP as a client or as a server.</span></span>
<span data-ttu-id="8644e-130">Die zulässigen Werte für diesen Parameter sind: Client und Server.</span><span class="sxs-lookup"><span data-stu-id="8644e-130">The acceptable values for this parameter are: Client and Server.</span></span>

<span data-ttu-id="8644e-131">Wenn Sie den-Client angeben, führt dieses Cmdlet die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="8644e-131">If you specify Client, this cmdlet performs the following actions:</span></span>

- <span data-ttu-id="8644e-132">Deaktiviert "kredssp" auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="8644e-132">Disables CredSSP on the client.</span></span> <span data-ttu-id="8644e-133">Dieses Cmdlet legt WS-Management Einstellung **\<localhost|computername\> \client\auth\kredssp** auf false fest.</span><span class="sxs-lookup"><span data-stu-id="8644e-133">This cmdlet sets WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="8644e-134">Entfernt alle WSMAN/\*-Einstellungen aus der Windows-kredssp-Richtlinie **allowfreshanmelde** Informationen auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="8644e-134">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="8644e-135">Wenn Sie den Server angeben, führt dieses Cmdlet die folgende Aktion aus:</span><span class="sxs-lookup"><span data-stu-id="8644e-135">If you specify Server, this cmdlet performs the following action:</span></span>

- <span data-ttu-id="8644e-136">Deaktiviert "kredssp" auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="8644e-136">Disables CredSSP on the server.</span></span> <span data-ttu-id="8644e-137">Mit diesem Cmdlet wird die WS-Management Einstellung **\<localhost|computername\> \service\auth\kredssp** auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8644e-137">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

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

### <span data-ttu-id="8644e-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8644e-138">CommonParameters</span></span>
<span data-ttu-id="8644e-139">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8644e-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8644e-140">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8644e-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8644e-141">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8644e-141">INPUTS</span></span>

### <span data-ttu-id="8644e-142">Keine</span><span class="sxs-lookup"><span data-stu-id="8644e-142">None</span></span>
<span data-ttu-id="8644e-143">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="8644e-143">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="8644e-144">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8644e-144">OUTPUTS</span></span>

### <span data-ttu-id="8644e-145">Keine</span><span class="sxs-lookup"><span data-stu-id="8644e-145">None</span></span>
<span data-ttu-id="8644e-146">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="8644e-146">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="8644e-147">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8644e-147">NOTES</span></span>

* <span data-ttu-id="8644e-148">Um die CredSSP-Authentifizierung zu aktivieren, verwenden Sie das Enable-WSManCredSSP-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8644e-148">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

*

## <span data-ttu-id="8644e-149">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8644e-149">RELATED LINKS</span></span>

[<span data-ttu-id="8644e-150">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="8644e-150">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="8644e-151">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="8644e-151">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="8644e-152">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="8644e-152">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="8644e-153">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="8644e-153">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="8644e-154">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8644e-154">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="8644e-155">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="8644e-155">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="8644e-156">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8644e-156">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="8644e-157">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="8644e-157">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="8644e-158">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8644e-158">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="8644e-159">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="8644e-159">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="8644e-160">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="8644e-160">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="8644e-161">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="8644e-161">Test-WSMan</span></span>](Test-WSMan.md)
