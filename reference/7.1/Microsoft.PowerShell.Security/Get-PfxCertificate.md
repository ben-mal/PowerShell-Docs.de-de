---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: 794146b1b347ad547c3283383aca32662d6433ca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217492"
---
# Get-PfxCertificate

## ZUSAMMENFASSUNG
Ruft Informationen zu PFX-Zertifikat Dateien auf dem Computer ab.

## SYNTAX

### Bypath (Standard)

```
Get-PfxCertificate [-FilePath] <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

### Byliteralpath

```
Get-PfxCertificate -LiteralPath <String[]> [-Password <SecureString>] [-NoPromptForPassword]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-PfxCertificate` Cmdlet wird ein Objekt abgerufen, das jede angegebene pfx-Zertifikat Datei darstellt.
Eine PFX-Datei enthält das Zertifikat und einen privaten Schlüssel.

## BEISPIELE

### Beispiel 1: erhalten eines PFX-Zertifikats

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

Dieser Befehl ruft Informationen über die Test. pfx-Zertifikat Datei auf dem System ab.

### Beispiel 2: erhalten eines PFX-Zertifikats von einem Remote Computer

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

Mit diesem Befehl wird eine PFX-Zertifikat Datei vom Remote Computer Server01 abgerufen. Es verwendet `Invoke-Command` , um einen `Get-PfxCertificate` Befehl Remote auszuführen.

Wenn die PFX-Zertifikat Datei nicht Kenn Wort geschützt ist, muss der Wert des **Authentifizierungs** Parameters von " `Invoke-Command` kredssp" lauten.

## PARAMETERS

### -FilePath

Gibt den vollständigen Pfad zur PFX-Datei der gesicherten Datei an. Wenn Sie einen Wert für diesen Parameter angeben, ist es nicht erforderlich, dass Sie `-FilePath` in der Befehlszeile eingeben.

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

### -Literalpath

Der vollständige Pfad zur PFX-Datei der gesicherten Datei. Im Gegensatz zu **FilePath** wird der Wert des **LiteralPath** -Parameters genau wie eingegeben verwendet. Es werden keine Zeichen als Platzhalter interpretiert. Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen. Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

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

### -Nopromptforpassword

Unterdrückt die Eingabeaufforderung für ein Kennwort.

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

### -Password

Gibt ein Kennwort für den Zugriff auf eine `.pfx` Zertifikatsdatei an.

Dieser Parameter wurde in PowerShell 6,1 eingeführt.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge mit einem Dateipfad an die Pipeline übergeben `Get-PfxCertificate` .

## AUSGABEN

### System.Security.Cryptography.X509Certificates.X509Certificate2

`Get-PfxCertificate` Gibt ein-Objekt für jedes Zertifikat zurück, das abgerufen wird.

## HINWEISE

Wenn Sie mit dem `Invoke-Command` Cmdlet einen `Get-PfxCertificate` Befehl Remote ausführen und die PFX-Zertifikat Datei nicht Kenn Wort geschützt ist, muss der Wert des **Authentifizierungs** Parameters von " `Invoke-Command` kredssp" lauten.

## VERWANDTE LINKS

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)

