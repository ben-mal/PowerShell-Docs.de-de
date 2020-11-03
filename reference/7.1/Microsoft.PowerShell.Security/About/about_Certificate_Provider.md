---
description: Zertifikat
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/about/about_certificate_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Zertifikat-Anbieter
ms.openlocfilehash: 6d78c587f79bb09c66700fb71519fe0f32318386
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223956"
---
# <a name="certificate-provider"></a>Zertifikat-Anbieter

## <a name="provider-name"></a>Anbietername

Zertifikat

## <a name="drives"></a>Laufwerke

`Cert:`

## <a name="capabilities"></a>Funktionen

**ShouldProcess**

## <a name="short-description"></a>Kurze Beschreibung

Ermöglicht den Zugriff auf X. 509-Zertifikat Speicher und-Zertifikate in PowerShell.

## <a name="detailed-description"></a>Detaillierte Beschreibung

Mit dem PowerShell- **Zertifikat** Anbieter können Sie Zertifikate und Zertifikat Speicher in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.

Das **Zertifikat** Laufwerk ist ein hierarchischer Namespace, der die Zertifikat Speicher und Zertifikate auf dem Computer enthält.

Der **Zertifikat** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [Invoke-Item](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [Move-Item](xref:Microsoft.PowerShell.Management.Move-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Get-ItemProperty](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Clear-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [Get-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)
- [Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

## <a name="types-exposed-by-this-provider"></a>Von diesem Anbieter verfügbar gemachte Typen

Das Zertifikat Laufwerk macht die folgenden Typen verfügbar.

- Speicherorte (Microsoft. PowerShell. Commands. X509StoreLocation), bei denen es sich um Container auf hoher Ebene handelt, die die Zertifikate für den aktuellen Benutzer und für alle Benutzer gruppieren. Jedes System verfügt über einen CurrentUser- und LocalMachine (alle Benutzer)-Speicherort.

- Zertifikate speichern (System. Security. Cryptography. X509Certificates. X509Store), bei denen es sich um physische Speicher handelt, in denen Zertifikate gespeichert und verwaltet werden.

- X. 509 **System. Security. Cryptography. X509Certificates. X509Certificate2** -Zertifikate, von denen jedes ein X. 509-Zertifikat auf dem Computer darstellt.
  Zertifikate werden durch ihre Fingerabdrücke identifiziert.

## <a name="navigating-the-certificate-drive"></a>Navigieren im Zertifikat Laufwerk

Der **Zertifikat Anbieter macht** den Zertifikat Namespace als `Cert:` Laufwerk in PowerShell verfügbar. Dieser Befehl verwendet den- `Set-Location` Befehl, um den aktuellen Speicherort in den Stamm Zertifikat Speicher im LocalMachine-Speicherort zu ändern. Verwenden Sie einen umgekehrten Schrägstrich ( \\ ) oder einen Schrägstrich (/), um eine Ebene des `Cert:` Laufwerks anzugeben.

```powershell
Set-Location Cert:
```

Sie können auch mit dem Zertifikat Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten. Um auf einen Alias von einem anderen Speicherort zu verweisen, verwenden Sie den `Cert:` Namen des Laufwerks im Pfad.

```powershell
PS Cert:\> Set-Location -Path LocalMachine\Root
```

Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein. Beispiel:

```powershell
Set-Location C:
```

> [!NOTE]
> PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten. Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).
> und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="displaying-the-contents-of-the-cert-drive"></a>Anzeigen des Inhalts des CERT:-Laufwerks

Dieser Befehl verwendet das `Get-ChildItem` Cmdlet, um die Zertifikat Speicher im Zertifikat Speicherort von CurrentUser anzuzeigen.

Wenn Sie sich nicht auf dem `Cert:` Laufwerk befinden, verwenden Sie einen absoluten Pfad.

```powershell
PS Cert:\CurrentUser\> Get-ChildItem
```

### <a name="displaying-certificate-properties-within-the-cert-drive"></a>Anzeigen von Zertifikat Eigenschaften im CERT:-Laufwerk

In diesem Beispiel wird ein Zertifikat mit abgerufen `Get-Item` und in einer Variablen gespeichert.
Das Beispiel zeigt die neuen Zertifikat Skript Eigenschaften ( **dnsnamelist** , **enhancedkeyugeist** **) mithilfe** von `Select-Object` .

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

### <a name="find-all-codesigning-certificates"></a>Alle codesigungszertifikate suchen

Dieser Befehl verwendet die **codeSigningCert** -und **recurse** -Parameter des `Get-ChildItem` Cmdlets, um alle Zertifikate auf dem Computer zu erhalten, die über die Code Signatur Berechtigung verfügen.

```powershell
Get-ChildItem -Path cert: -CodeSigningCert -Recurse
```

### <a name="find-expired-certificates"></a>Abgelaufene Zertifikate suchen

Mit diesem Befehl wird der **expiriingindays** -Parameter des `Get-ChildItem` Cmdlets verwendet, um Zertifikate zu erhalten, die innerhalb der nächsten 30 Tage ablaufen.

```powershell
Get-ChildItem -Path cert:\LocalMachine\WebHosting -ExpiringInDays 30
```

### <a name="find-server-ssl-certificates"></a>Suchen von Server-SSL-Zertifikaten

Dieser Befehl verwendet den **sslserverauthentication** -Parameter des `Get-ChildItem` Cmdlets, um alle Server-SSL-Zertifikate im My-und Webhosting-Speicher zu erhalten.

```powershell
Get-ChildItem -Path cert:\LocalMachine\My, cert:\LocalMachine\WebHosting `
  -SSLServerAuthentication
```

### <a name="find-expired-certificates-on-remote-computers"></a>Suchen abgelaufener Zertifikate auf Remote Computern

Dieser Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Get-ChildItem` Befehls auf den Computern SRV01 und Srv02. Der Wert NULL (0) im **expiriingindays** -Parameter ruft Zertifikate auf den Computern SRV01 und Srv02 ab, die abgelaufen sind.

```powershell
Invoke-Command -ComputerName Srv01, Srv02 {Get-ChildItem -Path cert:\* `
  -Recurse -ExpiringInDays 0}
```

### <a name="combining-filters-to-find-a-specific-set-of-certificates"></a>Kombinieren von Filtern für die Suche nach einem bestimmten Satz von Zertifikaten

Mit diesem Befehl werden alle Zertifikate im LocalMachine-Speicherort abgerufen, die die folgenden Attribute aufweisen:

- "Fabrikam" im DNS-Namen
- "Client Authentifizierung" in der EKU
- der Wert `$true` für die **sendastrusteabschrecker** -Eigenschaft.
- läuft nicht innerhalb der nächsten 30 Tage ab.

Die **NotAfter** -Eigenschaft speichert das Ablaufdatum des Zertifikats.

```powershell
[DateTime] $ValidThrough = (Get-Date) + (New-TimeSpan -Days 30)
Get-ChildItem -Path cert:\* -Recurse -DNSName "*fabrikam*" `
  -EKU "*Client Authentication*" | Where-Object {
                                     $_.SendAsTrustedIssuer -and `
                                     $_.NotAfter -gt $ValidThrough
                                   }
