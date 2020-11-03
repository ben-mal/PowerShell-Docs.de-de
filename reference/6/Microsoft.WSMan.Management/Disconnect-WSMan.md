---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disconnect-wsman?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-WSMan
ms.openlocfilehash: 211f1f1129a5497226dfa2d716955cf65c87ecbb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212535"
---
# Disconnect-WSMan

## ZUSAMMENFASSUNG
Trennt den Client vom WinRM-Dienst auf einem Remotecomputer.

## SYNTAX

```
Disconnect-WSMan [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
Das **Disconnect-WSMAN-** Cmdlet trennt den Client vom WinRM-Dienst auf einem Remote Computer.
Wenn Sie die WS-Management Sitzung in einer Variablen gespeichert haben, bleibt das Sitzungs Objekt in der Variablen, der Status der WS-Management Sitzung wird jedoch geschlossen.
Sie können dieses Cmdlet im Kontext des WSMan-Anbieters verwenden, um den Client vom WinRM-Dienst auf einem Remotecomputer zu trennen.
Sie können dieses Cmdlet jedoch auch verwenden, um die Verbindung mit dem WinRM-Dienst auf Remotecomputern zu trennen, bevor Sie zum WSMan-Anbieter wechseln.

Weitere Informationen zum Herstellen einer Verbindung mit dem WinRM-Dienst auf einem Remotecomputer finden Sie unter „Connect-WSMan“.

## BEISPIELE

### Beispiel 1: Löschen einer Verbindung mit einem Remote Computer

```
PS C:\> Disconnect-WSMan -computer server01
PS C:\> cd WSMan:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
```

Dieser Befehl löscht die Verbindung mit dem Remote Computer mit dem Namen Server01.

Dieses Cmdlet wird in der Regel im Kontext des WSMan-Anbieters verwendet, um eine Verbindung mit einem Remotecomputer zu trennen, in diesem Fall mit dem Computer server01.
Sie können jedoch auch **Disconnect-WSMAN** verwenden, um Verbindungen mit Remote Computern zu entfernen, bevor Sie zum WSMAN-Anbieter wechseln.
Diese Verbindungen werden nicht in der Computername-Liste angezeigt.

## PARAMETERS

### -ComputerName
Gibt den Computer an, für den der Verwaltungsvorgang ausgeführt werden soll.
Bei dem Wert kann es sich um einen vollqualifizierten Domänennamen, einen NetBIOS-Namen oder eine IP-Adresse handeln.
Verwenden Sie den Namen des lokalen Computers, „localhost“ oder einen Punkt (.), um den lokalen Computer anzugeben.
Der lokale Computer ist die Standardeinstellung.
Wenn sich der Remotecomputer in einer anderen Domäne als der Benutzer befindet, müssen Sie einen vollqualifizierten Domänennamen verwenden.
Sie können einen Wert für diesen Parameter an das Cmdlet weiterreichen.

Die Verbindung mit dem lokalen Host kann nicht getrennt werden.
Das heißt, Sie können die Standardverbindung mit dem lokalen Computer nicht trennen.
Wenn Sie jedoch eine separate Verbindung mit dem lokalen Computer erstellen, z. b. mithilfe des Computer namens.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Dieses Cmdlet nimmt keine Eingabe an.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

## VERWANDTE LINKS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
