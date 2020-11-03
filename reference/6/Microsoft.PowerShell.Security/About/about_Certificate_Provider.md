---
description: Zertifikat
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/about/about_certificate_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Zertifikat-Anbieter
ms.openlocfilehash: 6f1c279c0564b116188bbc7a309e7ed5861e42ff
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221039"
---
# <a name="certificate-provider"></a><span data-ttu-id="cb14f-104">Zertifikat-Anbieter</span><span class="sxs-lookup"><span data-stu-id="cb14f-104">Certificate Provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="cb14f-105">Anbietername</span><span class="sxs-lookup"><span data-stu-id="cb14f-105">Provider name</span></span>

<span data-ttu-id="cb14f-106">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="cb14f-106">Certificate</span></span>

## <a name="drives"></a><span data-ttu-id="cb14f-107">Laufwerke</span><span class="sxs-lookup"><span data-stu-id="cb14f-107">Drives</span></span>

`Cert:`

## <a name="capabilities"></a><span data-ttu-id="cb14f-108">Funktionen</span><span class="sxs-lookup"><span data-stu-id="cb14f-108">Capabilities</span></span>

<span data-ttu-id="cb14f-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="cb14f-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="cb14f-110">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb14f-110">Short description</span></span>

<span data-ttu-id="cb14f-111">Ermöglicht den Zugriff auf X. 509-Zertifikat Speicher und-Zertifikate in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb14f-111">Provides access to X.509 certificate stores and certificates in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="cb14f-112">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb14f-112">Detailed description</span></span>

<span data-ttu-id="cb14f-113">Mit dem PowerShell- **Zertifikat** Anbieter können Sie Zertifikate und Zertifikat Speicher in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-113">The PowerShell **Certificate** provider lets you get, add, change, clear, and delete certificates and certificate stores in PowerShell.</span></span>

<span data-ttu-id="cb14f-114">Das **Zertifikat** Laufwerk ist ein hierarchischer Namespace, der die Zertifikat Speicher und Zertifikate auf dem Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="cb14f-114">The **Certificate** drive is a hierarchical namespace containing the certificate stores and certificates on your computer.</span></span>

<span data-ttu-id="cb14f-115">Der **Zertifikat** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-115">The **Certificate** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="cb14f-116">Get-Location</span><span class="sxs-lookup"><span data-stu-id="cb14f-116">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="cb14f-117">Set-Location</span><span class="sxs-lookup"><span data-stu-id="cb14f-117">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="cb14f-118">Get-Item</span><span class="sxs-lookup"><span data-stu-id="cb14f-118">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="cb14f-119">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="cb14f-119">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="cb14f-120">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="cb14f-120">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="cb14f-121">Move-Item</span><span class="sxs-lookup"><span data-stu-id="cb14f-121">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="cb14f-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="cb14f-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="cb14f-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="cb14f-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="cb14f-124">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cb14f-124">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="cb14f-125">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cb14f-125">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="cb14f-126">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="cb14f-126">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="cb14f-127">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="cb14f-127">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [<span data-ttu-id="cb14f-128">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="cb14f-128">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="cb14f-129">Von diesem Anbieter verfügbar gemachte Typen</span><span class="sxs-lookup"><span data-stu-id="cb14f-129">Types exposed by this provider</span></span>

<span data-ttu-id="cb14f-130">Das Zertifikat Laufwerk macht die folgenden Typen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cb14f-130">The Certificate drive exposes the following types.</span></span>

- <span data-ttu-id="cb14f-131">Speicherorte (Microsoft. PowerShell. Commands. X509StoreLocation), bei denen es sich um Container auf hoher Ebene handelt, die die Zertifikate für den aktuellen Benutzer und für alle Benutzer gruppieren.</span><span class="sxs-lookup"><span data-stu-id="cb14f-131">Store locations (Microsoft.PowerShell.Commands.X509StoreLocation), which are high-level containers that group the certificates for the current user and for all users.</span></span> <span data-ttu-id="cb14f-132">Jedes System verfügt über einen CurrentUser- und LocalMachine (alle Benutzer)-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="cb14f-132">Each system has a CurrentUser and LocalMachine (all users) store location.</span></span>

- <span data-ttu-id="cb14f-133">Zertifikate speichern (System. Security. Cryptography. X509Certificates. X509Store), bei denen es sich um physische Speicher handelt, in denen Zertifikate gespeichert und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-133">Certificates stores (System.Security.Cryptography.X509Certificates.X509Store), which are physical stores in which certificates are saved and managed.</span></span>

- <span data-ttu-id="cb14f-134">X. 509 **System. Security. Cryptography. X509Certificates. X509Certificate2** -Zertifikate, von denen jedes ein X. 509-Zertifikat auf dem Computer darstellt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-134">X.509 **System.Security.Cryptography.X509Certificates.X509Certificate2** certificates, each of which represent an X.509 certificate on the computer.</span></span>
  <span data-ttu-id="cb14f-135">Zertifikate werden durch ihre Fingerabdrücke identifiziert.</span><span class="sxs-lookup"><span data-stu-id="cb14f-135">Certificates are identified by their thumbprints.</span></span>

## <a name="navigating-the-certificate-drive"></a><span data-ttu-id="cb14f-136">Navigieren im Zertifikat Laufwerk</span><span class="sxs-lookup"><span data-stu-id="cb14f-136">Navigating the Certificate drive</span></span>

