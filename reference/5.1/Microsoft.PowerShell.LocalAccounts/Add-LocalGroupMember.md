---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-LocalGroupMember
ms.openlocfilehash: 06993c8f6618472f4809e37fbf83d298d13ae515
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211927"
---
# Add-LocalGroupMember

## ZUSAMMENFASSUNG
Fügt einer lokalen Gruppe Mitglieder hinzu.

## SYNTAX

### Group

```
Add-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Standard

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Add-LocalGroupMember` Cmdlet werden Benutzer oder Gruppen einer lokalen Sicherheitsgruppe hinzugefügt. Alle einer Gruppe zugewiesenen Rechte und Berechtigungen werden allen Mitgliedern dieser Gruppe zugewiesen.

Mitglieder der Gruppe „Administratoren“ eines lokalen Computers haben die Berechtigung Vollzugriff auf dem Computer. Einschränken der Benutzeranzahl in der Gruppe „Administratoren“.

Wenn der Computer einer Domäne angehört, können Sie einer lokalen Gruppe Benutzerkonten, Computerkonten und Gruppenkonten aus dieser Domäne und aus vertrauenswürdigen Domänen hinzufügen.

> [!NOTE]
> Wenn der Computer einer Domäne angehört und Sie versuchen, einen lokalen Benutzer hinzuzufügen, der denselben Namen wie ein Mitglied der Domäne hat, wird das Domänen Mitglied hinzugefügt.

## BEISPIELE

### Beispiel 1: Hinzufügen von Mitgliedern zur Gruppe "Administratoren"

Mit diesem Befehl werden der lokalen Gruppe "Administratoren" mehrere Mitglieder hinzugefügt. Zu den neuen Mitgliedern gehören ein lokales Benutzerkonto, ein Microsoft-Konto, ein Azure Active Directory Konto und eine Domänen Gruppe. In diesem Beispiel wird ein Platzhalter Wert für den Benutzernamen eines Kontos unter Outlook.com verwendet.

```powershell
Add-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

## PARAMETERS

### -Group

Gibt die Sicherheitsgruppe an, der von diesem Cmdlet Mitglieder hinzugefügt werden.

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Member

Gibt ein Array von Benutzern oder Gruppen an, die von diesem Cmdlet zu einer Sicherheitsgruppe hinzugefügt werden. Sie können Benutzer oder Gruppen nach Name, Sicherheits-ID (SID) oder **localprincipal** -Objekten angeben.

```yaml
Type: Microsoft.PowerShell.Commands.LocalPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Gibt den Namen der Sicherheitsgruppe an, der von diesem Cmdlet Mitglieder hinzugefügt werden.

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SID

Gibt die Sicherheits-ID der Sicherheitsgruppe an, der von diesem Cmdlet Mitglieder hinzugefügt werden.

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird. Das Cmdlet wird nicht ausgeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. securityaccountmanager. localgroup, System. String, System. Security. Principal. SecurityIdentifier

Sie können einen lokalen Prinzipal, eine Zeichenfolge oder eine SID an dieses Cmdlet übergeben.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.

Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben. Folgende Quellen sind möglich:

- Lokal
- Active Directory
- Azure Active Directory-Gruppe
- Microsoft-Konto

**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt. Bei früheren Versionen ist die-Eigenschaft leer.

## VERWANDTE LINKS

[Get-LocalGroupMember](Get-LocalGroupMember.md)

[New-LocalGroup](New-LocalGroup.md)

[Remove-LocalGroupMember](Remove-LocalGroupMember.md)
