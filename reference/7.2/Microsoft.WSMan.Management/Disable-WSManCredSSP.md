---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: 3260c88d57e98c0072af8621600a02901c561acb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596558"
---
# <span data-ttu-id="d9b94-102">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="d9b94-102">Disable-WSManCredSSP</span></span>

## <span data-ttu-id="d9b94-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d9b94-103">SYNOPSIS</span></span>
<span data-ttu-id="d9b94-104">Deaktiviert die kredssp-Authentifizierung auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="d9b94-104">Disables CredSSP authentication on a computer.</span></span>

## <span data-ttu-id="d9b94-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d9b94-105">SYNTAX</span></span>

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## <span data-ttu-id="d9b94-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d9b94-106">DESCRIPTION</span></span>
<span data-ttu-id="d9b94-107">Das Cmdlet " **Disab-wsmankredssp** " deaktiviert die Authentifizierung der Credential Security Support Provider-Authentifizierung (-Authentifizierung) auf einem Client oder auf einem Server Computer.</span><span class="sxs-lookup"><span data-stu-id="d9b94-107">The **Disable-WSManCredSSP** cmdlet disables Credential Security Support Provider (CredSSP) authentication on a client or on a server computer.</span></span>
<span data-ttu-id="d9b94-108">Wenn die Authentifizierung mit der Authentifizierung verwendet wird, werden die Anmelde Informationen des Benutzers an einen Remote Computer übergeben, der authentifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9b94-108">When CredSSP authentication is used, the user credentials are passed to a remote computer to be authenticated.</span></span>

<span data-ttu-id="d9b94-109">Verwenden Sie dieses Cmdlet zum Deaktivieren von "dedssp" auf dem Client, indem Sie im *Role* -Parameter "Client" angeben.</span><span class="sxs-lookup"><span data-stu-id="d9b94-109">Use this cmdlet to disable CredSSP on the client by specifying Client in the *Role* parameter.</span></span>
<span data-ttu-id="d9b94-110">Dieses Cmdlet führt die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="d9b94-110">This cmdlet performs the following actions:</span></span>

- <span data-ttu-id="d9b94-111">Deaktiviert "kredssp" auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="d9b94-111">Disables CredSSP on the client.</span></span> <span data-ttu-id="d9b94-112">Mit diesem Cmdlet wird die WS-Management Einstellung **\<localhost|computername\> \client\auth\kredssp** auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9b94-112">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="d9b94-113">Entfernt alle WSMAN/\*-Einstellungen aus der Windows-kredssp-Richtlinie **allowfreshanmelde** Informationen auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="d9b94-113">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="d9b94-114">Verwenden Sie dieses Cmdlet zum Deaktivieren von "dedssp" auf dem Server, indem Sie den Server in der *Rolle* angeben.</span><span class="sxs-lookup"><span data-stu-id="d9b94-114">Use this cmdlet to disable CredSSP on the server by specifying Server in *Role*.</span></span>
<span data-ttu-id="d9b94-115">Dieses Cmdlet führt die folgende Aktion aus:</span><span class="sxs-lookup"><span data-stu-id="d9b94-115">This cmdlet performs the following action:</span></span>

- <span data-ttu-id="d9b94-116">Deaktiviert "kredssp" auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="d9b94-116">Disables CredSSP on the server.</span></span> <span data-ttu-id="d9b94-117">Mit diesem Cmdlet wird die WS-Management Einstellung **\<localhost|computername\> \service\auth\kredssp** auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9b94-117">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

<span data-ttu-id="d9b94-118">Vorsicht: die Benutzer Anmelde Informationen werden von der kredssp-Authentifizierung vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="d9b94-118">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="d9b94-119">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="d9b94-119">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="d9b94-120">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9b94-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="d9b94-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d9b94-121">EXAMPLES</span></span>

