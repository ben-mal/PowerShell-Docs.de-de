---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/get-wsmancredssp?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WSManCredSSP
ms.openlocfilehash: ce2046a9df5d4d02d718d6408c7a196a753c9914
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224836"
---
# Get-WSManCredSSP

## ZUSAMMENFASSUNG
Ruft die CredSSP (Credential Security Support Provider)-bezogene Konfiguration für den Client ab.

## SYNTAX

```
Get-WSManCredSSP [<CommonParameters>]
```

## DESCRIPTION
Das **Get-wsmankredssp** -Cmdlet ruft die Konfiguration des-Clients und des-Servers für die Unterstützung des Anmelde Informationsanbieters ab.
Die Ausgabe gibt an, ob die CredSSP (Credential Security Support Provider)-Authentifizierung aktiviert oder deaktiviert ist.
Dieses Cmdlet zeigt auch Konfigurationsinformationen für die **allowfreshanmelde** -Richtlinie von "kredssp" an.

Wenn Sie die dedssp-Authentifizierung verwenden, werden die Anmelde Informationen des Benutzers an einen Remote Computer übergeben, der authentifiziert werden soll.
Diese Art der Authentifizierung ist für Befehle vorgesehen, die eine Remote Sitzung aus einer anderen Remote Sitzung erstellen.
Wenn Sie z. b. einen Hintergrund Auftrag auf einem Remote Computer ausführen möchten, verwenden Sie diese Art der Authentifizierung.

Das Cmdlet führt folgende Aktionen aus:

- Ruft die WS-Management auf dem Client auf dem Client ( **\<localhost|computername\> \client\auth\kredssp** ) ab.
- Ruft die Windows-aufwärtsrichtlinieneinstellung **allowfreshanmeldeinformationen** ab.
- Ruft die WS-Management auf dem Server auf dem Server ( **\<localhost|computername\> \service\auth\kredssp** ) ab.

Vorsicht: die Benutzer Anmelde Informationen werden von der kredssp-Authentifizierung vom lokalen Computer an einen Remote Computer delegiert.
Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs.
Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

## BEISPIELE

### Beispiel 1: Anzeigen der Konfiguration von "kredssp"

```
PS C:\> Get-WSManCredSSP
```

Dieser Befehl zeigt CredSSP-Konfigurationsinformationen für Client und Server an.

Die Ausgabe gibt an, ob dieser Computer für CredSSP konfiguriert ist oder nicht.

Wenn der Computer für CredSSP konfiguriert ist, lautet die Ausgabe wie folgt:

`The machine is configured to allow delegating fresh credentials to the following target(s): wsman/server02.accounting.fabrikam.com`

Wenn der Computer nicht für CredSSP konfiguriert ist, lautet die Ausgabe wie folgt:

`The machine is not configured to allow delegating fresh credentials.`

## PARAMETERS

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine
Dieses Cmdlet nimmt keine Eingabe an.

## AUSGABEN

### Keine
Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

* Um die CredSSP-Authentifizierung zu deaktivieren, verwenden Sie das Disable-WSManCredSSP-Cmdlet. Um die CredSSP-Authentifizierung zu aktivieren, verwenden Sie das Enable-WSManCredSSP-Cmdlet.

## VERWANDTE LINKS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
