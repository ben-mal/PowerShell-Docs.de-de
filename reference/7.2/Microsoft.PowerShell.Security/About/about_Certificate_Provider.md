---
description: Zertifikat
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/about/about_certificate_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Zertifikat-Anbieter
ms.openlocfilehash: 78536024e8e953a70485a7d950b187ba9a3fc405
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596552"
---
# <a name="certificate-provider"></a><span data-ttu-id="beaa0-103">Zertifikat-Anbieter</span><span class="sxs-lookup"><span data-stu-id="beaa0-103">Certificate Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="beaa0-104">Anbietername</span><span class="sxs-lookup"><span data-stu-id="beaa0-104">Provider name</span></span>

<span data-ttu-id="beaa0-105">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="beaa0-105">Certificate</span></span>

## <a name="drives"></a><span data-ttu-id="beaa0-106">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="beaa0-106">Drives</span></span>

`Cert:`

## <a name="capabilities"></a><span data-ttu-id="beaa0-107">Funktionen</span><span class="sxs-lookup"><span data-stu-id="beaa0-107">Capabilities</span></span>

<span data-ttu-id="beaa0-108">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="beaa0-108">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="beaa0-109">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beaa0-109">Short description</span></span>

<span data-ttu-id="beaa0-110">Ermöglicht den Zugriff auf X. 509-Zertifikat Speicher und-Zertifikate in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beaa0-110">Provides access to X.509 certificate stores and certificates in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="beaa0-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beaa0-111">Detailed description</span></span>

<span data-ttu-id="beaa0-112">Mit dem PowerShell- **Zertifikat** Anbieter können Sie Zertifikate und Zertifikat Speicher in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-112">The PowerShell **Certificate** provider lets you get, add, change, clear, and delete certificates and certificate stores in PowerShell.</span></span>

<span data-ttu-id="beaa0-113">Das **Zertifikat** Laufwerk ist ein hierarchischer Namespace, der die Zertifikat Speicher und Zertifikate auf dem Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="beaa0-113">The **Certificate** drive is a hierarchical namespace containing the certificate stores and certificates on your computer.</span></span>

<span data-ttu-id="beaa0-114">Der **Zertifikat** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-114">The **Certificate** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="beaa0-115">Get-Location</span><span class="sxs-lookup"><span data-stu-id="beaa0-115">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="beaa0-116">Set-Location</span><span class="sxs-lookup"><span data-stu-id="beaa0-116">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="beaa0-117">Get-Item</span><span class="sxs-lookup"><span data-stu-id="beaa0-117">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="beaa0-118">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="beaa0-118">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="beaa0-119">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="beaa0-119">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="beaa0-120">Move-Item</span><span class="sxs-lookup"><span data-stu-id="beaa0-120">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="beaa0-121">New-Item</span><span class="sxs-lookup"><span data-stu-id="beaa0-121">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="beaa0-122">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="beaa0-122">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="beaa0-123">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="beaa0-123">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="beaa0-124">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="beaa0-124">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="beaa0-125">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="beaa0-125">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="beaa0-126">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="beaa0-126">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="beaa0-127">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="beaa0-127">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="beaa0-128">Von diesem Anbieter verfügbar gemachte Typen</span><span class="sxs-lookup"><span data-stu-id="beaa0-128">Types exposed by this provider</span></span>

<span data-ttu-id="beaa0-129">Das Zertifikat Laufwerk macht die folgenden Typen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="beaa0-129">The Certificate drive exposes the following types.</span></span>

- <span data-ttu-id="beaa0-130">Speicherorte (Microsoft. PowerShell. Commands. X509StoreLocation), bei denen es sich um Container auf hoher Ebene handelt, die die Zertifikate für den aktuellen Benutzer und für alle Benutzer gruppieren.</span><span class="sxs-lookup"><span data-stu-id="beaa0-130">Store locations (Microsoft.PowerShell.Commands.X509StoreLocation), which are high-level containers that group the certificates for the current user and for all users.</span></span> <span data-ttu-id="beaa0-131">Jedes System verfügt über einen CurrentUser- und LocalMachine (alle Benutzer)-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="beaa0-131">Each system has a CurrentUser and LocalMachine (all users) store location.</span></span>

- <span data-ttu-id="beaa0-132">Zertifikate speichern (System. Security. Cryptography. X509Certificates. X509Store), bei denen es sich um physische Speicher handelt, in denen Zertifikate gespeichert und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-132">Certificates stores (System.Security.Cryptography.X509Certificates.X509Store), which are physical stores in which certificates are saved and managed.</span></span>

- <span data-ttu-id="beaa0-133">X. 509 **System. Security. Cryptography. X509Certificates. X509Certificate2** -Zertifikate, von denen jedes ein X. 509-Zertifikat auf dem Computer darstellt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-133">X.509 **System.Security.Cryptography.X509Certificates.X509Certificate2** certificates, each of which represent an X.509 certificate on the computer.</span></span>
  <span data-ttu-id="beaa0-134">Zertifikate werden durch ihre Fingerabdrücke identifiziert.</span><span class="sxs-lookup"><span data-stu-id="beaa0-134">Certificates are identified by their thumbprints.</span></span>

## <a name="navigating-the-certificate-drive"></a><span data-ttu-id="beaa0-135">Navigieren im Zertifikat Laufwerk</span><span class="sxs-lookup"><span data-stu-id="beaa0-135">Navigating the Certificate drive</span></span>

<span data-ttu-id="beaa0-136">Der **Zertifikat Anbieter macht** den Zertifikat Namespace als `Cert:` Laufwerk in PowerShell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="beaa0-136">The **Certificate** provider exposes the certificate namespace as the `Cert:` drive in PowerShell.</span></span> <span data-ttu-id="beaa0-137">Dieser Befehl verwendet den- `Set-Location` Befehl, um den aktuellen Speicherort in den Stamm Zertifikat Speicher im LocalMachine-Speicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="beaa0-137">This command uses the `Set-Location` command to change the current location to the Root certificate store in the LocalMachine store location.</span></span> <span data-ttu-id="beaa0-138">Verwenden Sie einen umgekehrten Schrägstrich ( \\ ) oder einen Schrägstrich (/), um eine Ebene des `Cert:` Laufwerks anzugeben.</span><span class="sxs-lookup"><span data-stu-id="beaa0-138">Use a backslash (\\) or a forward slash (/) to indicate a level of the `Cert:` drive.</span></span>

