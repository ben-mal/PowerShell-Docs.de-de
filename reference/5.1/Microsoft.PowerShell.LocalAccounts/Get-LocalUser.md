---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalUser
ms.openlocfilehash: 34210145bcddc8d9420552d637a6cd6e5f8e61cc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211887"
---
# Get-LocalUser

## ZUSAMMENFASSUNG
Ruft lokale Benutzerkonten ab.

## SYNTAX

### Standard (Standard)

```
Get-LocalUser [[-Name] <String[]>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalUser [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-LocalUser` Cmdlet werden lokale Benutzerkonten abgerufen. Mit diesem Cmdlet werden standardmäßige integrierte Benutzerkonten, lokale Benutzerkonten, die Sie erstellt haben, und lokale Konten, die Sie mit Microsoft-Konten verbunden haben, abgerufen.

> [!NOTE]
> Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.

## BEISPIELE

### Beispiel 1: erhalten eines Kontos mithilfe des Namens

In diesem Beispiel wird ein Benutzerkonto mit dem Namen AdminContoso02 abgerufen.

```powershell
Get-LocalUser -Name "AdminContoso02"
```

```Output
Name             Enabled Description
----             ------- -----------
AdminContoso02   True    Description of this account.
```

### Beispiel 2: Holen Sie sich ein Konto, das mit einem Microsoft-Konto verbunden ist.

In diesem Beispiel wird ein Benutzerkonto abgerufen, das mit einem Microsoft-Konto verbunden ist. In diesem Beispiel wird ein Platzhalter Wert für den Benutzernamen eines Kontos unter Outlook.com verwendet.

```powershell
Get-LocalUser -Name "MicrosoftAccount\username@Outlook.com"
```

```Output
Name                                    Enabled  Description
----                                    -------  -----------
MicrosoftAccount\username@outlook.com  True     Description of this account.
```

### Beispiel 3: erhalten eines Kontos, das mit einem Microsoft-Konto verbunden ist

In diesem Beispiel wird ein lokales Benutzerkonto abgerufen, das über die angegebene SID verfügt.

```powershell
Get-LocalUser -SID S-1-5-21-9526073513-1762370368-3942940353-500
```

```Output
Name          Enabled Description
----          ------- -----------
Administrator True    Built-in account for administering the computer/domain
```

## PARAMETERS

### -Name

Gibt ein Array von Namen von Benutzerkonten an, die von diesem Cmdlet abgerufen werden. Sie können das Platzhalter Zeichen verwenden.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -SID

Gibt ein Array von Sicherheits-IDs (SIDs) von Benutzerkonten an, die von diesem Cmdlet abgerufen werden.

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. String, System. Security. Principal. SecurityIdentifier

Sie können eine Zeichenfolge oder eine SID an dieses Cmdlet übergeben.

## AUSGABEN

### System. Management. Automation. securityaccounungmanager. LocalUser []

Mit diesem Cmdlet werden lokale Benutzerkonten zurückgegeben.

## HINWEISE

Die **principalsource** -Eigenschaft für die Objekte **LocalUser** , **localgroup** und **localprincipal** beschreibt die Quelle des Objekts. Folgende Quellen sind möglich:

- Lokal
- Active Directory
- Azure Active Directory-Gruppe
- Microsoft-Konto

**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt. Bei früheren Versionen ist die-Eigenschaft leer.

## VERWANDTE LINKS

[Disable-LocalUser](Disable-LocalUser.md)

[Enable-LocalUser](Enable-LocalUser.md)

[New-LocalUser](New-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