<span data-ttu-id="cb14f-137">Der **Zertifikat Anbieter macht** den Zertifikat Namespace als `Cert:` Laufwerk in PowerShell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cb14f-137">The **Certificate** provider exposes the certificate namespace as the `Cert:` drive in PowerShell.</span></span> <span data-ttu-id="cb14f-138">Dieser Befehl verwendet den- `Set-Location` Befehl, um den aktuellen Speicherort in den Stamm Zertifikat Speicher im LocalMachine-Speicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cb14f-138">This command uses the `Set-Location` command to change the current location to the Root certificate store in the LocalMachine store location.</span></span> <span data-ttu-id="cb14f-139">Verwenden Sie einen umgekehrten Schrägstrich ( \\ ) oder einen Schrägstrich (/), um eine Ebene des `Cert:` Laufwerks anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cb14f-139">Use a backslash (\\) or a forward slash (/) to indicate a level of the `Cert:` drive.</span></span>

```powershell
Set-Location Cert:
```

<span data-ttu-id="cb14f-140">Sie können auch mit dem Zertifikat Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten.</span><span class="sxs-lookup"><span data-stu-id="cb14f-140">You can also work with the certificate provider from any other PowerShell drive.</span></span> <span data-ttu-id="cb14f-141">Um auf einen Alias von einem anderen Speicherort zu verweisen, verwenden Sie den `Cert:` Namen des Laufwerks im Pfad.</span><span class="sxs-lookup"><span data-stu-id="cb14f-141">To reference an alias from another location, use the `Cert:` drive name in the path.</span></span>

```powershell
PS Cert:\> Set-Location -Path LocalMachine\Root
```

<span data-ttu-id="cb14f-142">Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein.</span><span class="sxs-lookup"><span data-stu-id="cb14f-142">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="cb14f-143">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cb14f-143">For example, type:</span></span>

```powershell
Set-Location C:
```

> [!NOTE]
> <span data-ttu-id="cb14f-144">PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten.</span><span class="sxs-lookup"><span data-stu-id="cb14f-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="cb14f-145">Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span><span class="sxs-lookup"><span data-stu-id="cb14f-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span>
> <span data-ttu-id="cb14f-146">und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span><span class="sxs-lookup"><span data-stu-id="cb14f-146">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-contents-of-the-cert-drive"></a><span data-ttu-id="cb14f-147">Anzeigen des Inhalts des CERT:-Laufwerks</span><span class="sxs-lookup"><span data-stu-id="cb14f-147">Displaying the Contents of the Cert: drive</span></span>

<span data-ttu-id="cb14f-148">Dieser Befehl verwendet das `Get-ChildItem` Cmdlet, um die Zertifikat Speicher im Zertifikat Speicherort von CurrentUser anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-148">This command uses the `Get-ChildItem` cmdlet to display the certificate stores in the CurrentUser certificate store location.</span></span>

<span data-ttu-id="cb14f-149">Wenn Sie sich nicht auf dem `Cert:` Laufwerk befinden, verwenden Sie einen absoluten Pfad.</span><span class="sxs-lookup"><span data-stu-id="cb14f-149">If you are not in the `Cert:` drive, use an absolute path.</span></span>

```powershell
PS Cert:\CurrentUser\> Get-ChildItem
```

### <a name="displaying-certificate-properties-within-the-cert-drive"></a><span data-ttu-id="cb14f-150">Anzeigen von Zertifikat Eigenschaften im CERT:-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="cb14f-150">Displaying certificate properties within the Cert: drive</span></span>

<span data-ttu-id="cb14f-151">In diesem Beispiel wird ein Zertifikat mit abgerufen `Get-Item` und in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb14f-151">This example gets a certificate with `Get-Item` and stores it in a variable.</span></span>
<span data-ttu-id="cb14f-152">Das Beispiel zeigt die neuen Zertifikat Skript Eigenschaften ( **dnsnamelist** , **enhancedkeyugeist** **) mithilfe** von `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="cb14f-152">The example shows the new certificate script properties ( **DnsNameList** , **EnhancedKeyUsageList** , **SendAsTrustedIssuer** ) using `Select-Object`.</span></span>

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

### <a name="find-all-codesigning-certificates"></a><span data-ttu-id="cb14f-153">Alle codesigungszertifikate suchen</span><span class="sxs-lookup"><span data-stu-id="cb14f-153">Find all CodeSigning certificates</span></span>

<span data-ttu-id="cb14f-154">Dieser Befehl verwendet die **codeSigningCert** -und **recurse** -Parameter des `Get-ChildItem` Cmdlets, um alle Zertifikate auf dem Computer zu erhalten, die über die Code Signatur Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-154">This command uses the **CodeSigningCert** and **Recurse** parameters of the `Get-ChildItem` cmdlet to get all of the certificates on the computer that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path cert: -CodeSigningCert -Recurse
```

### <a name="find-expired-certificates"></a><span data-ttu-id="cb14f-155">Abgelaufene Zertifikate suchen</span><span class="sxs-lookup"><span data-stu-id="cb14f-155">Find expired certificates</span></span>

<span data-ttu-id="cb14f-156">Mit diesem Befehl wird der **expiriingindays** -Parameter des `Get-ChildItem` Cmdlets verwendet, um Zertifikate zu erhalten, die innerhalb der nächsten 30 Tage ablaufen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-156">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet to get certificates that will expire within the next 30 days.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\WebHosting -ExpiringInDays 30
```

### <a name="find-server-ssl-certificates"></a><span data-ttu-id="cb14f-157">Suchen von Server-SSL-Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="cb14f-157">Find Server SSL Certificates</span></span>

<span data-ttu-id="cb14f-158">Dieser Befehl verwendet den **sslserverauthentication** -Parameter des `Get-ChildItem` Cmdlets, um alle Server-SSL-Zertifikate im My-und Webhosting-Speicher zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cb14f-158">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get all Server SSL Certificates in the My and WebHosting stores.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine\My, cert:\LocalMachine\WebHosting `
  -SSLServerAuthentication