```

## <a name="opening-the-certificates-mmc-snap-in"></a>Öffnen des Zertifikate-MMC-Snap-Ins

Mit dem- `Invoke-Item` Cmdlet wird die Standardanwendung verwendet, um einen von Ihnen angegebenen Pfad zu öffnen. Bei Zertifikaten ist die Standardanwendung das MMC-Snap-in "Zertifikate".

Dieser Befehl öffnet das Zertifikate-MMC-Snap-In zum Verwalten des angegebenen Zertifikats.

```powershell
Invoke-Item cert:\CurrentUser\my\6B8223358119BB08840DEE50FD8AF9EA776CE66B
```

## <a name="copying-certificates"></a>Kopieren von Zertifikaten

Das Kopieren von Zertifikaten wird vom **Zertifikat** Anbieter nicht unterstützt. Wenn Sie versuchen, ein Zertifikat zu kopieren, wird dieser Fehler angezeigt.

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

## <a name="moving-certificates"></a>Verschieben von Zertifikaten

### <a name="move-all-ssl-server-authentication-certs-to-the-webhosting-store"></a>Verschieben aller Zertifikate der SSL-Server Authentifizierung in den Webhosting-Speicher

Dieser Befehl verwendet das `Move-Item` Cmdlet, um ein Zertifikat aus dem eigenen Speicher in den Webhosting-Speicher zu verschieben.

`Move-Item` von werden keine Zertifikat Speicher verschoben, und Zertifikate werden nicht an einen anderen Speicherort verschoben, z. b. das Verschieben eines Zertifikats von LocalMachine nach CurrentUser. Das `Move-Item` Cmdlet verschiebt Zertifikate, aber keine privaten Schlüssel.

Dieser Befehl verwendet den **sslserverauthentication** -Parameter des `Get-ChildItem` Cmdlets, um SSL-Server Authentifizierungs Zertifikate im My-Zertifikat Speicher zu erhalten.

Die zurückgegebenen Zertifikate werden an das `Move-Item` Cmdlet weitergeleitet, wodurch die Zertifikate in den Webhosting-Speicher verschoben werden.

```powershell
Get-ChildItem cert:\LocalMachine\My -SSLServerAuthentication | Move-Item `
  -Destination cert:\LocalMachine\WebHosting
```

