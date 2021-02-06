---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: baf06c34511217f23d876843007525b9ce17f35b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603520"
---
# <span data-ttu-id="ca00d-102">Get-PfxCertificate</span><span class="sxs-lookup"><span data-stu-id="ca00d-102">Get-PfxCertificate</span></span>

## <span data-ttu-id="ca00d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="ca00d-103">SYNOPSIS</span></span>
<span data-ttu-id="ca00d-104">Ruft Informationen zu PFX-Zertifikat Dateien auf dem Computer ab.</span><span class="sxs-lookup"><span data-stu-id="ca00d-104">Gets information about PFX certificate files on the computer.</span></span>

## <span data-ttu-id="ca00d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ca00d-105">SYNTAX</span></span>

### <span data-ttu-id="ca00d-106">Bypath (Standard)</span><span class="sxs-lookup"><span data-stu-id="ca00d-106">ByPath (Default)</span></span>

```
Get-PfxCertificate [-FilePath] <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

### <span data-ttu-id="ca00d-107">Byliteralpath</span><span class="sxs-lookup"><span data-stu-id="ca00d-107">ByLiteralPath</span></span>

```
Get-PfxCertificate -LiteralPath <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

## <span data-ttu-id="ca00d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ca00d-108">DESCRIPTION</span></span>

<span data-ttu-id="ca00d-109">Mit dem- `Get-PfxCertificate` Cmdlet wird ein Objekt abgerufen, das jede angegebene pfx-Zertifikat Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="ca00d-109">The `Get-PfxCertificate` cmdlet gets an object representing each specified PFX certificate file.</span></span>
<span data-ttu-id="ca00d-110">Eine PFX-Datei enthält das Zertifikat und einen privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ca00d-110">A PFX file includes both the certificate and a private key.</span></span>

## <span data-ttu-id="ca00d-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="ca00d-111">EXAMPLES</span></span>

### <span data-ttu-id="ca00d-112">Beispiel 1: erhalten eines PFX-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="ca00d-112">Example 1: Get a PFX certificate</span></span>

```powershell
Get-PfxCertificate -FilePath "C:\windows\system32\Test.pfx"
```

```output
Password: ******
Signer Certificate:      David Chew (Self Certificate)
Time Certificate:
Time Stamp:
Path:                    C:\windows\system32\zap.pfx
```

<span data-ttu-id="ca00d-113">Dieser Befehl ruft Informationen über die Test. pfx-Zertifikat Datei auf dem System ab.</span><span class="sxs-lookup"><span data-stu-id="ca00d-113">This command gets information about the Test.pfx certificate file on the system.</span></span>

### <span data-ttu-id="ca00d-114">Beispiel 2: erhalten eines PFX-Zertifikats von einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="ca00d-114">Example 2: Get a PFX certificate from a remote computer</span></span>

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

<span data-ttu-id="ca00d-115">Mit diesem Befehl wird eine PFX-Zertifikat Datei vom Remote Computer Server01 abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ca00d-115">This command gets a PFX certificate file from the Server01 remote computer.</span></span> <span data-ttu-id="ca00d-116">Es verwendet `Invoke-Command` , um einen `Get-PfxCertificate` Befehl Remote auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ca00d-116">It uses `Invoke-Command` to run a `Get-PfxCertificate` command remotely.</span></span>

<span data-ttu-id="ca00d-117">Wenn die PFX-Zertifikat Datei nicht Kenn Wort geschützt ist, muss der Wert des **Authentifizierungs** Parameters von " `Invoke-Command` kredssp" lauten.</span><span class="sxs-lookup"><span data-stu-id="ca00d-117">When the PFX certificate file is not password-protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="ca00d-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ca00d-118">PARAMETERS</span></span>

### <span data-ttu-id="ca00d-119">-FilePath</span><span class="sxs-lookup"><span data-stu-id="ca00d-119">-FilePath</span></span>