```powershell
Set-Location Cert:
```

<span data-ttu-id="beaa0-139">Sie können auch mit dem Zertifikat Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="beaa0-139">You can also work with the certificate provider from any other PowerShell drive.</span></span> <span data-ttu-id="beaa0-140">Um auf einen Alias von einem anderen Speicherort zu verweisen, verwenden Sie den `Cert:` Namen des Laufwerks im Pfad.</span><span class="sxs-lookup"><span data-stu-id="beaa0-140">To reference an alias from another location, use the `Cert:` drive name in the path.</span></span>

```powershell
PS Cert:\> Set-Location -Path LocalMachine\Root
```

<span data-ttu-id="beaa0-141">Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein.</span><span class="sxs-lookup"><span data-stu-id="beaa0-141">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="beaa0-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="beaa0-142">For example, type:</span></span>

```powershell
Set-Location C:
```

> [!NOTE]
> <span data-ttu-id="beaa0-143">PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten.</span><span class="sxs-lookup"><span data-stu-id="beaa0-143">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="beaa0-144">Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="beaa0-144">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span>
> <span data-ttu-id="beaa0-145">und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="beaa0-145">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-contents-of-the-cert-drive"></a><span data-ttu-id="beaa0-146">Anzeigen des Inhalts des CERT:-Laufwerks</span><span class="sxs-lookup"><span data-stu-id="beaa0-146">Displaying the Contents of the Cert: drive</span></span>

<span data-ttu-id="beaa0-147">Dieser Befehl verwendet das `Get-ChildItem` Cmdlet, um die Zertifikat Speicher im Zertifikat Speicherort von CurrentUser anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-147">This command uses the `Get-ChildItem` cmdlet to display the certificate stores in the CurrentUser certificate store location.</span></span>

<span data-ttu-id="beaa0-148">Wenn Sie sich nicht auf dem `Cert:` Laufwerk befinden, verwenden Sie einen absoluten Pfad.</span><span class="sxs-lookup"><span data-stu-id="beaa0-148">If you are not in the `Cert:` drive, use an absolute path.</span></span>

```powershell
PS Cert:\CurrentUser\> Get-ChildItem
```

### <a name="displaying-certificate-properties-within-the-cert-drive"></a><span data-ttu-id="beaa0-149">Anzeigen von Zertifikat Eigenschaften im CERT:-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="beaa0-149">Displaying certificate properties within the Cert: drive</span></span>

<span data-ttu-id="beaa0-150">In diesem Beispiel wird ein Zertifikat mit abgerufen `Get-Item` und in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="beaa0-150">This example gets a certificate with `Get-Item` and stores it in a variable.</span></span>
<span data-ttu-id="beaa0-151">Das Beispiel zeigt die neuen Zertifikat Skript Eigenschaften (**dnsnamelist**, **enhancedkeyugeist** **) mithilfe** von `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="beaa0-151">The example shows the new certificate script properties (**DnsNameList**, **EnhancedKeyUsageList**, **SendAsTrustedIssuer**) using `Select-Object`.</span></span>

```powershell
$c = Get-Item cert:\LocalMachine\My\52A149D0393CE8A8D4AF0B172ED667A9E3A1F44E
$c | Format-List DnsNameList, EnhancedKeyUsageList, SendAsTrustedIssuer
```

```output
DnsNameList          : {SERVER01.contoso.com}
EnhancedKeyUsageList : {WiFi-Machine (1.3.6.1.4.1.311.42.2.6),
                       Client Authentication (1.3.6.1.5.5.7.3.2)}
SendAsTrustedIssuer  : False
```

### <a name="find-all-codesigning-certificates"></a><span data-ttu-id="beaa0-152">Alle codesigungszertifikate suchen</span><span class="sxs-lookup"><span data-stu-id="beaa0-152">Find all CodeSigning certificates</span></span>

<span data-ttu-id="beaa0-153">Dieser Befehl verwendet die **codeSigningCert** -und **recurse** -Parameter des `Get-ChildItem` Cmdlets, um alle Zertifikate auf dem Computer zu erhalten, die über die Code Signatur Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-153">This command uses the **CodeSigningCert** and **Recurse** parameters of the `Get-ChildItem` cmdlet to get all of the certificates on the computer that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path cert: -CodeSigningCert -Recurse
```

### <a name="find-expired-certificates"></a><span data-ttu-id="beaa0-154">Abgelaufene Zertifikate suchen</span><span class="sxs-lookup"><span data-stu-id="beaa0-154">Find expired certificates</span></span>

<span data-ttu-id="beaa0-155">Mit diesem Befehl wird der **expiriingindays** -Parameter des `Get-ChildItem` Cmdlets verwendet, um Zertifikate zu erhalten, die innerhalb der nächsten 30 Tage ablaufen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-155">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet to get certificates that will expire within the next 30 days.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\WebHosting -ExpiringInDays 30
```

### <a name="find-server-ssl-certificates"></a><span data-ttu-id="beaa0-156">Suchen von Server-SSL-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="beaa0-156">Find Server SSL Certificates</span></span>

<span data-ttu-id="beaa0-157">Dieser Befehl verwendet den **sslserverauthentication** -Parameter des `Get-ChildItem` Cmdlets, um alle Server-SSL-Zertifikate im My-und Webhosting-Speicher zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="beaa0-157">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get all Server SSL Certificates in the My and WebHosting stores.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\My, cert:\LocalMachine\WebHosting `
  -SSLServerAuthentication
```

### <a name="find-expired-certificates-on-remote-computers"></a><span data-ttu-id="beaa0-158">Suchen abgelaufener Zertifikate auf Remote Computern</span><span class="sxs-lookup"><span data-stu-id="beaa0-158">Find expired certificates on remote computers</span></span>

<span data-ttu-id="beaa0-159">Dieser Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Get-ChildItem` Befehls auf den Computern SRV01 und Srv02.</span><span class="sxs-lookup"><span data-stu-id="beaa0-159">This command uses the `Invoke-Command` cmdlet to run a `Get-ChildItem` command on the Srv01 and Srv02 computers.</span></span> <span data-ttu-id="beaa0-160">Der Wert NULL (0) im **expiriingindays** -Parameter ruft Zertifikate auf den Computern SRV01 und Srv02 ab, die abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="beaa0-160">A value of zero (0) in the **ExpiringInDays** parameter gets certificates on the Srv01 and Srv02 computers that have expired.</span></span>

