---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: ce2046a9df5d4d02d718d6408c7a196a753c9914
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224836"
---
# <span data-ttu-id="1343e-103">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1343e-103">Get-WSManCredSSP</span></span>

## <span data-ttu-id="1343e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1343e-104">SYNOPSIS</span></span>
<span data-ttu-id="1343e-105">Ruft die CredSSP (Credential Security Support Provider)-bezogene Konfiguration für den Client ab.</span><span class="sxs-lookup"><span data-stu-id="1343e-105">Gets the Credential Security Support Provider-related configuration for the client.</span></span>

## <span data-ttu-id="1343e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1343e-106">SYNTAX</span></span>

```
Get-WSManCredSSP [<CommonParameters>]
```

## <span data-ttu-id="1343e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1343e-107">DESCRIPTION</span></span>
<span data-ttu-id="1343e-108">Das **Get-wsmankredssp** -Cmdlet ruft die Konfiguration des-Clients und des-Servers für die Unterstützung des Anmelde Informationsanbieters ab.</span><span class="sxs-lookup"><span data-stu-id="1343e-108">The **Get-WSManCredSSP** cmdlet gets the Credential Security Support Provider-related configuration of the client and the server.</span></span>
<span data-ttu-id="1343e-109">Die Ausgabe gibt an, ob die CredSSP (Credential Security Support Provider)-Authentifizierung aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1343e-109">The output indicates whether Credential Security Support Provider (CredSSP) authentication is enabled or disabled.</span></span>
<span data-ttu-id="1343e-110">Dieses Cmdlet zeigt auch Konfigurationsinformationen für die **allowfreshanmelde** -Richtlinie von "kredssp" an.</span><span class="sxs-lookup"><span data-stu-id="1343e-110">This cmdlet also displays configuration information for the **AllowFreshCredentials** policy of CredSSP.</span></span>

<span data-ttu-id="1343e-111">Wenn Sie die dedssp-Authentifizierung verwenden, werden die Anmelde Informationen des Benutzers an einen Remote Computer übergeben, der authentifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1343e-111">When you use CredSSP authentication, the user credentials are passed to a remote computer to be authenticated.</span></span>
<span data-ttu-id="1343e-112">Diese Art der Authentifizierung ist für Befehle vorgesehen, die eine Remote Sitzung aus einer anderen Remote Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="1343e-112">This type of authentication is designed for commands that create a remote session from another remote session.</span></span>
<span data-ttu-id="1343e-113">Wenn Sie z. b. einen Hintergrund Auftrag auf einem Remote Computer ausführen möchten, verwenden Sie diese Art der Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1343e-113">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="1343e-114">Das Cmdlet führt folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="1343e-114">The cmdlet performs the following actions:</span></span>

- <span data-ttu-id="1343e-115">Ruft die WS-Management auf dem Client auf dem Client ( **\<localhost|computername\> \client\auth\kredssp** ) ab.</span><span class="sxs-lookup"><span data-stu-id="1343e-115">Gets the WS-Management CredSSP setting on the client ( **\<localhost|computername\>\Client\Auth\CredSSP** ).</span></span>
- <span data-ttu-id="1343e-116">Ruft die Windows-aufwärtsrichtlinieneinstellung **allowfreshanmeldeinformationen** ab.</span><span class="sxs-lookup"><span data-stu-id="1343e-116">Gets the Windows CredSSP policy setting **AllowFreshCredentials** .</span></span>
- <span data-ttu-id="1343e-117">Ruft die WS-Management auf dem Server auf dem Server ( **\<localhost|computername\> \service\auth\kredssp** ) ab.</span><span class="sxs-lookup"><span data-stu-id="1343e-117">Gets the WS-Management CredSSP setting on the server ( **\<localhost|computername\>\Service\Auth\CredSSP** ).</span></span>

<span data-ttu-id="1343e-118">Vorsicht: die Benutzer Anmelde Informationen werden von der kredssp-Authentifizierung vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="1343e-118">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="1343e-119">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="1343e-119">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="1343e-120">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1343e-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="1343e-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1343e-121">EXAMPLES</span></span>

### <span data-ttu-id="1343e-122">Beispiel 1: Anzeigen der Konfiguration von "kredssp"</span><span class="sxs-lookup"><span data-stu-id="1343e-122">Example 1: Display CredSSP configuration</span></span>

```
PS C:\> Get-WSManCredSSP
```

<span data-ttu-id="1343e-123">Dieser Befehl zeigt CredSSP-Konfigurationsinformationen für Client und Server an.</span><span class="sxs-lookup"><span data-stu-id="1343e-123">This command displays CredSSP configuration information for both the client and server.</span></span>

<span data-ttu-id="1343e-124">Die Ausgabe gibt an, ob dieser Computer für CredSSP konfiguriert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="1343e-124">The output identifies that this computer is or is not configured for CredSSP.</span></span>

<span data-ttu-id="1343e-125">Wenn der Computer für CredSSP konfiguriert ist, lautet die Ausgabe wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1343e-125">If the computer is configured for CredSSP, this is the output:</span></span>

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

<span data-ttu-id="1343e-126">Wenn der Computer nicht für CredSSP konfiguriert ist, lautet die Ausgabe wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1343e-126">If the computer is not configured for CredSSP, this is the output:</span></span>

`The machine is not configured to allow delegating fresh credentials.`

## <span data-ttu-id="1343e-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1343e-127">PARAMETERS</span></span>

### <span data-ttu-id="1343e-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1343e-128">CommonParameters</span></span>
<span data-ttu-id="1343e-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1343e-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1343e-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1343e-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1343e-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1343e-131">INPUTS</span></span>

### <span data-ttu-id="1343e-132">Keine</span><span class="sxs-lookup"><span data-stu-id="1343e-132">None</span></span>
<span data-ttu-id="1343e-133">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="1343e-133">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="1343e-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1343e-134">OUTPUTS</span></span>

### <span data-ttu-id="1343e-135">Keine</span><span class="sxs-lookup"><span data-stu-id="1343e-135">None</span></span>
<span data-ttu-id="1343e-136">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="1343e-136">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1343e-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1343e-137">NOTES</span></span>

* <span data-ttu-id="1343e-138">Um die CredSSP-Authentifizierung zu deaktivieren, verwenden Sie das Disable-WSManCredSSP-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1343e-138">To disable CredSSP authentication, use the Disable-WSManCredSSP cmdlet.</span></span> <span data-ttu-id="1343e-139">Um die CredSSP-Authentifizierung zu aktivieren, verwenden Sie das Enable-WSManCredSSP-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1343e-139">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

## <span data-ttu-id="1343e-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1343e-140">RELATED LINKS</span></span>

[<span data-ttu-id="1343e-141">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="1343e-141">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="1343e-142">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1343e-142">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="1343e-143">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="1343e-143">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="1343e-144">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="1343e-144">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="1343e-145">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1343e-145">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="1343e-146">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="1343e-146">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="1343e-147">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1343e-147">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="1343e-148">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="1343e-148">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="1343e-149">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1343e-149">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="1343e-150">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="1343e-150">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="1343e-151">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="1343e-151">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="1343e-152">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="1343e-152">Test-WSMan</span></span>](Test-WSMan.md)