<span data-ttu-id="ca00d-120">Gibt den vollständigen Pfad zur PFX-Datei der gesicherten Datei an.</span><span class="sxs-lookup"><span data-stu-id="ca00d-120">Specifies the full path to the PFX file of the secured file.</span></span> <span data-ttu-id="ca00d-121">Wenn Sie einen Wert für diesen Parameter angeben, ist es nicht erforderlich, dass Sie `-FilePath` in der Befehlszeile eingeben.</span><span class="sxs-lookup"><span data-stu-id="ca00d-121">If you specify a value for this parameter, it is not necessary to type `-FilePath` at the command line.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ca00d-122">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="ca00d-122">-LiteralPath</span></span>

<span data-ttu-id="ca00d-123">Der vollständige Pfad zur PFX-Datei der gesicherten Datei.</span><span class="sxs-lookup"><span data-stu-id="ca00d-123">The full path to the PFX file of the secured file.</span></span> <span data-ttu-id="ca00d-124">Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath**-Parameters genau wie eingegeben verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca00d-124">Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="ca00d-125">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ca00d-125">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ca00d-126">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ca00d-126">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ca00d-127">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ca00d-127">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ca00d-128">-Nopromptforpassword</span><span class="sxs-lookup"><span data-stu-id="ca00d-128">-NoPromptForPassword</span></span>

<span data-ttu-id="ca00d-129">Unterdrückt die Eingabeaufforderung für ein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="ca00d-129">Suppresses prompting for a password.</span></span>

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

### <span data-ttu-id="ca00d-130">-Password</span><span class="sxs-lookup"><span data-stu-id="ca00d-130">-Password</span></span>

<span data-ttu-id="ca00d-131">Gibt ein Kennwort für den Zugriff auf eine `.pfx` Zertifikatsdatei an.</span><span class="sxs-lookup"><span data-stu-id="ca00d-131">Specifies a password required to access a `.pfx` certificate file.</span></span>

<span data-ttu-id="ca00d-132">Dieser Parameter wurde in PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ca00d-132">This parameter was introduced in PowerShell 6.1.</span></span>

> [!NOTE]
> <span data-ttu-id="ca00d-133">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="ca00d-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca00d-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ca00d-134">CommonParameters</span></span>

<span data-ttu-id="ca00d-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ca00d-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ca00d-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ca00d-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ca00d-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="ca00d-137">INPUTS</span></span>

### <span data-ttu-id="ca00d-138">System.String</span><span class="sxs-lookup"><span data-stu-id="ca00d-138">System.String</span></span>

<span data-ttu-id="ca00d-139">Sie können eine Zeichenfolge mit einem Dateipfad an die Pipeline übergeben `Get-PfxCertificate` .</span><span class="sxs-lookup"><span data-stu-id="ca00d-139">You can pipe a string that contains a file path to `Get-PfxCertificate`.</span></span>

## <span data-ttu-id="ca00d-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="ca00d-140">OUTPUTS</span></span>

### <span data-ttu-id="ca00d-141">System.Security.Cryptography.X509Certificates.X509Certificate2</span><span class="sxs-lookup"><span data-stu-id="ca00d-141">System.Security.Cryptography.X509Certificates.X509Certificate2</span></span>

<span data-ttu-id="ca00d-142">`Get-PfxCertificate` Gibt ein-Objekt für jedes Zertifikat zurück, das abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ca00d-142">`Get-PfxCertificate` returns an object for each certificate that it gets.</span></span>

## <span data-ttu-id="ca00d-143">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="ca00d-143">NOTES</span></span>

<span data-ttu-id="ca00d-144">Wenn Sie mit dem `Invoke-Command` Cmdlet einen `Get-PfxCertificate` Befehl Remote ausführen und die PFX-Zertifikat Datei nicht Kenn Wort geschützt ist, muss der Wert des **Authentifizierungs** Parameters von " `Invoke-Command` kredssp" lauten.</span><span class="sxs-lookup"><span data-stu-id="ca00d-144">When using the `Invoke-Command` cmdlet to run a `Get-PfxCertificate` command remotely, and the PFX certificate file is not password protected, the value of the **Authentication** parameter of `Invoke-Command` must be CredSSP.</span></span>

## <span data-ttu-id="ca00d-145">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="ca00d-145">RELATED LINKS</span></span>

[<span data-ttu-id="ca00d-146">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ca00d-146">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="ca00d-147">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ca00d-147">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