```

### <a name="find-expired-certificates-on-remote-computers"></a><span data-ttu-id="cb14f-159">Suchen abgelaufener Zertifikate auf Remote Computern</span><span class="sxs-lookup"><span data-stu-id="cb14f-159">Find expired certificates on remote computers</span></span>

<span data-ttu-id="cb14f-160">Dieser Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Get-ChildItem` Befehls auf den Computern SRV01 und Srv02.</span><span class="sxs-lookup"><span data-stu-id="cb14f-160">This command uses the `Invoke-Command` cmdlet to run a `Get-ChildItem` command on the Srv01 and Srv02 computers.</span></span> <span data-ttu-id="cb14f-161">Der Wert NULL (0) im **expiriingindays** -Parameter ruft Zertifikate auf den Computern SRV01 und Srv02 ab, die abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="cb14f-161">A value of zero (0) in the **ExpiringInDays** parameter gets certificates on the Srv01 and Srv02 computers that have expired.</span></span>

```powershell
Invoke-Command -ComputerName Srv01, Srv02 {Get-ChildItem -Path cert:\* `
  -Recurse -ExpiringInDays 0}
```

### <a name="combining-filters-to-find-a-specific-set-of-certificates"></a><span data-ttu-id="cb14f-162">Kombinieren von Filtern für die Suche nach einem bestimmten Satz von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="cb14f-162">Combining filters to find a specific set of certificates</span></span>

<span data-ttu-id="cb14f-163">Mit diesem Befehl werden alle Zertifikate im LocalMachine-Speicherort abgerufen, die die folgenden Attribute aufweisen:</span><span class="sxs-lookup"><span data-stu-id="cb14f-163">This command gets all certificates in the LocalMachine store location that have the following attributes:</span></span>

- <span data-ttu-id="cb14f-164">"Fabrikam" im DNS-Namen</span><span class="sxs-lookup"><span data-stu-id="cb14f-164">"fabrikam" in their DNS name</span></span>
- <span data-ttu-id="cb14f-165">"Client Authentifizierung" in der EKU</span><span class="sxs-lookup"><span data-stu-id="cb14f-165">"Client Authentication" in their EKU</span></span>
- <span data-ttu-id="cb14f-166">der Wert `$true` für die **sendastrusteabschrecker** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cb14f-166">a value of `$true` for the **SendAsTrustedIssuer** property</span></span>
- <span data-ttu-id="cb14f-167">läuft nicht innerhalb der nächsten 30 Tage ab.</span><span class="sxs-lookup"><span data-stu-id="cb14f-167">do not expire within the next 30 days.</span></span>

<span data-ttu-id="cb14f-168">Die **NotAfter** -Eigenschaft speichert das Ablaufdatum des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="cb14f-168">The **NotAfter** property stores the certificate expiration date.</span></span>

```powershell
[DateTime] $ValidThrough = (Get-Date) + (New-TimeSpan -Days 30)
Get-ChildItem -Path cert:\* -Recurse -DNSName "*fabrikam*" `
  -EKU "*Client Authentication*" | Where-Object {
                                     $_.SendAsTrustedIssuer -and `
                                     $_.NotAfter -gt $ValidThrough
                                   }
```

## <a name="opening-the-certificates-mmc-snap-in"></a><span data-ttu-id="cb14f-169">Öffnen des Zertifikate-MMC-Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="cb14f-169">Opening the Certificates MMC Snap-in</span></span>

<span data-ttu-id="cb14f-170">Mit dem- `Invoke-Item` Cmdlet wird die Standardanwendung verwendet, um einen von Ihnen angegebenen Pfad zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-170">The `Invoke-Item` cmdlet will use the default application to open a path you specify.</span></span> <span data-ttu-id="cb14f-171">Bei Zertifikaten ist die Standardanwendung das MMC-Snap-in "Zertifikate".</span><span class="sxs-lookup"><span data-stu-id="cb14f-171">For certificates, the default application is the Certificates MMC snap-in.</span></span>

<span data-ttu-id="cb14f-172">Dieser Befehl öffnet das Zertifikate-MMC-Snap-In zum Verwalten des angegebenen Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="cb14f-172">This command opens the Certificates MMC snap-in to manage the specified certificate.</span></span>

```powershell
Invoke-Item cert:\CurrentUser\my\6B8223358119BB08840DEE50FD8AF9EA776CE66B
```

## <a name="copying-certificates"></a><span data-ttu-id="cb14f-173">Kopieren von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="cb14f-173">Copying Certificates</span></span>

<span data-ttu-id="cb14f-174">Das Kopieren von Zertifikaten wird vom **Zertifikat** Anbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-174">Copying certificates is not supported by the **Certificate** provider.</span></span> <span data-ttu-id="cb14f-175">Wenn Sie versuchen, ein Zertifikat zu kopieren, wird dieser Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-175">When you attempt to copy a certificate, you see this error.</span></span>

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

## <a name="moving-certificates"></a><span data-ttu-id="cb14f-176">Verschieben von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="cb14f-176">Moving Certificates</span></span>

### <a name="move-all-ssl-server-authentication-certs-to-the-webhosting-store"></a><span data-ttu-id="cb14f-177">Verschieben aller Zertifikate der SSL-Server Authentifizierung in den Webhosting-Speicher</span><span class="sxs-lookup"><span data-stu-id="cb14f-177">Move all SSL Server authentication certs to the WebHosting store</span></span>

<span data-ttu-id="cb14f-178">Dieser Befehl verwendet das `Move-Item` Cmdlet, um ein Zertifikat aus dem eigenen Speicher in den Webhosting-Speicher zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="cb14f-178">This command uses the `Move-Item` cmdlet to move a certificate from the My store to the WebHosting store.</span></span>

<span data-ttu-id="cb14f-179">`Move-Item` von werden keine Zertifikat Speicher verschoben, und Zertifikate werden nicht an einen anderen Speicherort verschoben, z. b. das Verschieben eines Zertifikats von LocalMachine nach CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="cb14f-179">`Move-Item` will not move certificate stores and it will not move certificates to a different store location, such as moving a certificate from LocalMachine to CurrentUser.</span></span> <span data-ttu-id="cb14f-180">Das `Move-Item` Cmdlet verschiebt Zertifikate, aber keine privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="cb14f-180">The `Move-Item` cmdlet moves certificates, but it does not move private keys.</span></span>

<span data-ttu-id="cb14f-181">Dieser Befehl verwendet den **sslserverauthentication** -Parameter des `Get-ChildItem` Cmdlets, um SSL-Server Authentifizierungs Zertifikate im My-Zertifikat Speicher zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cb14f-181">This command uses the **SSLServerAuthentication** parameter of the `Get-ChildItem` cmdlet to get SSL server authentication certificates in the MY certificate store.</span></span>

<span data-ttu-id="cb14f-182">Die zurückgegebenen Zertifikate werden an das `Move-Item` Cmdlet weitergeleitet, wodurch die Zertifikate in den Webhosting-Speicher verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-182">The returned certificates are piped to the `Move-Item` cmdlet, which moves the certificates to the WebHosting store.</span></span>

```powershell
Get-ChildItem cert:\LocalMachine\My -SSLServerAuthentication | Move-Item `
  -Destination cert:\LocalMachine\WebHosting
```

