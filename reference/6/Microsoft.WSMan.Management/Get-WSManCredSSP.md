---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: 814be4153687268123114b4036b640eeb0f0da71
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93200835"
---
# <span data-ttu-id="bc62b-103">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="bc62b-103">Get-WSManCredSSP</span></span>

## <span data-ttu-id="bc62b-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="bc62b-104">SYNOPSIS</span></span>
<span data-ttu-id="bc62b-105">Ruft die CredSSP (Credential Security Support Provider)-bezogene Konfiguration für den Client ab.</span><span class="sxs-lookup"><span data-stu-id="bc62b-105">Gets the Credential Security Support Provider-related configuration for the client.</span></span>

## <span data-ttu-id="bc62b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bc62b-106">SYNTAX</span></span>

```
Get-WSManCredSSP [<CommonParameters>]
```

## <span data-ttu-id="bc62b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bc62b-107">DESCRIPTION</span></span>
<span data-ttu-id="bc62b-108">Das **Get-wsmankredssp** -Cmdlet ruft die Konfiguration des-Clients und des-Servers für die Unterstützung des Anmelde Informationsanbieters ab.</span><span class="sxs-lookup"><span data-stu-id="bc62b-108">The **Get-WSManCredSSP** cmdlet gets the Credential Security Support Provider-related configuration of the client and the server.</span></span>
<span data-ttu-id="bc62b-109">Die Ausgabe gibt an, ob die CredSSP (Credential Security Support Provider)-Authentifizierung aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bc62b-109">The output indicates whether Credential Security Support Provider (CredSSP) authentication is enabled or disabled.</span></span>
<span data-ttu-id="bc62b-110">Dieses Cmdlet zeigt auch Konfigurationsinformationen für die **allowfreshanmelde** -Richtlinie von "kredssp" an.</span><span class="sxs-lookup"><span data-stu-id="bc62b-110">This cmdlet also displays configuration information for the **AllowFreshCredentials** policy of CredSSP.</span></span>

<span data-ttu-id="bc62b-111">Wenn Sie die dedssp-Authentifizierung verwenden, werden die Anmelde Informationen des Benutzers an einen Remote Computer übergeben, der authentifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc62b-111">When you use CredSSP authentication, the user credentials are passed to a remote computer to be authenticated.</span></span>
<span data-ttu-id="bc62b-112">Diese Art der Authentifizierung ist für Befehle vorgesehen, die eine Remote Sitzung aus einer anderen Remote Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="bc62b-112">This type of authentication is designed for commands that create a remote session from another remote session.</span></span>
<span data-ttu-id="bc62b-113">Wenn Sie z. b. einen Hintergrund Auftrag auf einem Remote Computer ausführen möchten, verwenden Sie diese Art der Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="bc62b-113">For example, if you want to run a background job on a remote computer, use this kind of authentication.</span></span>

<span data-ttu-id="bc62b-114">Das Cmdlet führt folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="bc62b-114">The cmdlet performs the following actions:</span></span>

- <span data-ttu-id="bc62b-115">Ruft die WS-Management auf dem Client auf dem Client ( **\<localhost|computername\> \client\auth\kredssp** ) ab.</span><span class="sxs-lookup"><span data-stu-id="bc62b-115">Gets the WS-Management CredSSP setting on the client ( **\<localhost|computername\>\Client\Auth\CredSSP** ).</span></span>
- <span data-ttu-id="bc62b-116">Ruft die Windows-aufwärtsrichtlinieneinstellung **allowfreshanmeldeinformationen** ab.</span><span class="sxs-lookup"><span data-stu-id="bc62b-116">Gets the Windows CredSSP policy setting **AllowFreshCredentials** .</span></span>
- <span data-ttu-id="bc62b-117">Ruft die WS-Management auf dem Server auf dem Server ( **\<localhost|computername\> \service\auth\kredssp** ) ab.</span><span class="sxs-lookup"><span data-stu-id="bc62b-117">Gets the WS-Management CredSSP setting on the server ( **\<localhost|computername\>\Service\Auth\CredSSP** ).</span></span>

<span data-ttu-id="bc62b-118">Vorsicht: die Benutzer Anmelde Informationen werden von der kredssp-Authentifizierung vom lokalen Computer an einen Remote Computer delegiert.</span><span class="sxs-lookup"><span data-stu-id="bc62b-118">Caution: CredSSP authentication delegates the user credentials from the local computer to a remote computer.</span></span>
<span data-ttu-id="bc62b-119">Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.</span><span class="sxs-lookup"><span data-stu-id="bc62b-119">This practice increases the security risk of the remote operation.</span></span>
<span data-ttu-id="bc62b-120">Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc62b-120">If the remote computer is compromised, when credentials are passed to it, the credentials can be used to control the network session.</span></span>

