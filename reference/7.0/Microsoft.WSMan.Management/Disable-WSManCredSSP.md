---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/disable-wsmancredssp?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManCredSSP
ms.openlocfilehash: 3202e21b5f002610557f827f3a5f65659dec6823
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210839"
---
# Disable-WSManCredSSP

## ZUSAMMENFASSUNG
Deaktiviert die kredssp-Authentifizierung auf einem Computer.

## SYNTAX

```
Disable-WSManCredSSP [-Role] <String> [<CommonParameters>]
```

## DESCRIPTION
Das Cmdlet " **Disab-wsmankredssp** " deaktiviert die Authentifizierung der Credential Security Support Provider-Authentifizierung (-Authentifizierung) auf einem Client oder auf einem Server Computer.
Wenn die Authentifizierung mit der Authentifizierung verwendet wird, werden die Anmelde Informationen des Benutzers an einen Remote Computer übergeben, der authentifiziert werden soll.

Verwenden Sie dieses Cmdlet zum Deaktivieren von "dedssp" auf dem Client, indem Sie im *Role* -Parameter "Client" angeben.
Dieses Cmdlet führt die folgenden Aktionen aus:

- Deaktiviert "kredssp" auf dem Client. Mit diesem Cmdlet wird die WS-Management Einstellung **\<localhost|computername\> \client\auth\kredssp** auf false festgelegt.
- Entfernt alle WSMAN/*-Einstellungen aus der Windows-kredssp-Richtlinie **allowfreshanmelde** Informationen auf dem Client.

Verwenden Sie dieses Cmdlet zum Deaktivieren von "dedssp" auf dem Server, indem Sie den Server in der *Rolle* angeben.
Dieses Cmdlet führt die folgende Aktion aus:

- Deaktiviert "kredssp" auf dem Server. Mit diesem Cmdlet wird die WS-Management Einstellung **\<localhost|computername\> \service\auth\kredssp** auf false festgelegt.

Vorsicht: die Benutzer Anmelde Informationen werden von der kredssp-Authentifizierung vom lokalen Computer an einen Remote Computer delegiert.
Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.
Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

## BEISPIELE

### Beispiel 1: Deaktivieren von "kredssp" auf einem Client

```
PS C:\> Disable-WSManCredSSP -Role Client
```

Dieser Befehl deaktiviert CredSSP auf dem Client, wodurch die Delegierung an Server verhindert wird.

### Beispiel 2: Deaktivieren von "kredssp" auf einem Server

```
PS C:\> Disable-WSManCredSSP -Role Server
```

Dieser Befehl deaktiviert CredSSP auf dem Server, wodurch die Delegierung von Clients verhindert wird.

## PARAMETERS

### -Rolle
Gibt an, ob "kredssp" als Client oder als Server deaktiviert werden soll.
Die zulässigen Werte für diesen Parameter sind: Client und Server.

Wenn Sie den-Client angeben, führt dieses Cmdlet die folgenden Aktionen aus:

- Deaktiviert "kredssp" auf dem Client. Dieses Cmdlet legt WS-Management Einstellung **\<localhost|computername\> \client\auth\kredssp** auf false fest.
- Entfernt alle WSMAN/*-Einstellungen aus der Windows-kredssp-Richtlinie **allowfreshanmelde** Informationen auf dem Client.

Wenn Sie den Server angeben, führt dieses Cmdlet die folgende Aktion aus:

- Deaktiviert "kredssp" auf dem Server. Mit diesem Cmdlet wird die WS-Management Einstellung **\<localhost|computername\> \service\auth\kredssp** auf false festgelegt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Client, Server

Required: True
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

* Um die CredSSP-Authentifizierung zu aktivieren, verwenden Sie das Enable-WSManCredSSP-Cmdlet.

*

## VERWANDTE LINKS

[Connect-WSMan](Connect-WSMan.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

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