## <a name="deleting-certificates-and-private-keys"></a><span data-ttu-id="cb14f-183">Löschen von Zertifikaten und privaten Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="cb14f-183">Deleting Certificates and Private Keys</span></span>

<span data-ttu-id="cb14f-184">Mit dem- `Remove-Item` Cmdlet werden von Ihnen angegebene Zertifikate entfernt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-184">The `Remove-Item` cmdlet will remove certificates that you specify.</span></span> <span data-ttu-id="cb14f-185">Der `-DeleteKey` dynamische Parameter löscht den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="cb14f-185">The `-DeleteKey` dynamic parameter deletes the private key.</span></span>

### <a name="delete-a-certificate-from-the-ca-store"></a><span data-ttu-id="cb14f-186">Löschen eines Zertifikats aus dem ca-Speicher</span><span class="sxs-lookup"><span data-stu-id="cb14f-186">Delete a Certificate from the CA store</span></span>

<span data-ttu-id="cb14f-187">Dieser Befehl löscht ein Zertifikat aus dem CA-Zertifikatspeicher, lässt jedoch den zugehörigen privaten Schlüssel intakt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-187">This command deletes a certificate from the CA certificate store, but leaves the associated private key intact.</span></span>

<span data-ttu-id="cb14f-188">Im- `Cert:` Laufwerk `Remove-Item` unterstützt das Cmdlet nur die **Parameter DeleteKey** , **path** , **WhatIf** und **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="cb14f-188">In the `Cert:` drive, the `Remove-Item` cmdlet supports only the **DeleteKey** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="cb14f-189">Alle anderen Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cb14f-189">All other parameters are ignored.</span></span>

```powershell
Remove-Item cert:\LocalMachine\CA\5DDC44652E62BF9AA1116DC41DE44AB47C87BDD0
```

### <a name="delete-a-certificate-using-a-wildcards-in-the-dns-name"></a><span data-ttu-id="cb14f-190">Löschen eines Zertifikats mithilfe von Platzhaltern im DNS-Namen</span><span class="sxs-lookup"><span data-stu-id="cb14f-190">Delete a Certificate using a wildcards in the DNS name</span></span>

<span data-ttu-id="cb14f-191">Dieser Befehl löscht alle Zertifikate, deren DNS-Name "Fabrikam" enthält.</span><span class="sxs-lookup"><span data-stu-id="cb14f-191">This command deletes all certificates that have a DNS name that contains "Fabrikam".</span></span> <span data-ttu-id="cb14f-192">Er verwendet den **DnsName** -Parameter des `Get-ChildItem` Cmdlets, um die Zertifikate zu erhalten, und das `Remove-Item` Cmdlet, um Sie zu löschen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-192">It uses the **DNSName** parameter of the `Get-ChildItem` cmdlet to get the certificates and the `Remove-Item` cmdlet to delete them.</span></span>

```powershell
Get-ChildItem -Path cert:\LocalMachine -DnsName *Fabrikam* | Remove-Item
```

### <a name="delete-private-keys-from-a-remote-computer"></a><span data-ttu-id="cb14f-193">Löschen von privaten Schlüsseln von einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="cb14f-193">Delete private keys from a remote computer</span></span>

<span data-ttu-id="cb14f-194">Diese Reihe von Befehlen ermöglicht die Delegation und löscht dann das Zertifikat und den zugehörigen privaten Schlüssel auf einem Remotecomputer.</span><span class="sxs-lookup"><span data-stu-id="cb14f-194">This series of commands enables delegation and then deletes the certificate and associated private key on a remote computer.</span></span> <span data-ttu-id="cb14f-195">Um einen privaten Schlüssel auf einem Remotecomputer zu löschen, müssen Sie die delegierten Anmeldeinformationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-195">To delete a private key on a remote computer, you must use delegated credentials.</span></span>