## <a name="deleting-certificates-and-private-keys"></a>Löschen von Zertifikaten und privaten Schlüsseln

Mit dem- `Remove-Item` Cmdlet werden von Ihnen angegebene Zertifikate entfernt. Der `-DeleteKey` dynamische Parameter löscht den privaten Schlüssel.

### <a name="delete-a-certificate-from-the-ca-store"></a>Löschen eines Zertifikats aus dem ca-Speicher

Dieser Befehl löscht ein Zertifikat aus dem CA-Zertifikatspeicher, lässt jedoch den zugehörigen privaten Schlüssel intakt.

Im- `Cert:` Laufwerk `Remove-Item` unterstützt das Cmdlet nur die **Parameter DeleteKey** , **path** , **WhatIf** und **Confirm** . Alle anderen Parameter werden ignoriert.

```powershell
Remove-Item cert:\LocalMachine\CA\5DDC44652E62BF9AA1116DC41DE44AB47C87BDD0
```

### <a name="delete-a-certificate-using-a-wildcards-in-the-dns-name"></a>Löschen eines Zertifikats mithilfe von Platzhaltern im DNS-Namen

Dieser Befehl löscht alle Zertifikate, deren DNS-Name "Fabrikam" enthält. Er verwendet den **DnsName** -Parameter des `Get-ChildItem` Cmdlets, um die Zertifikate zu erhalten, und das `Remove-Item` Cmdlet, um Sie zu löschen.

```powershell
Get-ChildItem -Path cert:\LocalMachine -DnsName *Fabrikam* | Remove-Item
```

### <a name="delete-private-keys-from-a-remote-computer"></a>Löschen von privaten Schlüsseln von einem Remote Computer

Diese Reihe von Befehlen ermöglicht die Delegation und löscht dann das Zertifikat und den zugehörigen privaten Schlüssel auf einem Remotecomputer. Um einen privaten Schlüssel auf einem Remotecomputer zu löschen, müssen Sie die delegierten Anmeldeinformationen verwenden.

