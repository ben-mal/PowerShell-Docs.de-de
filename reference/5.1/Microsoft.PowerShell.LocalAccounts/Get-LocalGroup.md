---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroup
ms.openlocfilehash: 2cd77c2766840527825b0ccf68abaac3c2ea6c16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211903"
---
# Get-LocalGroup

## ZUSAMMENFASSUNG
Ruft die lokalen Sicherheitsgruppen ab.

## SYNTAX

### Standard (Standard)

```
Get-LocalGroup [[-Name] <String[]>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalGroup [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## DESCRIPTION
Mit dem " **Get-localgroup"-** Cmdlet werden lokale Sicherheitsgruppen im Sicherheits Konto-Manager abgerufen.
Mit diesem Cmdlet werden die von Ihnen erstellten standardmäßigen integrierten Gruppen und lokalen Sicherheitsgruppen abgerufen.

> [!NOTE]
> Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.

## BEISPIELE

### Beispiel 1: erhalten der Gruppe "Administratoren"

```
PS C:\> Get-LocalGroup -Name "Administrators"
Name           Description
----           -----------
Administrators Administrators have complete and unrestricted access to the computer/domain
```

Mit diesem Befehl wird die lokale Gruppe "Administratoren" abgerufen.
Der Befehl zeigt die Eigenschaften der Gruppe in der-Konsole an.

## PARAMETERS

### -Name
Gibt ein Array von Namen von Sicherheitsgruppen an, die von diesem Cmdlet abgerufen werden.
Sie können das Platzhalter Zeichen verwenden.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SID
Gibt ein Array von Sicherheits-IDs (SIDs) von Sicherheitsgruppen an, die von diesem Cmdlet abgerufen werden.

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
Sie können eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.

## AUSGABEN

### System. Management. Automation. securityaccounzmanager. localgroup
Mit diesem Cmdlet wird eine lokale Gruppe zurückgegeben.

## HINWEISE

* Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben. Folgende Quellen sind möglich:

- Lokal
- Active Directory
- Azure Active Directory-Gruppe
- Microsoft-Konto

**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt. Bei früheren Versionen ist die-Eigenschaft leer.

## VERWANDTE LINKS

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroup](Remove-LocalGroup.md)

[Rename-LocalGroup](Rename-LocalGroup.md)

[Set-LocalGroup](Set-LocalGroup.md)