## <span data-ttu-id="bc62b-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="bc62b-121">EXAMPLES</span></span>

### <span data-ttu-id="bc62b-122">Beispiel 1: Anzeigen der Konfiguration von "kredssp"</span><span class="sxs-lookup"><span data-stu-id="bc62b-122">Example 1: Display CredSSP configuration</span></span>

```
PS C:\> Get-WSManCredSSP
```

<span data-ttu-id="bc62b-123">Dieser Befehl zeigt CredSSP-Konfigurationsinformationen für Client und Server an.</span><span class="sxs-lookup"><span data-stu-id="bc62b-123">This command displays CredSSP configuration information for both the client and server.</span></span>

<span data-ttu-id="bc62b-124">Die Ausgabe gibt an, ob dieser Computer für CredSSP konfiguriert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="bc62b-124">The output identifies that this computer is or is not configured for CredSSP.</span></span>

<span data-ttu-id="bc62b-125">Wenn der Computer für CredSSP konfiguriert ist, lautet die Ausgabe wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bc62b-125">If the computer is configured for CredSSP, this is the output:</span></span>

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

<span data-ttu-id="bc62b-126">Wenn der Computer nicht für CredSSP konfiguriert ist, lautet die Ausgabe wie folgt:</span><span class="sxs-lookup"><span data-stu-id="bc62b-126">If the computer is not configured for CredSSP, this is the output:</span></span>

`The machine is not configured to allow delegating fresh credentials.`

## <span data-ttu-id="bc62b-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bc62b-127">PARAMETERS</span></span>

### <span data-ttu-id="bc62b-128">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bc62b-128">CommonParameters</span></span>
<span data-ttu-id="bc62b-129">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bc62b-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bc62b-130">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bc62b-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bc62b-131">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="bc62b-131">INPUTS</span></span>

### <span data-ttu-id="bc62b-132">Keine</span><span class="sxs-lookup"><span data-stu-id="bc62b-132">None</span></span>
<span data-ttu-id="bc62b-133">Dieses Cmdlet nimmt keine Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="bc62b-133">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="bc62b-134">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="bc62b-134">OUTPUTS</span></span>

### <span data-ttu-id="bc62b-135">Keine</span><span class="sxs-lookup"><span data-stu-id="bc62b-135">None</span></span>
<span data-ttu-id="bc62b-136">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="bc62b-136">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bc62b-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="bc62b-137">NOTES</span></span>

* <span data-ttu-id="bc62b-138">Um die CredSSP-Authentifizierung zu deaktivieren, verwenden Sie das Disable-WSManCredSSP-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bc62b-138">To disable CredSSP authentication, use the Disable-WSManCredSSP cmdlet.</span></span> <span data-ttu-id="bc62b-139">Um die CredSSP-Authentifizierung zu aktivieren, verwenden Sie das Enable-WSManCredSSP-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bc62b-139">To enable CredSSP authentication, use the Enable-WSManCredSSP cmdlet.</span></span>

## <span data-ttu-id="bc62b-140">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="bc62b-140">RELATED LINKS</span></span>

[<span data-ttu-id="bc62b-141">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="bc62b-141">Connect-WSMan</span></span>](Connect-WSMan.md)

[<span data-ttu-id="bc62b-142">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="bc62b-142">Disable-WSManCredSSP</span></span>](Disable-WSManCredSSP.md)

[<span data-ttu-id="bc62b-143">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="bc62b-143">Disconnect-WSMan</span></span>](Disconnect-WSMan.md)

[<span data-ttu-id="bc62b-144">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="bc62b-144">Enable-WSManCredSSP</span></span>](Enable-WSManCredSSP.md)

[<span data-ttu-id="bc62b-145">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc62b-145">Get-WSManInstance</span></span>](Get-WSManInstance.md)

[<span data-ttu-id="bc62b-146">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="bc62b-146">Invoke-WSManAction</span></span>](Invoke-WSManAction.md)

[<span data-ttu-id="bc62b-147">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc62b-147">New-WSManInstance</span></span>](New-WSManInstance.md)

[<span data-ttu-id="bc62b-148">New-WSManSessionOption</span><span class="sxs-lookup"><span data-stu-id="bc62b-148">New-WSManSessionOption</span></span>](New-WSManSessionOption.md)

[<span data-ttu-id="bc62b-149">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc62b-149">Remove-WSManInstance</span></span>](Remove-WSManInstance.md)

[<span data-ttu-id="bc62b-150">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="bc62b-150">Set-WSManInstance</span></span>](Set-WSManInstance.md)

[<span data-ttu-id="bc62b-151">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="bc62b-151">Set-WSManQuickConfig</span></span>](Set-WSManQuickConfig.md)

[<span data-ttu-id="bc62b-152">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="bc62b-152">Test-WSMan</span></span>](Test-WSMan.md)