<span data-ttu-id="cb14f-196">Verwenden Sie das- `Enable-WSManCredSSP` Cmdlet, um die Authentifizierung für den Anmelde Informationsdienst (Security Service Provider, kredssp) auf einem Client auf dem Remote Computer S1 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb14f-196">Use the `Enable-WSManCredSSP` cmdlet to enable Credential Security Service Provider (CredSSP) authentication on a client on the S1 remote computer.</span></span>
<span data-ttu-id="cb14f-197">CredSSP ermöglicht die delegierte Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="cb14f-197">CredSSP permits delegated authentication.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer S1
```

<span data-ttu-id="cb14f-198">Verwenden `Connect-WSMan` Sie das Cmdlet, um den Computer S1 mit dem WinRM-Dienst auf dem lokalen Computer zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-198">Use the `Connect-WSMan` cmdlet to connect the S1 computer to the WinRM service on the local computer.</span></span> <span data-ttu-id="cb14f-199">Wenn dieser Befehl abgeschlossen ist, wird der S1-Computer auf dem lokalen `WSMan:` Laufwerk in PowerShell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-199">When this command completes, the S1 computer appears in the local `WSMan:` drive in PowerShell.</span></span>

```powershell
Connect-WSMan -ComputerName S1 -Credential Domain01\Admin01
```

<span data-ttu-id="cb14f-200">Nun können Sie das Cmdlet "Set-Item" im WSMAN:-Laufwerk verwenden, um das Attribut "Attribut" für den WinRM-Dienst zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb14f-200">Now, you can use the Set-Item cmdlet in the WSMan: drive to enable the CredSSP attribute for the WinRM service.</span></span>

```powershell
Set-Item -Path WSMan:\S1\Service\Auth\CredSSP -Value $true
```

<span data-ttu-id="cb14f-201">Starten Sie mithilfe des Cmdlets eine Remote Sitzung auf dem Computer S1 `New-PSSession` , und geben Sie die Authentifizierung für die Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="cb14f-201">Start a remote session on the s1 computer using the `New-PSSession` cmdlet, and specify CredSSP authentication.</span></span> <span data-ttu-id="cb14f-202">Speichert die Sitzung in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-202">Saves the session in the `$s` variable.</span></span>

```powershell
$s  = New-PSSession S1 -Authentication CredSSP -Credential Domain01\Admin01
```

<span data-ttu-id="cb14f-203">Verwenden Sie abschließend das `Invoke-Command` Cmdlet, um einen `Remove-Item` Befehl in der Sitzung in der `$s` Variablen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-203">Finally, use the `Invoke-Command` cmdlet to run a `Remove-Item` command in the session in the `$s` variable.</span></span> <span data-ttu-id="cb14f-204">Der `Remove-Item` Befehl verwendet den **DeleteKey** -Parameter, um den privaten Schlüssel zusammen mit dem angegebenen Zertifikat zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-204">The `Remove-Item` command uses the **DeleteKey** parameter to remove the private key along with the specified certificate.</span></span>

```powershell
Invoke-Command -Session $s { Remove-Item `
  -Path cert:\LocalMachine\My\D2D38EBA60CAA1C12055A2E1C83B15AD450110C2 `
  -DeleteKey
  }