```powershell
Invoke-Command -ComputerName Srv01, Srv02 {Get-ChildItem -Path cert:\* `
  -Recurse -ExpiringInDays 0}
```

### <a name="combining-filters-to-find-a-specific-set-of-certificates"></a><span data-ttu-id="beaa0-161">Kombinieren von Filtern für die Suche nach einem bestimmten Satz von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="beaa0-161">Combining filters to find a specific set of certificates</span></span>

<span data-ttu-id="beaa0-162">Mit diesem Befehl werden alle Zertifikate im LocalMachine-Speicherort abgerufen, die die folgenden Attribute aufweisen:</span><span class="sxs-lookup"><span data-stu-id="beaa0-162">This command gets all certificates in the LocalMachine store location that have the following attributes:</span></span>

- <span data-ttu-id="beaa0-163">"Fabrikam" im DNS-Namen</span><span class="sxs-lookup"><span data-stu-id="beaa0-163">"fabrikam" in their DNS name</span></span>
- <span data-ttu-id="beaa0-164">"Client Authentifizierung" in der EKU</span><span class="sxs-lookup"><span data-stu-id="beaa0-164">"Client Authentication" in their EKU</span></span>
- <span data-ttu-id="beaa0-165">der Wert `$true` für die **sendastrusteabschrecker** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="beaa0-165">a value of `$true` for the **SendAsTrustedIssuer** property</span></span>
- <span data-ttu-id="beaa0-166">läuft nicht innerhalb der nächsten 30 Tage ab.</span><span class="sxs-lookup"><span data-stu-id="beaa0-166">do not expire within the next 30 days.</span></span>

<span data-ttu-id="beaa0-167">Die **NotAfter** -Eigenschaft speichert das Ablaufdatum des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="beaa0-167">The **NotAfter** property stores the certificate expiration date.</span></span>

```powershell
[DateTime] $ValidThrough = (Get-Date) + (New-TimeSpan -Days 30)
Get-ChildItem -Path cert:\* -Recurse -DNSName "*fabrikam*" `
  -EKU "*Client Authentication*" | Where-Object {
                                     $_.SendAsTrustedIssuer -and `
                                     $_.NotAfter -gt $ValidThrough
                                   }
```

## <a name="opening-the-certificates-mmc-snap-in"></a><span data-ttu-id="beaa0-168">Öffnen des Zertifikate-MMC-Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="beaa0-168">Opening the Certificates MMC Snap-in</span></span>

<span data-ttu-id="beaa0-169">Mit dem- `Invoke-Item` Cmdlet wird die Standardanwendung verwendet, um einen von Ihnen angegebenen Pfad zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-169">The `Invoke-Item` cmdlet will use the default application to open a path you specify.</span></span> <span data-ttu-id="beaa0-170">Bei Zertifikaten ist die Standardanwendung das MMC-Snap-in "Zertifikate".</span><span class="sxs-lookup"><span data-stu-id="beaa0-170">For certificates, the default application is the Certificates MMC snap-in.</span></span>

<span data-ttu-id="beaa0-171">Dieser Befehl öffnet das Zertifikate-MMC-Snap-In zum Verwalten des angegebenen Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="beaa0-171">This command opens the Certificates MMC snap-in to manage the specified certificate.</span></span>

```powershell
Invoke-Item cert:\CurrentUser\my\6B8223358119BB08840DEE50FD8AF9EA776CE66B
```

## <a name="copying-certificates"></a><span data-ttu-id="beaa0-172">Kopieren von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="beaa0-172">Copying Certificates</span></span>

<span data-ttu-id="beaa0-173">Das Kopieren von Zertifikaten wird vom **Zertifikat** Anbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-173">Copying certificates is not supported by the **Certificate** provider.</span></span> <span data-ttu-id="beaa0-174">Wenn Sie versuchen, ein Zertifikat zu kopieren, wird dieser Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-174">When you attempt to copy a certificate, you see this error.</span></span>

```
$path = "Cert:\LocalMachine\Root\E2C0F6662D3C569705B4B31FE2CBF3434094B254"
PS Cert:\LocalMachine\> Copy-Item -Path $path -Destination .\CA\
Copy-Item : Provider operation stopped because the provider does not support
this operation.
At line:1 char:1
+ Copy-Item -Path $path -Destination .\CA\
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotImplemented: (:) [Copy-Item],
                              PSNotSupportedException
    + FullyQualifiedErrorId : NotSupported,
                              Microsoft.PowerShell.Commands.CopyItemCommand
```

## <a name="moving-certificates"></a><span data-ttu-id="beaa0-175">Verschieben von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="beaa0-175">Moving Certificates</span></span>

### <a name="move-all-ssl-server-authentication-certs-to-the-webhosting-store"></a><span data-ttu-id="beaa0-176">Verschieben aller Zertifikate der SSL-Server Authentifizierung in den Webhosting-Speicher</span><span class="sxs-lookup"><span data-stu-id="beaa0-176">Move all SSL Server authentication certs to the WebHosting store</span></span>

<span data-ttu-id="beaa0-177">Dieser Befehl verwendet das `Move-Item` Cmdlet, um ein Zertifikat aus dem eigenen Speicher in den Webhosting-Speicher zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="beaa0-177">This command uses the `Move-Item` cmdlet to move a certificate from the My store to the WebHosting store.</span></span>

<span data-ttu-id="beaa0-178">`Move-Item` von werden keine Zertifikat Speicher verschoben, und Zertifikate werden nicht an einen anderen Speicherort verschoben, z. b. das Verschieben eines Zertifikats von LocalMachine nach CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="beaa0-178">`Move-Item` will not move certificate stores and it will not move certificates to a different store location, such as moving a certificate from LocalMachine to CurrentUser.</span></span> <span data-ttu-id="beaa0-179">Das `Move-Item` Cmdlet verschiebt Zertifikate, aber keine privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="beaa0-179">The `Move-Item` cmdlet moves certificates, but it does not move private keys.</span></span>

<span data-ttu-id="beaa0-180">Dieser Befehl verwendet den **sslserverauthentication** -Parameter des `Get-ChildItem` Cmdlets, um SSL-Server Authentifizierungs Zertifikate im My-Zertifikat Speicher zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="beaa0-180">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get SSL server authentication certificates in the MY certificate store.</span></span>

<span data-ttu-id="beaa0-181">Die zurückgegebenen Zertifikate werden an das `Move-Item` Cmdlet weitergeleitet, wodurch die Zertifikate in den Webhosting-Speicher verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-181">The returned certificates are piped to the `Move-Item` cmdlet, which moves the certificates to the WebHosting store.</span></span>

```powershell
Get-ChildItem cert:\LocalMachine\My -SSLServerAuthentication | Move-Item `
  -Destination cert:\LocalMachine\WebHosting
```

