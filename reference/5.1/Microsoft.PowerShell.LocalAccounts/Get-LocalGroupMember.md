---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroupMember
ms.openlocfilehash: 200368c5d13bd027302ad824533e6c187906ed0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211892"
---
# Get-LocalGroupMember

## ZUSAMMENFASSUNG
Ruft Mitglieder aus einer lokalen Gruppe ab.

## SYNTAX

### Standard (Standard)

```
Get-LocalGroupMember [[-Member] <String>] [-Name] <String> [<CommonParameters>]
```

### Group

```
Get-LocalGroupMember [-Group] <LocalGroup> [[-Member] <String>] [<CommonParameters>]
```

### SecurityIdentifier

```
Get-LocalGroupMember [[-Member] <String>] [-SID] <SecurityIdentifier> [<CommonParameters>]
```

## DESCRIPTION
Das **Get-localgroupmember** -Cmdlet ruft Mitglieder aus einer lokalen Gruppe ab.

> [!NOTE]
> Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.

## BEISPIELE

### Beispiel 1: alle Mitglieder der Gruppe "Administratoren" erhalten

```
PS C:\> Get-LocalGroupMember -Group "Administrators"
ObjectClass Name                    PrincipalSource
----------- ----                    ---------------
User        CONTOSOPC\Administrator Local
User        CONTOSOPC\LocalAdmin    Local
```

Mit diesem Befehl werden alle Mitglieder der lokalen Gruppe "Administratoren" abgerufen.

## PARAMETERS

### -Group
Gibt die Sicherheitsgruppe an, von der dieses Cmdlet Mitglieder abruft.

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Member
Gibt einen Benutzer oder eine Gruppe an, der von diesem Cmdlet aus einer Sicherheitsgruppe abgerufen wird.
Sie können Benutzer oder Gruppen anhand des Namens oder der Sicherheits-ID (SID) angeben.
Geben Sie sid-Zeichen folgen in s-R-I-s-s an.
. .
akzeptiert.
Sie können Platzhalter Zeichen verwenden.
Wenn Sie diesen Parameter nicht angeben, ruft das Cmdlet alle Mitglieder der Gruppe ab.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Gibt den Namen der Sicherheitsgruppe an, von der dieses Cmdlet Mitglieder abruft.

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SID
Gibt die Sicherheits-ID der Sicherheitsgruppe an, von der das Cmdlet Mitglieder abruft.

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. securityaccountmanager. localgroup, System. String, System. Security. Principal. SecurityIdentifier
Sie können eine lokale Gruppe, eine Zeichenfolge oder eine SID über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Microsoft. securityaccounpmanager. localprincipal
Mit diesem Cmdlet werden lokale Prinzipale zurückgegeben.

## HINWEISE

* Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben. Folgende Quellen sind möglich:

- Lokal
- Active Directory
- Azure Active Directory-Gruppe
- Microsoft-Konto

**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt. Bei früheren Versionen ist die-Eigenschaft leer.

## VERWANDTE LINKS

[Add-LocalGroupMember](Add-LocalGroupMember.md)

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroupMember](Remove-LocalGroupMember.md)