Verwenden Sie das- `Enable-WSManCredSSP` Cmdlet, um die Authentifizierung für den Anmelde Informationsdienst (Security Service Provider, kredssp) auf einem Client auf dem Remote Computer S1 zu aktivieren.
CredSSP ermöglicht die delegierte Authentifizierung.

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer S1
```

Verwenden `Connect-WSMan` Sie das Cmdlet, um den Computer S1 mit dem WinRM-Dienst auf dem lokalen Computer zu verbinden. Wenn dieser Befehl abgeschlossen ist, wird der S1-Computer auf dem lokalen `WSMan:` Laufwerk in PowerShell angezeigt.

```powershell
Connect-WSMan -ComputerName S1 -Credential Domain01\Admin01
```

Nun können Sie das Cmdlet "Set-Item" im WSMAN:-Laufwerk verwenden, um das Attribut "Attribut" für den WinRM-Dienst zu aktivieren.

```powershell
Set-Item -Path WSMan:\S1\Service\Auth\CredSSP -Value $true
```

Starten Sie mithilfe des Cmdlets eine Remote Sitzung auf dem Computer S1 `New-PSSession` , und geben Sie die Authentifizierung für die Authentifizierung an. Speichert die Sitzung in der `$s` Variablen.

```powershell
$s  = New-PSSession S1 -Authentication CredSSP -Credential Domain01\Admin01
```

Verwenden Sie abschließend das `Invoke-Command` Cmdlet, um einen `Remove-Item` Befehl in der Sitzung in der `$s` Variablen auszuführen. Der `Remove-Item` Befehl verwendet den **DeleteKey** -Parameter, um den privaten Schlüssel zusammen mit dem angegebenen Zertifikat zu entfernen.

```powershell
Invoke-Command -Session $s { Remove-Item `
  -Path cert:\LocalMachine\My\D2D38EBA60CAA1C12055A2E1C83B15AD450110C2 `
  -DeleteKey
  }
```

### <a name="delete-expired-certificates"></a>Abgelaufene Zertifikate löschen

Dieser Befehl verwendet den **expiriingindays** -Parameter des `Get-ChildItem` Cmdlets mit dem Wert 0, um Zertifikate im Webhosting-Speicher zu erhalten, die abgelaufen sind.

Die Variable, die die zurückgegebenen Zertifikate enthält, wird an das `Remove-Item` Cmdlet weitergeleitet, wodurch Sie gelöscht werden. Der Befehl verwendet den **DeleteKey** -Parameter, um den privaten Schlüssel zusammen mit dem Zertifikat zu löschen.

```powershell
$expired = Get-ChildItem cert:\LocalMachine\WebHosting -ExpiringInDays 0
$expired | Remove-Item -DeleteKey
```

## <a name="creating-certificates"></a>Erstellen von Zertifikaten

Mit dem- `New-Item` Cmdlet werden keine neuen Zertifikate im **Zertifikat** Anbieter erstellt. Verwenden Sie das Cmdlet [New-selfsignedcertificate](/powershell/module/pkiclient/new-selfsignedcertificate) , um ein Zertifikat zu Testzwecken zu erstellen.

## <a name="creating-certificate-stores"></a>Erstellen von Zertifikatspeichern

Im CERT:-Laufwerk erstellt das `New-Item` Cmdlet Zertifikat Speicher am LocalMachine-Speicherort. Er unterstützt die Parameter **Name** , **path** , **WhatIf** und **Confirm** . Alle anderen Parameter werden ignoriert. Der Befehl gibt eine **System. Security. Cryptography. X509Certificates. X509Store** zurück, die den neuen Zertifikat Speicher darstellt.

Dieser Befehl erstellt einen neuen Zertifikatspeicher mit dem Namen "CustomStore" am Speicherort des LocalMachine-Speichers.

```powershell
New-Item -Path cert:\LocalMachine\CustomStore
```

### <a name="create-a-new-certificate-store-on-a-remote-computer"></a>Erstellen eines neuen Zertifikat Speicher auf einem Remote Computer

Dieser Befehl erstellt einen neuen Zertifikatspeicher mit dem Namen "HostingStore" am LocalMachine-Speicherort auf dem Computer Server01.

Der Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `New-Item` Befehls auf dem Server01-Computer. Der Befehl gibt eine **System. Security. Cryptography. X509Certificates. X509Store** zurück, die den neuen Zertifikat Speicher darstellt.

```powershell
Invoke-Command { New-Item -Path cert:\LocalMachine\CustomStore } `
  -ComputerName Server01
```

## <a name="creating-client-certificates-for-ws-man"></a>Erstellen von Client Zertifikaten für WS-Man