### <span data-ttu-id="d9b94-122">Beispiel 1: Deaktivieren von "kredssp" auf einem Client</span><span class="sxs-lookup"><span data-stu-id="d9b94-122">Example 1: Disable CredSSP on a client</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Client
```

<span data-ttu-id="d9b94-123">Dieser Befehl deaktiviert CredSSP auf dem Client, wodurch die Delegierung an Server verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="d9b94-123">This command disables CredSSP on the client, which prevents delegation to servers.</span></span>

### <span data-ttu-id="d9b94-124">Beispiel 2: Deaktivieren von "kredssp" auf einem Server</span><span class="sxs-lookup"><span data-stu-id="d9b94-124">Example 2: Disable CredSSP on a server</span></span>

```
PS C:\> Disable-WSManCredSSP -Role Server
```

<span data-ttu-id="d9b94-125">Dieser Befehl deaktiviert CredSSP auf dem Server, wodurch die Delegierung von Clients verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="d9b94-125">This command disables CredSSP on the server, which prevents delegation from clients.</span></span>

## <span data-ttu-id="d9b94-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d9b94-126">PARAMETERS</span></span>

### <span data-ttu-id="d9b94-127">-Rolle</span><span class="sxs-lookup"><span data-stu-id="d9b94-127">-Role</span></span>
<span data-ttu-id="d9b94-128">Gibt an, ob "kredssp" als Client oder als Server deaktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9b94-128">Specifies whether to disable CredSSP as a client or as a server.</span></span>
<span data-ttu-id="d9b94-129">Die zulässigen Werte für diesen Parameter sind: Client und Server.</span><span class="sxs-lookup"><span data-stu-id="d9b94-129">The acceptable values for this parameter are: Client and Server.</span></span>

<span data-ttu-id="d9b94-130">Wenn Sie den-Client angeben, führt dieses Cmdlet die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="d9b94-130">If you specify Client, this cmdlet performs the following actions:</span></span>

- <span data-ttu-id="d9b94-131">Deaktiviert "kredssp" auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="d9b94-131">Disables CredSSP on the client.</span></span> <span data-ttu-id="d9b94-132">Dieses Cmdlet legt WS-Management Einstellung **\<localhost|computername\> \client\auth\kredssp** auf false fest.</span><span class="sxs-lookup"><span data-stu-id="d9b94-132">This cmdlet sets WS-Management setting **\<localhost|computername\>\Client\Auth\CredSSP** to false.</span></span>
- <span data-ttu-id="d9b94-133">Entfernt alle WSMAN/\*-Einstellungen aus der Windows-kredssp-Richtlinie **allowfreshanmelde** Informationen auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="d9b94-133">Removes any WSMan/\* setting from the Windows CredSSP policy **AllowFreshCredentials** on the client.</span></span>

<span data-ttu-id="d9b94-134">Wenn Sie den Server angeben, führt dieses Cmdlet die folgende Aktion aus:</span><span class="sxs-lookup"><span data-stu-id="d9b94-134">If you specify Server, this cmdlet performs the following action:</span></span>

- <span data-ttu-id="d9b94-135">Deaktiviert "kredssp" auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="d9b94-135">Disables CredSSP on the server.</span></span> <span data-ttu-id="d9b94-136">Mit diesem Cmdlet wird die WS-Management Einstellung **\<localhost|computername\> \service\auth\kredssp** auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9b94-136">This cmdlet sets the WS-Management setting **\<localhost|computername\>\Service\Auth\CredSSP** to false.</span></span>

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

### <span data-ttu-id="d9b94-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d9b94-137">CommonParameters</span></span>
<span data-ttu-id="d9b94-138">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d9b94-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d9b94-139">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d9b94-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d9b94-140">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d9b94-140">INPUTS</span></span>

### <span data-ttu-id="d9b94-141">Keine</span><span class="sxs-lookup"><span data-stu-id="d9b94-141">None</span></span>
<span data-ttu-id="d9b94-142">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="d9b94-142">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="d9b94-143">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d9b94-143">OUTPUTS</span></span>

### <span data-ttu-id="d9b94-144">Keine</span><span class="sxs-lookup"><span data-stu-id="d9b94-144">None</span></span>
<span data-ttu-id="d9b94-145">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d9b94-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d9b94-146">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d9b94-146">NOTES</span></span>

* <span data-ttu-id="d9b94-147">Um die CredSSP-Authentifizierung zu aktivieren, verwenden Sie das Enable-WSManCredSSP-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d9b94-147">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

*

## <span data-ttu-id="d9b94-148">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d9b94-148">RELATED LINKS</span></span>

[<span data-ttu-id="d9b94-149">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="d9b94-149">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="d9b94-150">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="d9b94-150">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="d9b94-151">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="d9b94-151">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="d9b94-152">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="d9b94-152">Get-WSManCredSSP</span></span>](Get-WSManCredSSP.md)

[<span data-ttu-id="d9b94-153">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d9b94-153">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="d9b94-154">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="d9b94-154">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="d9b94-155">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d9b94-155">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="d9b94-156">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="d9b94-156">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="d9b94-157">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d9b94-157">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="d9b94-158">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="d9b94-158">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="d9b94-159">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="d9b94-159">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="d9b94-160">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="d9b94-160">Test-WSMan</span></span>](Test-WSMan.md)

