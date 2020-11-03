---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroup
ms.openlocfilehash: 6a2f921972fef1794581b301df6e7439e56c7f47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214676"
---
# Remove-LocalGroup

## ZUSAMMENFASSUNG
Löscht lokale Sicherheitsgruppen.

## SYNTAX

### InputObject

```
Remove-LocalGroup [-InputObject] <LocalGroup[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Standard

```
Remove-LocalGroup [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SecurityIdentifier

```
Remove-LocalGroup [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Mit dem " **Remove-localgroup"-** Cmdlet werden lokale Sicherheitsgruppen gelöscht.
Mit diesem Cmdlet wird nur eine lokale Gruppe gelöscht.
Die Benutzerkonten, Computer Konten oder Gruppenkonten, die zu dieser Gruppe gehören, werden nicht gelöscht.
Eine gelöschte Gruppe kann nicht wieder hergestellt werden.

Wenn Sie eine Gruppe löschen und dann eine andere Gruppe mit demselben Gruppennamen erstellen, müssen Sie neue Berechtigungen für die neue Gruppe festlegen.
Die neue Gruppe erbt nicht die Berechtigungen, die der Gruppe zugewiesen wurden.

> [!NOTE]
> Das Microsoft. PowerShell. LocalAccounts-Modul ist in der 32-Bit-PowerShell auf einem 64-Bit-System nicht verfügbar.

## BEISPIELE

### Beispiel 1: Löschen einer Sicherheitsgruppe

```
PS C:\> Remove-LocalGroup -Name "SecurityGroup04"
```

Dieser Befehl löscht die Gruppe mit dem Namen SecurityGroup04.

## PARAMETERS

### -InputObject
Gibt ein Array von Sicherheitsgruppen an, die von diesem Cmdlet gelöscht werden.
Verwenden Sie das Cmdlet "Get-LocalGroup", um Gruppen zu erhalten.

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
Gibt ein Array von Namen der Sicherheitsgruppen an, die von diesem Cmdlet gelöscht werden.

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
Gibt ein Array von Sicherheits-IDs (SIDs) von Sicherheitsgruppen an, die von diesem Cmdlet gelöscht werden.

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

### System. Management. Automation. securityaccountmanager. localgroup, System. String, System. Security. Principal. SecurityIdentifier
Sie können eine Sicherheitsgruppe, eine Zeichenfolge oder eine SID an dieses Cmdlet weiterreichen.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Mit diesem Cmdlet können die folgenden Standard Gruppen nicht gelöscht werden:

- Administratoren
- Sicherungsoperatoren
- Kryptografie-Operatoren
- Distributed COM-Benutzer
- Event Log Readers
- Gäste
- Hyper-V-Administratoren
- IIS_IUSRS
- Netzwerkkonfigurations-Operatoren
- Leistungsprotokollbenutzer
- Systemmonitorbenutzer
- Powerusers
- Remotedesktopbenutzer
- Remoteverwaltungsbenutzer
- Replicator
- Benutzer
- WinRMRemoteWMIUsers__

* Die **principalsource** -Eigenschaft ist eine Eigenschaft für die Objekte " **LocalUser** ", " **localgroup** " und " **localprincipal** ", die die Quelle des Objekts beschreiben. Folgende Quellen sind möglich:

- Lokal
- Active Directory
- Azure Active Directory-Gruppe
- Microsoft-Konto

**Principalsource** wird nur von Windows 10, Windows Server 2016 und neueren Versionen des Windows-Betriebssystems unterstützt. Bei früheren Versionen ist die-Eigenschaft leer.

## VERWANDTE LINKS

[Get-LocalGroup](Get-LocalGroup.md)

[New-LocalGroup](New-LocalGroup.md)

[Rename-LocalGroup](Rename-LocalGroup.md)

[Set-LocalGroup](Set-LocalGroup.md)