Mit diesem Befehl wird der **ClientCertificate** -Eintrag erstellt, der vom **WS-Management** -Client verwendet werden kann. Das neue **ClientCertificate** wird unter dem Verzeichnis " **ClientCertificate** " als "ClientCertificate_1234567890" angezeigt. Alle Parameter müssen angegeben werden. Der **Aussteller** muss den Fingerabdruck des Aussteller Zertifikats aufweisen.

```powershell
$cred = Get-Credential
New-Item -Path WSMan:\localhost\ClientCertificate `
         -Issuer 1b3fd224d66c6413fe20d21e38b304226d192dfe `
         -URI wmicimv2/* -Credential $cred
```

## <a name="deleting-certificate-stores"></a>Löschen von Zertifikatspeichern

### <a name="delete-a-certificate-store-from-a-remote-computer"></a>Löschen eines Zertifikat Speicher von einem Remote Computer

Dieser Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines `Remove-Item` Befehls auf den Computern S1 und S2. Der `Remove-Item` Befehl enthält den **recurse** -Parameter, mit dem die Zertifikate im Speicher gelöscht werden, bevor der Speicher gelöscht wird.

```powershell
Invoke-Command { Remove-Item -Path cert:\LocalMachine\TestStore -Recurse } `
  -ComputerName S1, S2