## <a name="deleting-certificates-and-private-keys"></a><span data-ttu-id="beaa0-182">Löschen von Zertifikaten und privaten Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="beaa0-182">Deleting Certificates and Private Keys</span></span>

<span data-ttu-id="beaa0-183">Mit dem- `Remove-Item` Cmdlet werden von Ihnen angegebene Zertifikate entfernt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-183">The `Remove-Item` cmdlet will remove certificates that you specify.</span></span> <span data-ttu-id="beaa0-184">Der `-DeleteKey` dynamische Parameter löscht den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="beaa0-184">The `-DeleteKey` dynamic parameter deletes the private key.</span></span>

### <a name="delete-a-certificate-from-the-ca-store"></a><span data-ttu-id="beaa0-185">Löschen eines Zertifikats aus dem ca-Speicher</span><span class="sxs-lookup"><span data-stu-id="beaa0-185">Delete a Certificate from the CA store</span></span>

<span data-ttu-id="beaa0-186">Dieser Befehl löscht ein Zertifikat aus dem CA-Zertifikatspeicher, lässt jedoch den zugehörigen privaten Schlüssel intakt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-186">This command deletes a certificate from the CA certificate store, but leaves the associated private key intact.</span></span>

<span data-ttu-id="beaa0-187">Im- `Cert:` Laufwerk `Remove-Item` unterstützt das Cmdlet nur die **Parameter DeleteKey**, **path**, **WhatIf** und **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="beaa0-187">In the `Cert:` drive, the `Remove-Item` cmdlet supports only the **DeleteKey**, **Path**, **WhatIf**, and **Confirm** parameters.</span></span> <span data-ttu-id="beaa0-188">Alle anderen Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="beaa0-188">All other parameters are ignored.</span></span>

```powershell
Remove-Item cert:\LocalMachine\CA\5DDC44652E62BF9AA1116DC41DE44AB47C87BDD0
```

### <a name="delete-a-certificate-using-a-wildcards-in-the-dns-name"></a><span data-ttu-id="beaa0-189">Löschen eines Zertifikats mithilfe von Platzhaltern im DNS-Namen</span><span class="sxs-lookup"><span data-stu-id="beaa0-189">Delete a Certificate using a wildcards in the DNS name</span></span>

<span data-ttu-id="beaa0-190">Dieser Befehl löscht alle Zertifikate, deren DNS-Name "Fabrikam" enthält.</span><span class="sxs-lookup"><span data-stu-id="beaa0-190">This command deletes all certificates that have a DNS name that contains "Fabrikam".</span></span> <span data-ttu-id="beaa0-191">Er verwendet den **DnsName** -Parameter des `Get-ChildItem` Cmdlets, um die Zertifikate zu erhalten, und das `Remove-Item` Cmdlet, um Sie zu löschen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-191">It uses the **DNSName** parameter of the `Get-ChildItem` cmdlet to get the certificates and the `Remove-Item` cmdlet to delete them.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine -DnsName *Fabrikam* | Remove-Item
```

### <a name="delete-private-keys-from-a-remote-computer"></a><span data-ttu-id="beaa0-192">Löschen von privaten Schlüsseln von einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="beaa0-192">Delete private keys from a remote computer</span></span>

<span data-ttu-id="beaa0-193">Diese Reihe von Befehlen ermöglicht die Delegation und löscht dann das Zertifikat und den zugehörigen privaten Schlüssel auf einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="beaa0-193">This series of commands enables delegation and then deletes the certificate and associated private key on a remote computer.</span></span> <span data-ttu-id="beaa0-194">Um einen privaten Schlüssel auf einem Remotecomputer zu löschen, müssen Sie die delegierten Anmeldeinformationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-194">To delete a private key on a remote computer, you must use delegated credentials.</span></span>

<span data-ttu-id="beaa0-195">Verwenden Sie das- `Enable-WSManCredSSP` Cmdlet, um die Authentifizierung für den Anmelde Informationsdienst (Security Service Provider, kredssp) auf einem Client auf dem Remote Computer S1 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="beaa0-195">Use the `Enable-WSManCredSSP` cmdlet to enable Credential Security Service Provider (CredSSP) authentication on a client on the S1 remote computer.</span></span>
<span data-ttu-id="beaa0-196">CredSSP ermöglicht die delegierte Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="beaa0-196">CredSSP permits delegated authentication.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer S1
```

<span data-ttu-id="beaa0-197">Verwenden `Connect-WSMan` Sie das Cmdlet, um den Computer S1 mit dem WinRM-Dienst auf dem lokalen Computer zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-197">Use the `Connect-WSMan` cmdlet to connect the S1 computer to the WinRM service on the local computer.</span></span> <span data-ttu-id="beaa0-198">Wenn dieser Befehl abgeschlossen ist, wird der S1-Computer auf dem lokalen `WSMan:` Laufwerk in PowerShell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-198">When this command completes, the S1 computer appears in the local `WSMan:` drive in PowerShell.</span></span>

```powershell
Connect-WSMan -ComputerName S1 -Credential Domain01\Admin01
```

<span data-ttu-id="beaa0-199">Nun können Sie das Cmdlet "Set-Item" im WSMAN:-Laufwerk verwenden, um das Attribut "Attribut" für den WinRM-Dienst zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="beaa0-199">Now, you can use the Set-Item cmdlet in the WSMan: drive to enable the CredSSP attribute for the WinRM service.</span></span>