```

### <a name="delete-expired-certificates"></a><span data-ttu-id="cb14f-205">Abgelaufene Zertifikate löschen</span><span class="sxs-lookup"><span data-stu-id="cb14f-205">Delete expired Certificates</span></span>

<span data-ttu-id="cb14f-206">Dieser Befehl verwendet den **expiriingindays** -Parameter des `Get-ChildItem` Cmdlets mit dem Wert 0, um Zertifikate im Webhosting-Speicher zu erhalten, die abgelaufen sind.</span><span class="sxs-lookup"><span data-stu-id="cb14f-206">This command uses the **ExpiringInDays** parameter of the `Get-ChildItem` cmdlet with a value of 0 to get certificates in the WebHosting store that have expired.</span></span>

<span data-ttu-id="cb14f-207">Die Variable, die die zurückgegebenen Zertifikate enthält, wird an das `Remove-Item` Cmdlet weitergeleitet, wodurch Sie gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-207">The variable containing the returned certificates is piped to the `Remove-Item` cmdlet, which deletes them.</span></span> <span data-ttu-id="cb14f-208">Der Befehl verwendet den **DeleteKey** -Parameter, um den privaten Schlüssel zusammen mit dem Zertifikat zu löschen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-208">The command uses the **DeleteKey** parameter to delete the private key along with the certificate.</span></span>

```powershell
$expired = Get-ChildItem cert:\LocalMachine\WebHosting -ExpiringInDays 0
$expired | Remove-Item -DeleteKey
```

## <a name="creating-certificates"></a><span data-ttu-id="cb14f-209">Erstellen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="cb14f-209">Creating Certificates</span></span>

<span data-ttu-id="cb14f-210">Mit dem- `New-Item` Cmdlet werden keine neuen Zertifikate im **Zertifikat** Anbieter erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-210">The `New-Item` cmdlet does not create new certificates in the **Certificate** provider.</span></span> <span data-ttu-id="cb14f-211">Verwenden Sie das Cmdlet [New-selfsignedcertificate](/powershell/module/pkiclient/new-selfsignedcertificate) , um ein Zertifikat zu Testzwecken zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-211">Use the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet to create a certificate for testing purposes.</span></span>

## <a name="creating-certificate-stores"></a><span data-ttu-id="cb14f-212">Erstellen von Zertifikatspeichern</span><span class="sxs-lookup"><span data-stu-id="cb14f-212">Creating Certificate Stores</span></span>

<span data-ttu-id="cb14f-213">Im CERT:-Laufwerk erstellt das `New-Item` Cmdlet Zertifikat Speicher am LocalMachine-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="cb14f-213">In the Cert: drive, the `New-Item` cmdlet creates certificate stores in the LocalMachine store location.</span></span> <span data-ttu-id="cb14f-214">Er unterstützt die Parameter **Name** , **path** , **WhatIf** und **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="cb14f-214">It supports the **Name** , **Path** , **WhatIf** , and **Confirm** parameters.</span></span> <span data-ttu-id="cb14f-215">Alle anderen Parameter werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cb14f-215">All other parameters are ignored.</span></span> <span data-ttu-id="cb14f-216">Der Befehl gibt eine **System. Security. Cryptography. X509Certificates. X509Store** zurück, die den neuen Zertifikat Speicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-216">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

<span data-ttu-id="cb14f-217">Dieser Befehl erstellt einen neuen Zertifikatspeicher mit dem Namen "CustomStore" am Speicherort des LocalMachine-Speichers.</span><span class="sxs-lookup"><span data-stu-id="cb14f-217">This command creates a new certificate store named "CustomStore" in the LocalMachine store location.</span></span>

```powershell
New-Item -Path cert:\LocalMachine\CustomStore
```

### <a name="create-a-new-certificate-store-on-a-remote-computer"></a><span data-ttu-id="cb14f-218">Erstellen eines neuen Zertifikat Speicher auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="cb14f-218">Create a new certificate store on a remote computer</span></span>

<span data-ttu-id="cb14f-219">Dieser Befehl erstellt einen neuen Zertifikatspeicher mit dem Namen "HostingStore" am LocalMachine-Speicherort auf dem Computer Server01.</span><span class="sxs-lookup"><span data-stu-id="cb14f-219">This command creates a new certificate store named "HostingStore" in the LocalMachine store location on the Server01 computer.</span></span>

<span data-ttu-id="cb14f-220">Der Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `New-Item` Befehls auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="cb14f-220">The command uses the `Invoke-Command` cmdlet to run a `New-Item` command on the Server01 computer.</span></span> <span data-ttu-id="cb14f-221">Der Befehl gibt eine **System. Security. Cryptography. X509Certificates. X509Store** zurück, die den neuen Zertifikat Speicher darstellt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-221">The command returns a **System.Security.Cryptography.X509Certificates.X509Store** that represents the new certificate store.</span></span>

```powershell
Invoke-Command { New-Item -Path cert:\LocalMachine\CustomStore } `
  -ComputerName Server01
```

## <a name="creating-client-certificates-for-ws-man"></a><span data-ttu-id="cb14f-222">Erstellen von Client Zertifikaten für WS-Man</span><span class="sxs-lookup"><span data-stu-id="cb14f-222">Creating Client Certificates for WS-Man</span></span>

<span data-ttu-id="cb14f-223">Mit diesem Befehl wird der **ClientCertificate** -Eintrag erstellt, der vom **WS-Management** -Client verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb14f-223">This command creates **ClientCertificate** entry that can be used by the **WS-Management** client.</span></span> <span data-ttu-id="cb14f-224">Das neue **ClientCertificate** wird unter dem Verzeichnis " **ClientCertificate** " als "ClientCertificate_1234567890" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-224">The new **ClientCertificate** will show up under the **ClientCertificate** directory as "ClientCertificate_1234567890".</span></span> <span data-ttu-id="cb14f-225">Alle Parameter müssen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-225">All of the parameters are mandatory.</span></span> <span data-ttu-id="cb14f-226">Der **Aussteller** muss den Fingerabdruck des Aussteller Zertifikats aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-226">The **Issuer** needs to be thumbprint of the issuers certificate.</span></span>

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* -Credential $cred
```

## <a name="deleting-certificate-stores"></a><span data-ttu-id="cb14f-227">Löschen von Zertifikatspeichern</span><span class="sxs-lookup"><span data-stu-id="cb14f-227">Deleting Certificate Stores</span></span>

### <a name="delete-a-certificate-store-from-a-remote-computer"></a><span data-ttu-id="cb14f-228">Löschen eines Zertifikat Speicher von einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="cb14f-228">Delete a certificate store from a remote computer</span></span>

<span data-ttu-id="cb14f-229">Dieser Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Remove-Item` Befehls auf den Computern S1 und S2.</span><span class="sxs-lookup"><span data-stu-id="cb14f-229">This command uses the `Invoke-Command` cmdlet to run a `Remove-Item` command on the S1 and S2 computers.</span></span> <span data-ttu-id="cb14f-230">Der `Remove-Item` Befehl enthält den **recurse** -Parameter, mit dem die Zertifikate im Speicher gelöscht werden, bevor der Speicher gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="cb14f-230">The `Remove-Item` command includes the **Recurse** parameter, which deletes the certificates in the store before it deletes the store.</span></span>

```powershell
Invoke-Command { Remove-Item -Path cert:\LocalMachine\TestStore -Recurse } `
  -ComputerName S1, S2