```

## <a name="dynamic-parameters"></a>Dynamische Parameter

Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird. Diese Parameter sind in allen Unterverzeichnissen des Zertifikat Anbieters gültig, gelten aber nur für Zertifikate.

> [!NOTE]
> Parameter, die die Filterung für die Eigenschaft ausführen, `EnhancedKeyUsageList` geben auch Elemente mit einem leeren `EnhancedKeyUsageList` Eigenschafts Wert zurück.
> Zertifikate, die eine leere **enhancedkeyceist** haben, können für alle Zwecke verwendet werden.

Die folgenden Zertifikat Anbieter Parameter wurden in PowerShell 7,1 erneut eingeführt.

- DNSName
- DocumentEncryptionCert
- EKU
- ExpiringInDays
- SSLServerAuthentication

### <a name="codesigningcert-systemmanagementautomationswitchparameter"></a>CodeSigningCert <System. Management. Automation. Switchparameter>

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Dieser Parameter ruft die Zertifikate ab, die "Code Signing" in Ihrem **enhancedkey-agelist** -Eigenschafts Wert aufweisen.

### <a name="deletekey-systemmanagementautomationswitchparameter"></a>DeleteKey <System. Management. Automation. Switchparameter>

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)

Mit diesem Parameter wird der zugehörige private Schlüssel gelöscht, wenn das Zertifikat gelöscht wird.

> [!IMPORTANT]
> Wenn Sie einen privaten Schlüssel löschen möchten, der einem Benutzerzertifikat im `Cert:\CurrentUser` Speicher auf einem Remote Computer zugeordnet ist, müssen Sie Delegierte Anmelde Informationen verwenden. Das `Invoke-Command` Cmdlet unterstützt die Delegierung von Anmelde Informationen mithilfe des Parameters " **kredssp** ". Vor der Verwendung `Remove-Item` von mit und der Delegierung von Anmelde Informationen sollten Sicherheitsrisiken berücksichtigt werden `Invoke-Command` .

Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.

### <a name="dnsname-microsoftpowershellcommandsdnsnamerepresentation"></a>DnsName <Microsoft. PowerShell. Commands. dnsnamerepresentation>

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Dieser Parameter ruft die Zertifikate ab, die den angegebenen Domänen Namen oder das Namensmuster in der **dnsnamelist** -Eigenschaft des Zertifikats aufweisen. Der Wert dieses Parameters kann "Unicode" oder "ASCII" lauten. Punycode-Werte werden in Unicode konvertiert. Platzhalter Zeichen ( `*` ) sind zulässig.

Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.

### <a name="documentencryptioncert-systemmanagementautomationswitchparameter"></a>Documentverschlüsseltioncert <System. Management. Automation. Switchparameter>

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Dieser Parameter ruft die Zertifikate ab, die "Document Encryption" in Ihrem **enhancedkey-agelist** -Eigenschafts Wert aufweisen.

### <a name="eku-systemstring"></a>EKU <System. String>

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Dieser Parameter ruft die Zertifikate ab, die den angegebenen Text oder das Textmuster in der- `EnhancedKeyUsageList` Eigenschaft des Zertifikats aufweisen. Platzhalter Zeichen ( `*` ) sind zulässig. Die `EnhancedKeyUsageList` -Eigenschaft enthält den anzeigen Amen und die OID-Felder der EKU.

Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.

### <a name="expiringindays-systemint32"></a>Expiriingindays <System. Int32>

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Dieser Parameter ruft Zertifikate ab, die in oder vor der angegebenen Anzahl von Tagen ablaufen. Der Wert 0 (Null) ruft die Zertifikate ab, die abgelaufen sind.

Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.

### <a name="itemtype-string"></a>ItemType \<String\>

Mit diesem Parameter können Sie den Typ des Elements angeben, das von erstellt wird `New-Item` .

In einem `Certificate` Laufwerk sind folgende Werte zulässig:

- Zertifikat-Anbieter
- Zertifikat
- Speicher
- StoreLocation

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

### <a name="sslserverauthentication-systemmanagementautomationswitchparameter"></a>Sslserverauthentication <System. Management. Automation. Switchparameter>

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)

Ruft nur die Serverzertifikate für SSL-Webhosting ab. Dieser Parameter ruft die Zertifikate ab, die im Eigenschafts Wert "Server Authentifizierung" aufweisen `EnhancedKeyUsageList` .

Dieser Parameter wurde in PowerShell 7,1 neu eingeführt.

## <a name="script-properties"></a>Skript Eigenschaften

Dem **x509Certificate2** -Objekt wurden neue Skript Eigenschaften hinzugefügt, die die Zertifikate darstellen, um das Suchen und Verwalten der Zertifikate zu erleichtern.

- `DnsNameList`: Zum Auffüllen der- `DnsNameList` Eigenschaft kopiert der Zertifikat Anbieter den Inhalt aus dem Eintrag "DnsName" in der Erweiterung "subjetalternativename" (San). Wenn die SAN-Erweiterung leer ist, wird die Eigenschaft mit dem Inhalt aus dem Antragstellerfeld des Zertifikats aufgefüllt.

- `EnhancedKeyUsageList`: Zum Auffüllen der- `EnhancedKeyUsageList` Eigenschaft kopiert der Zertifikat Anbieter die OID-Eigenschaften des Felds EnhancedKeyUsage (EKU) im Zertifikat und erstellt einen anzeigen Amen dafür.

- `SendAsTrustedIssuer`: Zum Auffüllen der- `SendAsTrustedIssuer` Eigenschaft kopiert der Zertifikat Anbieter die- `SendAsTrustedIssuer` Eigenschaft aus dem Zertifikat.  Weitere Informationen finden Sie [unter Verwaltung vertrauenswürdiger Aussteller für die Client Authentifizierung](/windows-server/security/tls/what-s-new-in-tls-ssl-schannel-ssp-overview#BKMK_TrustedIssuers).

Mit diesen neuen Funktionen können Sie die Zertifikate basierend auf ihren DNS-Namen und Ablaufdaten suchen und Zertifikate für Client- und Server-Authentifizierung durch den Wert der erweiterten Schlüsselverwendung (EKU)-Eigenschaften unterscheiden.

## <a name="using-the-pipeline"></a>Verwenden der Pipeline

Anbieter-Cmdlets akzeptieren Pipeline Eingaben. Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.
Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.

## <a name="getting-help"></a>Hilfe

Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.

Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den- `-Path` Parameter von `Get-Help` , um ein Dateisystem Laufwerk anzugeben.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path cert:
```

## <a name="see-also"></a>Weitere Informationen:

[about_Providers](../../Microsoft.PowerShell.Core/About/about_Providers.md)

[about_Signing](../../Microsoft.PowerShell.Core/About/about_Signing.md)

[Get-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Get-AuthenticodeSignature)

[Set-AuthenticodeSignature](xref:Microsoft.PowerShell.Security.Set-AuthenticodeSignature)

[Get-PfxCertificate](xref:Microsoft.PowerShell.Security.Get-PfxCertificate)
