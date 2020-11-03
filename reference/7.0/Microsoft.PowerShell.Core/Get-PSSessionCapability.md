---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssessioncapability?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSessionCapability
ms.openlocfilehash: cc660b80a29d2e27a0b3928c1073168b2575af8f
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211284"
---
# Get-PSSessionCapability

## ZUSAMMENFASSUNG
Ruft die Funktionen eines bestimmten Benutzers in einer eingeschränkten Sitzungs Konfiguration ab.

## SYNTAX

```
Get-PSSessionCapability [-ConfigurationName] <String> [-Username] <String> [-Full] [<CommonParameters>]
```

## DESCRIPTION

Mit dem " **Get-pssessioncapability"-** Cmdlet werden die Funktionen eines bestimmten Benutzers in einer eingeschränkten Sitzungs Konfiguration abgerufen.
Verwenden Sie dieses Cmdlet, um benutzerdefinierte Sitzungs Konfigurationen für Benutzer zu überwachen.

Ab Windows PowerShell 5,0 können Sie die **roledefinitions** -Eigenschaft in einer Sitzungs Konfigurationsdatei (. PSSC) verwenden.
Mithilfe dieser Eigenschaft können Sie Benutzern basierend auf der Gruppenmitgliedschaft unterschiedliche Funktionen für einen einzelnen eingeschränkten Endpunkt erteilen.
Mit dem " **Get-pssessioncapability"-** Cmdlet wird die Komplexität bei der Überwachung dieser Endpunkte reduziert, indem Sie die genauen Funktionen eines Benutzers bestimmen können.

Standardmäßig gibt das **Get-pssessioncapability** -Cmdlet eine Liste der Befehle zurück, die der angegebene Benutzer im angegebenen Endpunkt ausführen kann.
Dies entspricht dem Benutzer, der " **Get-Command** " im angegebenen Endpunkt ausgeführt hat.
Bei der Verwendung mit dem *Full* -Parameter gibt dieses Cmdlet ein **initialsessionstate** -Objekt zurück.
Dieses Objekt enthält Details zum PowerShell-Runspace, mit dem der angegebene Benutzer für den angegebenen Endpunkt interagieren würde.
Sie enthält Informationen wie den Sprachmodus, die Ausführungs Richtlinie und Umgebungsvariablen.

## BEISPIELE

### Beispiel 1: Get-Befehle, die für einen Benutzer verfügbar sind

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User'
```

In diesem Beispiel werden die Befehle, die für den Benutzer contoso\user verfügbar sind, beim Herstellen einer Verbindung mit dem eingeschränkten Endpunkt endpoint1 auf dem lokalen Computer zurückgegeben.

### Beispiel 2: erhalten von Details zu einem Runspace für einen Benutzer

```powershell
Get-PSSessionCapability -ConfigurationName Endpoint1 -Username 'CONTOSO\User' -Full
```

In diesem Beispiel werden Details zum Runspace zurückgegeben, mit dem der Benutzer contoso\user interagieren würde, wenn eine Verbindung mit dem eingeschränkten endpoint1-Endpunkt hergestellt wird.

## PARAMETERS

### -ConfigurationName

Gibt die Konfiguration der eingeschränkten Sitzung (Endpunkt) an, die Sie überprüfen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full

Gibt an, dass dieses Cmdlet den gesamten anfänglichen Sitzungs Status für den angegebenen Benutzer am angegebenen eingeschränkten Endpunkt zurückgibt.

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

### -Username

Gibt den Benutzer an, dessen Funktionen Sie überprüfen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

## AUSGABEN

### System. Management. Automation. AliasInfo

### System. Management. Automation. functioninfo

### System.Management.Automation.Runspaces.Initialsessionstate

## HINWEISE

## VERWANDTE LINKS

[New-PSRoleCapabilityFile](New-PSRoleCapabilityFile.md)
