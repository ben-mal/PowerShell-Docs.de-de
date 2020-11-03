---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/enable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-LocalUser
ms.openlocfilehash: 80d062578e7114b69e5cb5f3367b56da3871b9df
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211916"
---
# Enable-LocalUser

## ZUSAMMENFASSUNG
Aktiviert ein lokales Benutzerkonto.

## SYNTAX

### InputObject

```
Enable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Standard

```
Enable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Enable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Das **enable-LocalUser-** Cmdlet aktiviert lokale Benutzerkonten.
Wenn ein Benutzerkonto deaktiviert ist, kann sich der Benutzer nicht anmelden.
Wenn ein Benutzerkonto aktiviert ist, kann sich der Benutzer anmelden.

> [!NOTE]
> Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.

## BEISPIELE

### Beispiel 1: Aktivieren eines Kontos durch Angeben eines Namens

```
PS C:\> Enable-LocalUser -Name "Admin02"
```

Mit diesem Befehl wird das Benutzerkonto mit dem Namen Admin02 aktiviert.

### Beispiel 2: Aktivieren eines Kontos mithilfe der Pipeline

```
PS C:\> Get-LocalUser -Name "Administrator" | Enable-LocalUser
```

Mit diesem Befehl wird das integrierte Administrator Konto mithilfe von **Get-LocalUser** abgerufen und dann mithilfe des Pipeline-Operators an das aktuelle Cmdlet übergeben.
Dieses Cmdlet aktiviert dieses Konto.

## PARAMETERS

### -InputObject
Gibt ein Array von Benutzerkonten an, die von diesem Cmdlet aktiviert werden.
Verwenden Sie das Cmdlet "Get-LocalUser", um ein Benutzerkonto zu erhalten.

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Gibt ein Array von Namen der Benutzerkonten an, die von diesem Cmdlet aktiviert werden.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SID
Gibt ein Array von Benutzerkonten an, die von diesem Cmdlet aktiviert werden.

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

### System. Management. Automation. securityaccountmanager. LocalUser, System. String, System. Security. Principal. SecurityIdentifier
Sie können einen lokalen Benutzer, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben. Folgende Quellen sind möglich:

- Lokal
- Active Directory
- Azure Active Directory-Gruppe
- Microsoft-Konto

**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt. Bei früheren Versionen ist die-Eigenschaft leer.

## VERWANDTE LINKS

[Disable-LocalUser](Disable-LocalUser.md)

[Get-LocalUser](Get-LocalUser.md)

[New-LocalUser](New-LocalUser.md)

[Remove-LocalUser](Remove-LocalUser.md)

[Rename-LocalUser](Rename-LocalUser.md)

[Set-LocalUser](Set-LocalUser.md)