```

## <a name="dynamic-parameters"></a><span data-ttu-id="cb14f-231">Dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="cb14f-231">Dynamic parameters</span></span>

<span data-ttu-id="cb14f-232">Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cb14f-232">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span> <span data-ttu-id="cb14f-233">Diese Parameter sind in allen Unterverzeichnissen des Zertifikat Anbieters gültig, gelten aber nur für Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="cb14f-233">These parameters are valid in all subdirectories of the Certificate provider, but are effective only on certificates.</span></span>

> [!NOTE]
> <span data-ttu-id="cb14f-234">Parameter, die die Filterung für die Eigenschaft ausführen, `EnhancedKeyUsageList` geben auch Elemente mit einem leeren `EnhancedKeyUsageList` Eigenschafts Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="cb14f-234">Parameters that perform filtering against the `EnhancedKeyUsageList` property also return items with an empty `EnhancedKeyUsageList` property value.</span></span>
> <span data-ttu-id="cb14f-235">Zertifikate, die eine leere **enhancedkeyceist** haben, können für alle Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-235">Certificates that have an empty **EnhancedKeyUsageList** can be used for all purposes.</span></span>

<span data-ttu-id="cb14f-236">Die folgenden Zertifikat Anbieter Parameter wurden in PowerShell 6,0 entfernt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-236">The following Certificate provider parameters were removed in PowerShell 6.0.</span></span>

- <span data-ttu-id="cb14f-237">DNSName</span><span class="sxs-lookup"><span data-stu-id="cb14f-237">DNSName</span></span>
- <span data-ttu-id="cb14f-238">DocumentEncryptionCert</span><span class="sxs-lookup"><span data-stu-id="cb14f-238">DocumentEncryptionCert</span></span>
- <span data-ttu-id="cb14f-239">EKU</span><span class="sxs-lookup"><span data-stu-id="cb14f-239">EKU</span></span>
- <span data-ttu-id="cb14f-240">ExpiringInDays</span><span class="sxs-lookup"><span data-stu-id="cb14f-240">ExpiringInDays</span></span>
- <span data-ttu-id="cb14f-241">SSLServerAuthentication</span><span class="sxs-lookup"><span data-stu-id="cb14f-241">SSLServerAuthentication</span></span>

### <a name="codesigningcert-systemmanagementautomationswitchparameter"></a><span data-ttu-id="cb14f-242">CodeSigningCert <System. Management. Automation. Switchparameter></span><span class="sxs-lookup"><span data-stu-id="cb14f-242">CodeSigningCert <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="cb14f-243">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cb14f-243">Cmdlets supported</span></span>

- [<span data-ttu-id="cb14f-244">Get-Item</span><span class="sxs-lookup"><span data-stu-id="cb14f-244">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

- [<span data-ttu-id="cb14f-245">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="cb14f-245">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

<span data-ttu-id="cb14f-246">Dieser Parameter ruft die Zertifikate ab, die "Code Signing" in Ihrem **enhancedkey-agelist** -Eigenschafts Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-246">This parameter gets certificates that have "Code Signing" in their **EnhancedKeyUsageList** property value.</span></span>

### <a name="deletekey-systemmanagementautomationswitchparameter"></a><span data-ttu-id="cb14f-247">DeleteKey <System. Management. Automation. Switchparameter></span><span class="sxs-lookup"><span data-stu-id="cb14f-247">DeleteKey <System.Management.Automation.SwitchParameter></span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="cb14f-248">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cb14f-248">Cmdlets supported</span></span>

- [<span data-ttu-id="cb14f-249">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="cb14f-249">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)

<span data-ttu-id="cb14f-250">Mit diesem Parameter wird der zugehörige private Schlüssel gelöscht, wenn das Zertifikat gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="cb14f-250">This parameter deletes the associated private key when it deletes the certificate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb14f-251">Wenn Sie einen privaten Schlüssel löschen möchten, der einem Benutzerzertifikat im `Cert:\CurrentUser` Speicher auf einem Remote Computer zugeordnet ist, müssen Sie Delegierte Anmelde Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-251">To delete a private key that is associated with a user certificate in the `Cert:\CurrentUser` store on a remote computer, you must use delegated credentials.</span></span> <span data-ttu-id="cb14f-252">Das `Invoke-Command` Cmdlet unterstützt die Delegierung von Anmelde Informationen mithilfe des Parameters " **kredssp** ".</span><span class="sxs-lookup"><span data-stu-id="cb14f-252">The `Invoke-Command` cmdlet supports credential delegation using the **CredSSP** parameter.</span></span> <span data-ttu-id="cb14f-253">Vor der Verwendung `Remove-Item` von mit und der Delegierung von Anmelde Informationen sollten Sicherheitsrisiken berücksichtigt werden `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="cb14f-253">You should consider any security risks before using `Remove-Item` with `Invoke-Command` and credential delegation.</span></span>

<span data-ttu-id="cb14f-254">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-254">This parameter was introduced in Windows PowerShell 3.0.</span></span>

### <a name="itemtype-string"></a><span data-ttu-id="cb14f-255">ItemType \<String\></span><span class="sxs-lookup"><span data-stu-id="cb14f-255">ItemType \<String\></span></span>

<span data-ttu-id="cb14f-256">Mit diesem Parameter können Sie den Typ des Elements angeben, das von erstellt wird `New-Item` .</span><span class="sxs-lookup"><span data-stu-id="cb14f-256">This parameter allows you to specify the type of item created by `New-Item`.</span></span>

<span data-ttu-id="cb14f-257">In einem `Certificate` Laufwerk sind folgende Werte zulässig:</span><span class="sxs-lookup"><span data-stu-id="cb14f-257">In a `Certificate` drive, the following values are allowed:</span></span>