```powershell
Set-Item -Path WSMan:\S1\Service\Auth\CredSSP -Value $true
```

<span data-ttu-id="beaa0-200">Starten Sie mithilfe des Cmdlets eine Remote Sitzung auf dem Computer S1 `New-PSSession` , und geben Sie die Authentifizierung für die Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="beaa0-200">Start a remote session on the s1 computer using the `New-PSSession` cmdlet, and specify CredSSP authentication.</span></span> <span data-ttu-id="beaa0-201">Speichert die Sitzung in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-201">Saves the session in the `$s` variable.</span></span>

```powershell
$s  = New-PSSession S1 -Authentication CredSSP -Credential Domain01\Admin01
```

<span data-ttu-id="beaa0-202">Verwenden Sie abschließend das `Invoke-Command` Cmdlet, um einen `Remove-Item` Befehl in der Sitzung in der `$s` Variablen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-202">Finally, use the `Invoke-Command` cmdlet to run a `Remove-Item` command in the session in the `$s` variable.</span></span> <span data-ttu-id="beaa0-203">Der `Remove-Item` Befehl verwendet den **DeleteKey** -Parameter, um den privaten Schlüssel zusammen mit dem angegebenen Zertifikat zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-203">The `Remove-Item` command uses the **DeleteKey** parameter to remove the private key along with the specified certificate.</span></span>

```powershell
Invoke-Command -Session $s { Remove-Item `
  -Path cert:\LocalMachine\My\D2D38EBA60CAA1C12055A2E1C83B15AD450110C2 `
  -DeleteKey
  }
```

### <a name="delete-expired-certificates"></a><span data-ttu-id="beaa0-204">Abgelaufene Zertifikate löschen</span><span class="sxs-lookup"><span data-stu-id="beaa0-204">Delete expired Certificates</span></span>

<span data-ttu-id="beaa0-205">Dieser Befehl verwendet den **expiriingindays** -Parameter des `Get-ChildItem` Cmdlets mit dem Wert 0, um Zertifikate im Webhosting-Speicher zu erhalten, die abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="beaa0-205">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet with a value of 0 to get certificates in the WebHosting store that have expired.</span></span>

<span data-ttu-id="beaa0-206">Die Variable, die die zurückgegebenen Zertifikate enthält, wird an das `Remove-Item` Cmdlet weitergeleitet, wodurch Sie gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-206">The variable containing the returned certificates is piped to the `Remove-Item` cmdlet, which deletes them.</span></span> <span data-ttu-id="beaa0-207">Der Befehl verwendet den **DeleteKey** -Parameter, um den privaten Schlüssel zusammen mit dem Zertifikat zu löschen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-207">The command uses the **DeleteKey** parameter to delete the private key along with the certificate.</span></span>

```powershell
$expired = Get-ChildItem cert:\LocalMachine\WebHosting -ExpiringInDays 0
$expired | Remove-Item -DeleteKey
```

## <a name="creating-certificates"></a><span data-ttu-id="beaa0-208">Erstellen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="beaa0-208">Creating Certificates</span></span>

<span data-ttu-id="beaa0-209">Mit dem- `New-Item` Cmdlet werden keine neuen Zertifikate im **Zertifikat** Anbieter erstellt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-209">The `New-Item` cmdlet does not create new certificates in the **Certificate** provider.</span></span> <span data-ttu-id="beaa0-210">Verwenden Sie das Cmdlet [New-selfsignedcertificate](/powershell/module/pkiclient/new-selfsignedcertificate) , um ein Zertifikat zu Testzwecken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-210">Use the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet to create a certificate for testing purposes.</span></span>

## <a name="creating-certificate-stores"></a><span data-ttu-id="beaa0-211">Erstellen von Zertifikatspeichern</span><span class="sxs-lookup"><span data-stu-id="beaa0-211">Creating Certificate Stores</span></span>

<span data-ttu-id="beaa0-212">Im CERT:-Laufwerk erstellt das `New-Item` Cmdlet Zertifikat Speicher am LocalMachine-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="beaa0-212">In the Cert: drive, the `New-Item` cmdlet creates certificate stores in the LocalMachine store location.</span></span> <span data-ttu-id="beaa0-213">Er unterstützt die Parameter **Name**, **path**, **WhatIf** und **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="beaa0-213">It supports the **Name**, **Path**, **WhatIf**, and **Confirm** parameters.</span></span> <span data-ttu-id="beaa0-214">Alle anderen Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="beaa0-214">All other parameters are ignored.</span></span> <span data-ttu-id="beaa0-215">Der Befehl gibt eine **System. Security. Cryptography. X509Certificates. X509Store** zurück, die den neuen Zertifikat Speicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-215">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

<span data-ttu-id="beaa0-216">Dieser Befehl erstellt einen neuen Zertifikatspeicher mit dem Namen "CustomStore" am Speicherort des LocalMachine-Speichers.</span><span class="sxs-lookup"><span data-stu-id="beaa0-216">This command creates a new certificate store named "CustomStore" in the LocalMachine store location.</span></span>

```powershell
New-Item -Path cert:\LocalMachine\CustomStore
```

### <a name="create-a-new-certificate-store-on-a-remote-computer"></a><span data-ttu-id="beaa0-217">Erstellen eines neuen Zertifikat Speicher auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="beaa0-217">Create a new certificate store on a remote computer</span></span>

<span data-ttu-id="beaa0-218">Dieser Befehl erstellt einen neuen Zertifikatspeicher mit dem Namen "HostingStore" am LocalMachine-Speicherort auf dem Computer Server01.</span><span class="sxs-lookup"><span data-stu-id="beaa0-218">This command creates a new certificate store named "HostingStore" in the LocalMachine store location on the Server01 computer.</span></span>

<span data-ttu-id="beaa0-219">Der Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `New-Item` Befehls auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="beaa0-219">The command uses the `Invoke-Command` cmdlet to run a `New-Item` command on the Server01 computer.</span></span> <span data-ttu-id="beaa0-220">Der Befehl gibt eine **System. Security. Cryptography. X509Certificates. X509Store** zurück, die den neuen Zertifikat Speicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-220">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

```powershell
Invoke-Command { New-Item -Path cert:\LocalMachine\CustomStore } `
  -ComputerName Server01