- <span data-ttu-id="cb14f-258">Zertifikat-Anbieter</span><span class="sxs-lookup"><span data-stu-id="cb14f-258">Certificate Provider</span></span>
- <span data-ttu-id="cb14f-259">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="cb14f-259">Certificate</span></span>
- <span data-ttu-id="cb14f-260">Speicher</span><span class="sxs-lookup"><span data-stu-id="cb14f-260">Store</span></span>
- <span data-ttu-id="cb14f-261">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="cb14f-261">StoreLocation</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="cb14f-262">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cb14f-262">Cmdlets Supported</span></span>

- [<span data-ttu-id="cb14f-263">New-Item</span><span class="sxs-lookup"><span data-stu-id="cb14f-263">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

## <a name="script-properties"></a><span data-ttu-id="cb14f-264">Skript Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb14f-264">Script properties</span></span>

<span data-ttu-id="cb14f-265">Dem **x509Certificate2** -Objekt wurden neue Skript Eigenschaften hinzugefügt, die die Zertifikate darstellen, um das Suchen und Verwalten der Zertifikate zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="cb14f-265">New script properties have been added to the **x509Certificate2** object that represents the certificates to make it easy to search and manage the certificates.</span></span>

- <span data-ttu-id="cb14f-266">`DnsNameList`: Zum Auffüllen der- `DnsNameList` Eigenschaft kopiert der Zertifikat Anbieter den Inhalt aus dem Eintrag "DnsName" in der Erweiterung "subjetalternativename" (San).</span><span class="sxs-lookup"><span data-stu-id="cb14f-266">`DnsNameList`: To populate the `DnsNameList` property, the Certificate provider copies the content from the DNSName entry in the SubjectAlternativeName (SAN) extension.</span></span> <span data-ttu-id="cb14f-267">Wenn die SAN-Erweiterung leer ist, wird die Eigenschaft mit dem Inhalt aus dem Antragstellerfeld des Zertifikats aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="cb14f-267">If the SAN extension is empty, the property is populated with content from the Subject field of the certificate.</span></span>

- <span data-ttu-id="cb14f-268">`EnhancedKeyUsageList`: Zum Auffüllen der- `EnhancedKeyUsageList` Eigenschaft kopiert der Zertifikat Anbieter die OID-Eigenschaften des Felds EnhancedKeyUsage (EKU) im Zertifikat und erstellt einen anzeigen Amen dafür.</span><span class="sxs-lookup"><span data-stu-id="cb14f-268">`EnhancedKeyUsageList`: To populate the `EnhancedKeyUsageList` property, the Certificate provider copies the OID properties of the EnhancedKeyUsage (EKU) field in the certificate and creates a friendly name for it.</span></span>

- <span data-ttu-id="cb14f-269">`SendAsTrustedIssuer`: Zum Auffüllen der- `SendAsTrustedIssuer` Eigenschaft kopiert der Zertifikat Anbieter die- `SendAsTrustedIssuer` Eigenschaft aus dem Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="cb14f-269">`SendAsTrustedIssuer`: To populate the `SendAsTrustedIssuer` property, the Certificate provider copies the `SendAsTrustedIssuer` property from the certificate.</span></span>  <span data-ttu-id="cb14f-270">Weitere Informationen finden Sie [unter Verwaltung vertrauenswürdiger Aussteller für die Client Authentifizierung](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span><span class="sxs-lookup"><span data-stu-id="cb14f-270">For more information see [Management of trusted issuers for client authentication](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).</span></span>

<span data-ttu-id="cb14f-271">Mit diesen neuen Funktionen können Sie die Zertifikate basierend auf ihren DNS-Namen und Ablaufdaten suchen und Zertifikate für Client- und Server-Authentifizierung durch den Wert der erweiterten Schlüsselverwendung (EKU)-Eigenschaften unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-271">These new features let you search for certificates based on their DNS names and expiration dates, and distinguish client and server authentication certificates by the value of their Enhanced Key Usage (EKU) properties.</span></span>

## <a name="using-the-pipeline"></a><span data-ttu-id="cb14f-272">Verwenden der Pipeline</span><span class="sxs-lookup"><span data-stu-id="cb14f-272">Using the pipeline</span></span>

<span data-ttu-id="cb14f-273">Anbieter-Cmdlets akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="cb14f-273">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="cb14f-274">Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-274">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="cb14f-275">Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="cb14f-275">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="cb14f-276">Hilfe</span><span class="sxs-lookup"><span data-stu-id="cb14f-276">Getting help</span></span>

<span data-ttu-id="cb14f-277">Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.</span><span class="sxs-lookup"><span data-stu-id="cb14f-277">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="cb14f-278">Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den- `-Path` Parameter von `Get-Help` , um ein Dateisystem Laufwerk anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cb14f-278">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of `Get-Help` to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path cert:
```

## <a name="see-also"></a><span data-ttu-id="cb14f-279">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="cb14f-279">See also</span></span>

[<span data-ttu-id="cb14f-280">about_Providers</span><span class="sxs-lookup"><span data-stu-id="cb14f-280">about_Providers</span></span>](../../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="cb14f-281">about_Signing</span><span class="sxs-lookup"><span data-stu-id="cb14f-281">about_Signing</span></span>](../../Microsoft.PowerShell.Core/About/about_Signing.md)

[<span data-ttu-id="cb14f-282">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="cb14f-282">Get-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)

[<span data-ttu-id="cb14f-283">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="cb14f-283">Set-AuthenticodeSignature</span></span>](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[<span data-ttu-id="cb14f-284">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="cb14f-284">Get-PfxCertificate</span></span>](xref:Microsoft.PowerShell.Security.Get-PfxCertificate)