```

## <a name="creating-client-certificates-for-ws-man"></a><span data-ttu-id="beaa0-221">Erstellen von Client Zertifikaten für WS-Man</span><span class="sxs-lookup"><span data-stu-id="beaa0-221">Creating Client Certificates for WS-Man</span></span>

<span data-ttu-id="beaa0-222">Mit diesem Befehl wird der **ClientCertificate** -Eintrag erstellt, der vom **WS-Management** -Client verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="beaa0-222">This command creates **ClientCertificate** entry that can be used by the **WS-Management** client.</span></span> <span data-ttu-id="beaa0-223">Das neue **ClientCertificate** wird unter dem Verzeichnis " **ClientCertificate** " als "ClientCertificate_1234567890" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-223">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="beaa0-224">Alle Parameter müssen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-224">All of the parameters are mandatory.</span></span> <span data-ttu-id="beaa0-225">Der **Aussteller** muss den Fingerabdruck des Aussteller Zertifikats aufweisen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-225">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* -Credential $cred
```

## <a name="deleting-certificate-stores"></a><span data-ttu-id="beaa0-226">Löschen von Zertifikatspeichern</span><span class="sxs-lookup"><span data-stu-id="beaa0-226">Deleting Certificate Stores</span></span>

### <a name="delete-a-certificate-store-from-a-remote-computer"></a><span data-ttu-id="beaa0-227">Löschen eines Zertifikat Speicher von einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="beaa0-227">Delete a certificate store from a remote computer</span></span>

<span data-ttu-id="beaa0-228">Dieser Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Remove-Item` Befehls auf den Computern S1 und S2.</span><span class="sxs-lookup"><span data-stu-id="beaa0-228">This command uses the `Invoke-Command` cmdlet to run a `Remove-Item` command on the S1 and S2 computers.</span></span> <span data-ttu-id="beaa0-229">Der `Remove-Item` Befehl enthält den **recurse** -Parameter, mit dem die Zertifikate im Speicher gelöscht werden, bevor der Speicher gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="beaa0-229">The `Remove-Item` command includes the **Recurse** parameter, which deletes the certificates in the store before it deletes the store.</span></span>

```powershell
Invoke-Command { Remove-Item -Path cert:\LocalMachine\TestStore -Recurse } `
  -ComputerName S1, S2
```

## <a name="dynamic-parameters"></a><span data-ttu-id="beaa0-230">Dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="beaa0-230">Dynamic parameters</span></span>

<span data-ttu-id="beaa0-231">Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="beaa0-231">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span> <span data-ttu-id="beaa0-232">Diese Parameter sind in allen Unterverzeichnissen des Zertifikat Anbieters gültig, gelten aber nur für Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="beaa0-232">These parameters are valid in all subdirectories of the Certificate provider, but are effective only on certificates.</span></span>

> [!NOTE]
> <span data-ttu-id="beaa0-233">Parameter, die die Filterung für die Eigenschaft ausführen, `EnhancedKeyUsageList` geben auch Elemente mit einem leeren `EnhancedKeyUsageList` Eigenschafts Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="beaa0-233">Parameters that perform filtering against the `EnhancedKeyUsageList` property also return items with an empty `EnhancedKeyUsageList` property value.</span></span>
> <span data-ttu-id="beaa0-234">Zertifikate, die eine leere **enhancedkeyceist** haben, können für alle Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-234">Certificates that have an empty **EnhancedKeyUsageList** can be used for all purposes.</span></span>

<span data-ttu-id="beaa0-235">Die folgenden Zertifikat Anbieter Parameter wurden in PowerShell 7,1 erneut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-235">The following Certificate provider parameters were reintroduced in PowerShell 7.1.</span></span>

- <span data-ttu-id="beaa0-236">DNSName</span><span class="sxs-lookup"><span data-stu-id="beaa0-236">DNSName</span></span>
- <span data-ttu-id="beaa0-237">DocumentEncryptionCert</span><span class="sxs-lookup"><span data-stu-id="beaa0-237">DocumentEncryptionCert</span></span>
- <span data-ttu-id="beaa0-238">EKU</span><span class="sxs-lookup"><span data-stu-id="beaa0-238">EKU</span></span>
- <span data-ttu-id="beaa0-239">ExpiringInDays</span><span class="sxs-lookup"><span data-stu-id="beaa0-239">ExpiringInDays</span></span>
- <span data-ttu-id="beaa0-240">SSLServerAuthentication</span><span class="sxs-lookup"><span data-stu-id="beaa0-240">SSLServerAuthentication</span></span>

### <a name="codesigningcert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="beaa0-241">CodeSigningCert <System. Management. Automation. Switchparameter></span><span class="sxs-lookup"><span data-stu-id="beaa0-241">CodeSigningCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="beaa0-242">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="beaa0-242">Cmdlets supported</span></span>

- [<span data-ttu-id="beaa0-243">Get-Item</span><span class="sxs-lookup"><span data-stu-id="beaa0-243">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="beaa0-244">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="beaa0-244">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="beaa0-245">Dieser Parameter ruft die Zertifikate ab, die "Code Signing" in Ihrem **enhancedkey-agelist** -Eigenschafts Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-245">This parameter gets certificates that have "Code Signing" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="deletekey-systemmanagementautomationswitchparameter"></a><span data-ttu-id="beaa0-246">DeleteKey <System. Management. Automation. Switchparameter></span><span class="sxs-lookup"><span data-stu-id="beaa0-246">DeleteKey <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="beaa0-247">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="beaa0-247">Cmdlets supported</span></span>

- [<span data-ttu-id="beaa0-248">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="beaa0-248">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

<span data-ttu-id="beaa0-249">Mit diesem Parameter wird der zugehörige private Schlüssel gelöscht, wenn das Zertifikat gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="beaa0-249">This parameter deletes the associated private key when it deletes the certificate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="beaa0-250">Wenn Sie einen privaten Schlüssel löschen möchten, der einem Benutzerzertifikat im `Cert:\CurrentUser` Speicher auf einem Remote Computer zugeordnet ist, müssen Sie Delegierte Anmelde Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-250">To delete a private key that is associated with a user certificate in the `Cert:\CurrentUser` store on a remote computer, you must use delegated credentials.</span></span> <span data-ttu-id="beaa0-251">Das `Invoke-Command` Cmdlet unterstützt die Delegierung von Anmelde Informationen mithilfe des Parameters " **kredssp** ".</span><span class="sxs-lookup"><span data-stu-id="beaa0-251">The `Invoke-Command` cmdlet supports credential delegation using the **CredSSP** parameter.</span></span> <span data-ttu-id="beaa0-252">Vor der Verwendung `Remove-Item` von mit und der Delegierung von Anmelde Informationen sollten Sicherheitsrisiken berücksichtigt werden `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="beaa0-252">You should consider any security risks before using `Remove-Item` with `Invoke-Command` and credential delegation.</span></span>

<span data-ttu-id="beaa0-253">Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-253">This parameter was reintroduced in PowerShell 7.1</span></span>

### <a name="dnsname-microsoftpowershellcommandsdnsnamerepresentation"></a><span data-ttu-id="beaa0-254">DnsName <Microsoft. PowerShell. Commands. dnsnamerepresentation></span><span class="sxs-lookup"><span data-stu-id="beaa0-254">DnsName <Microsoft.PowerShell.Commands.DnsNameRepresentation></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="beaa0-255">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="beaa0-255">Cmdlets supported</span></span>

- [<span data-ttu-id="beaa0-256">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="beaa0-256">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="beaa0-257">Dieser Parameter ruft die Zertifikate ab, die den angegebenen Domänen Namen oder das Namensmuster in der **dnsnamelist** -Eigenschaft des Zertifikats aufweisen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-257">This parameter gets certificates that have the specified domain name or name pattern in the **DNSNameList** property of the certificate.</span></span> <span data-ttu-id="beaa0-258">Der Wert dieses Parameters kann "Unicode" oder "ASCII" lauten.</span><span class="sxs-lookup"><span data-stu-id="beaa0-258">The value of this parameter can either be "Unicode" or "ASCII".</span></span> <span data-ttu-id="beaa0-259">Punycode-Werte werden in Unicode konvertiert.</span><span class="sxs-lookup"><span data-stu-id="beaa0-259">Punycode values are converted to Unicode.</span></span> <span data-ttu-id="beaa0-260">Platzhalter Zeichen ( `*` ) sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="beaa0-260">Wildcard characters (`*`) are permitted.</span></span>

<span data-ttu-id="beaa0-261">Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-261">This parameter was reintroduced in PowerShell 7.1</span></span>

### <a name="documentencryptioncert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="beaa0-262">Documentverschlüsseltioncert <System. Management. Automation. Switchparameter></span><span class="sxs-lookup"><span data-stu-id="beaa0-262">DocumentEncryptionCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="beaa0-263">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="beaa0-263">Cmdlets supported</span></span>

- [<span data-ttu-id="beaa0-264">Get-Item</span><span class="sxs-lookup"><span data-stu-id="beaa0-264">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="beaa0-265">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="beaa0-265">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="beaa0-266">Dieser Parameter ruft die Zertifikate ab, die "Document Encryption" in Ihrem **enhancedkey-agelist** -Eigenschafts Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-266">This parameter gets certificates that have "Document Encryption" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="eku-systemstring"></a><span data-ttu-id="beaa0-267">EKU <System. String></span><span class="sxs-lookup"><span data-stu-id="beaa0-267">EKU <System.String></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="beaa0-268">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="beaa0-268">Cmdlets supported</span></span>

- [<span data-ttu-id="beaa0-269">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="beaa0-269">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="beaa0-270">Dieser Parameter ruft die Zertifikate ab, die den angegebenen Text oder das Textmuster in der- `EnhancedKeyUsageList` Eigenschaft des Zertifikats aufweisen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-270">This parameter gets certificates that have the specified text or text pattern in the `EnhancedKeyUsageList` property of the certificate.</span></span> <span data-ttu-id="beaa0-271">Platzhalter Zeichen ( `*` ) sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="beaa0-271">Wildcard characters (`*`) are permitted.</span></span> <span data-ttu-id="beaa0-272">Die `EnhancedKeyUsageList` -Eigenschaft enthält den anzeigen Amen und die OID-Felder der EKU.</span><span class="sxs-lookup"><span data-stu-id="beaa0-272">The `EnhancedKeyUsageList` property contains the friendly name and the OID fields of the EKU.</span></span>

<span data-ttu-id="beaa0-273">Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-273">This parameter was reintroduced in PowerShell 7.1</span></span>

### <a name="expiringindays-systemint32"></a><span data-ttu-id="beaa0-274">Expiriingindays <System. Int32></span><span class="sxs-lookup"><span data-stu-id="beaa0-274">ExpiringInDays <System.Int32></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="beaa0-275">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="beaa0-275">Cmdlets supported</span></span>

- [<span data-ttu-id="beaa0-276">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="beaa0-276">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="beaa0-277">Dieser Parameter ruft Zertifikate ab, die in oder vor der angegebenen Anzahl von Tagen ablaufen.</span><span class="sxs-lookup"><span data-stu-id="beaa0-277">This parameter gets certificates that are expiring in or before the specified number of days.</span></span> <span data-ttu-id="beaa0-278">Der Wert 0 (Null) ruft die Zertifikate ab, die abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="beaa0-278">A value of 0 (zero) gets certificates that have expired.</span></span>

<span data-ttu-id="beaa0-279">Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-279">This parameter was reintroduced in PowerShell 7.1</span></span>

### <a name="itemtype-string"></a><span data-ttu-id="beaa0-280">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="beaa0-280">ItemType \<String\></span></span>

<span data-ttu-id="beaa0-281">Mit diesem Parameter können Sie den Typ des Elements angeben, das von erstellt wird `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="beaa0-281">This parameter allows you to specify the type of item created by `New-Item`.</span></span>

<span data-ttu-id="beaa0-282">In einem `Certificate` Laufwerk sind folgende Werte zulässig:</span><span class="sxs-lookup"><span data-stu-id="beaa0-282">In a `Certificate` drive, the following values are allowed:</span></span>

- <span data-ttu-id="beaa0-283">Zertifikat-Anbieter</span><span class="sxs-lookup"><span data-stu-id="beaa0-283">Certificate Provider</span></span>
- <span data-ttu-id="beaa0-284">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="beaa0-284">Certificate</span></span>
- <span data-ttu-id="beaa0-285">Speicher</span><span class="sxs-lookup"><span data-stu-id="beaa0-285">Store</span></span>
- <span data-ttu-id="beaa0-286">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="beaa0-286">StoreLocation</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="beaa0-287">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="beaa0-287">Cmdlets Supported</span></span>

- [<span data-ttu-id="beaa0-288">New-Item</span><span class="sxs-lookup"><span data-stu-id="beaa0-288">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sslserverauthentication-systemmanagementautomationswitchparameter"></a><span data-ttu-id="beaa0-289">Sslserverauthentication <System. Management. Automation. Switchparameter></span><span class="sxs-lookup"><span data-stu-id="beaa0-289">SSLServerAuthentication <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="beaa0-290">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="beaa0-290">Cmdlets supported</span></span>

- [<span data-ttu-id="beaa0-291">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="beaa0-291">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="beaa0-292">Ruft nur die Serverzertifikate für SSL-Webhosting ab.</span><span class="sxs-lookup"><span data-stu-id="beaa0-292">Gets only server certificates for SSL web hosting.</span></span> <span data-ttu-id="beaa0-293">Dieser Parameter ruft die Zertifikate ab, die im Eigenschafts Wert "Server Authentifizierung" aufweisen `EnhancedKeyUsageList` .</span><span class="sxs-lookup"><span data-stu-id="beaa0-293">This parameter gets certificates that have "Server Authentication" in their `EnhancedKeyUsageList` property value.</span></span>

<span data-ttu-id="beaa0-294">Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-294">This parameter was reintroduced in PowerShell 7.1</span></span>

## <a name="script-properties"></a><span data-ttu-id="beaa0-295">Skript Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="beaa0-295">Script properties</span></span>

<span data-ttu-id="beaa0-296">Dem **x509Certificate2** -Objekt wurden neue Skript Eigenschaften hinzugefügt, die die Zertifikate darstellen, um das Suchen und Verwalten der Zertifikate zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="beaa0-296">New script properties have been added to the **x509Certificate2** object that represents the certificates to make it easy to search and manage the certificates.</span></span>

- <span data-ttu-id="beaa0-297">`DnsNameList`: Zum Auffüllen der- `DnsNameList` Eigenschaft kopiert der Zertifikat Anbieter den Inhalt aus dem Eintrag "DnsName" in der Erweiterung "subjetalternativename" (San).</span><span class="sxs-lookup"><span data-stu-id="beaa0-297">`DnsNameList`: To populate the `DnsNameList` property, the Certificate provider copies the content from the DNSName entry in the SubjectAlternativeName (SAN) extension.</span></span> <span data-ttu-id="beaa0-298">Wenn die SAN-Erweiterung leer ist, wird die Eigenschaft mit dem Inhalt aus dem Antragstellerfeld des Zertifikats aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="beaa0-298">If the SAN extension is empty, the property is populated with content from the Subject field of the certificate.</span></span>

- <span data-ttu-id="beaa0-299">`EnhancedKeyUsageList`: Zum Auffüllen der- `EnhancedKeyUsageList` Eigenschaft kopiert der Zertifikat Anbieter die OID-Eigenschaften des Felds EnhancedKeyUsage (EKU) im Zertifikat und erstellt einen anzeigen Amen dafür.</span><span class="sxs-lookup"><span data-stu-id="beaa0-299">`EnhancedKeyUsageList`: To populate the `EnhancedKeyUsageList` property, the Certificate provider copies the OID properties of the EnhancedKeyUsage (EKU) field in the certificate and creates a friendly name for it.</span></span>

- <span data-ttu-id="beaa0-300">`SendAsTrustedIssuer`: Zum Auffüllen der- `SendAsTrustedIssuer` Eigenschaft kopiert der Zertifikat Anbieter die- `SendAsTrustedIssuer` Eigenschaft aus dem Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="beaa0-300">`SendAsTrustedIssuer`: To populate the `SendAsTrustedIssuer` property, the Certificate provider copies the `SendAsTrustedIssuer` property from the certificate.</span></span>  <span data-ttu-id="beaa0-301">Weitere Informationen finden Sie [unter Verwaltung vertrauenswürdiger Aussteller für die Client Authentifizierung](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span><span class="sxs-lookup"><span data-stu-id="beaa0-301">For more information see [Management of trusted issuers for client authentication](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span></span>

<span data-ttu-id="beaa0-302">Mit diesen neuen Funktionen können Sie die Zertifikate basierend auf ihren DNS-Namen und Ablaufdaten suchen und Zertifikate für Client- und Server-Authentifizierung durch den Wert der erweiterten Schlüsselverwendung (EKU)-Eigenschaften unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-302">These new features let you search for certificates based on their DNS names and expiration dates, and distinguish client and server authentication certificates by the value of their Enhanced Key Usage (EKU) properties.</span></span>

## <a name="using-the-pipeline"></a><span data-ttu-id="beaa0-303">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="beaa0-303">Using the pipeline</span></span>

<span data-ttu-id="beaa0-304">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="beaa0-304">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="beaa0-305">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="beaa0-305">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="beaa0-306">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="beaa0-306">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="beaa0-307">Hilfe</span><span class="sxs-lookup"><span data-stu-id="beaa0-307">Getting help</span></span>

<span data-ttu-id="beaa0-308">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="beaa0-308">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="beaa0-309">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den- `-Path` Parameter von `Get-Help` , um ein Dateisystem Laufwerk anzugeben.</span><span class="sxs-lookup"><span data-stu-id="beaa0-309">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of `Get-Help` to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path cert:
```

## <a name="see-also"></a><span data-ttu-id="beaa0-310">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="beaa0-310">See also</span></span>

[<span data-ttu-id="beaa0-311">about_Providers</span><span class="sxs-lookup"><span data-stu-id="beaa0-311">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="beaa0-312">about_Signing</span><span class="sxs-lookup"><span data-stu-id="beaa0-312">about_Signing</span></span>](../../Microsoft.PowerShell.Core/About/about_Signing.md)

[<span data-ttu-id="beaa0-313">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="beaa0-313">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)

[<span data-ttu-id="beaa0-314">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="beaa0-314">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[<span data-ttu-id="beaa0-315">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="beaa0-315">Get-PfxCertificate</span></span>](xref:Microsoft.PowerShell.Security.Get-PfxCertificate)
