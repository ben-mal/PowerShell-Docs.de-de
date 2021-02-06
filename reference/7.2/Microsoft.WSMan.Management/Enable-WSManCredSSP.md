---
external help file: Microsoft.WSMan.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 08/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/enable-wsmancredssp?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManCredSSP
ms.openlocfilehash: bacafee683fa47d7be331b4e44d2ab75be5bdb23
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603143"
---
# Enable-WSManCredSSP

## ZUSAMMENFASSUNG
Aktiviert die Authentifizierung der Credential Security Support Provider (kredssp) auf einem Computer.

## SYNTAX

### Alle

```
Enable-WSManCredSSP [[-DelegateComputer] <String[]>] [-Force] [-Role] <String> [<CommonParameters>]
```

## DESCRIPTION

Das- `Enable-WSManCredSSP` Cmdlet aktiviert die Authentifizierung auf einem Client oder auf einem Server Computer.
Wenn die Authentifizierung mit der Authentifizierung verwendet wird, werden die Anmelde Informationen des Benutzers an einen Remote Computer übergeben, der authentifiziert werden soll. Diese Art der Authentifizierung ist für Befehle vorgesehen, die eine Remote Sitzung aus einer anderen Remote Sitzung erstellen. Wenn Sie z. b. einen Hintergrund Auftrag auf einem Remote Computer ausführen möchten, verwenden Sie diese Art der Authentifizierung.

`Enable-WSManCredSSP` kann "kredssp" auf einem **Client** oder einem **Server** aktivieren. Geben Sie zum Aktivieren von "kredssp" auf einem Client im **Role** -Parameter " **Client** " an. Clients delegieren explizite Anmelde Informationen an einen Server, wenn die Server Authentifizierung erfolgt ist. Geben Sie im **Role** -Parameter " **Server** " an, um "up" auf einem Server zu aktivieren. Ein Server fungiert als Delegat für Clients. Weitere Informationen finden Sie im Abschnitt zu den Parametern unter **Rolle** .

> [!CAUTION]
> Bei der-Authentifizierung werden die Anmelde Informationen des Benutzers vom lokalen Computer an einen Remote Computer delegiert. Dieser Vorgang erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, während Anmeldeinformationen an ihn übergeben werden, können die Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

## BEISPIELE

### Beispiel 1: Delegieren von Client Anmelde Informationen

In diesem Beispiel können die Client Anmelde Informationen mithilfe des voll qualifizierten Domänen Namens an einen Computer delegiert werden.

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "Server02.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### Beispiel 2: Delegieren von Client Anmelde Informationen an alle Computer in einer Domäne

In diesem Beispiel können die Client Anmelde Informationen an alle Computer in der **Fabrikam.com** -Domäne delegiert werden. Das Sternchen ()-Platzhalter Zeichen `*` gibt alle Computer an.

> [!NOTE]
> Durch die Verwendung von Platzhaltern mit dem Parameter " **delegatecomputer** " kann "kredssp" auf mehr Computern als notwendig aktiviert werden.

```powershell
Enable-WSManCredSSP -Role "Client" -DelegateComputer "*.fabrikam.com"
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

### Beispiel 3: Delegieren von Client Anmelde Informationen an mehrere Computer

In diesem Beispiel können die Client Anmelde Informationen an mehrere Computer delegiert werden.

```powershell
$servers = "server02.fabrikam.com", "server03.fabrikam.com", "server04.fabrikam.com"
Enable-WSManCredSSP -Role "Client" -DelegateComputer $servers
```

```Output
cfg         : http://schemas.microsoft.com/wbem/wsman/1/config/client/auth
lang        : en-US
Basic       : true
Digest      : true
Kerberos    : true
Negotiate   : true
Certificate : true
CredSSP     : true
```

Die- `$servers` Variable enthält eine Liste von Servernamen. `Enable-WSManCredSSP` verwendet den **Role** -Parameter, um die **Client** Rolle anzugeben. Der **delegatecomputer** Ruft die Computernamen aus der `$servers` Variablen ab.

### Beispiel 4: zulassen, dass ein Computer als Delegat fungiert

In diesem Beispiel kann ein Computer als Delegat für einen anderen fungieren. Das `Enable-WSManCredSSP` -Cmdlet, wie in den vorherigen Beispielen gezeigt, aktiviert nur die Authentifizierung auf dem Client und gibt die Remote Computer an, die in seinem Auftrag agieren können. Damit der Remote Computer als Delegat für den Client fungieren kann, muss das Element "kredssp" im **Dienst** Knoten von WSMan auf "true" festgelegt werden. In diesem Beispiel wird das Element "kredssp" im **Dienst** Knoten von WSMan auf "true" festgelegt.

```powershell
Enable-WSManCredSSP -Role "Server"
```

### Beispiel 5: zulassen, dass ein Computer mithilfe von Set-Item als Delegat fungiert

In diesem Beispiel kann ein Computer als Delegat für einen anderen Computer fungieren. Die `Enable-WSManCredSSP` in den vorherigen Beispielen gezeigten Befehle aktivieren die-Authentifizierung nur auf dem Client Computer und geben die Remote Computer an, die im Namen des Client Computers agieren können. Damit der Remotecomputer als Delegat für den Clientcomputer fungieren kann, muss das CredSSP-Element im Dienstverzeichnis des WSMan-Anbieters auf „True“ festgelegt werden.

```powershell
Connect-WSMan -ComputerName "server02"
Set-Item -Path "WSMan:\server02\service\auth\credSSP" -Value $True
```

`Connect-WSMan` erstellt eine Verbindung mit dem Remote Computer Server02. `Set-Item` verwendet den **path** -Parameter, um den Speicherort des **WSMAN** -Anbieters anzugeben. Mit dem **value** -Parameter wird die **Dienst** Einstellung auf true festgelegt.

## PARAMETERS

### -Delegatecomputer

Gibt Server an, an die Client Anmelde Informationen delegiert werden. Die bewährte Vorgehensweise besteht darin, vollständig qualifizierte Domänen Namen zu verwenden.

Platzhalter werden akzeptiert, können aber auch auf mehr Computern als notwendig aktiviert werden.

Wenn der **Role** -Parameter " **Client**" ist, müssen Sie diesen Parameter angeben. Wenn **Role** **Server** ist, geben Sie diesen Parameter nicht an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rolle

Gibt an, ob "kredssp" als Client oder als Server aktiviert werden soll. Die zulässigen Werte für diesen Parameter sind: **Client** und **Server**.

Wenn Sie den- **Client** angeben, werden die folgenden Aktionen ausgeführt. Diese Einstellungen ermöglichen es dem Client, nach erfolgreicher Serverauthentifizierung explizite Anmeldeinformationen an einen Server zu delegieren.

- Aktiviert "kredssp" auf dem Client.
- Legt die WS-Management Einstellung `\<localhost|computername\>\Client\Auth\CredSSP` auf "true" fest.
- Legt die Windows-kredssp-Richtlinie **allowfreshanmelde** Informationen auf dem Client auf **WSMAN/** Delegat fest.

Wenn Sie den **Server** angeben, werden die folgenden Aktionen ausgeführt. Durch diese Richtlinieneinstellung kann der Server als Delegat für Clients fungieren.

- Aktiviert die auf dem Server erstellten kredssp.
- Legt die WS-Management Einstellung `\<localhost|computername\>\Service\Auth\CredSSP` auf "true" fest.

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

Dieses Cmdlet akzeptiert keine Eingaben.

## AUSGABEN

### System.Xml.Xml-Element

Wenn die kredssp-Authentifizierung erfolgreich aktiviert wurde, generiert dieses Cmdlet ein **XmlElement** -Objekt.

## HINWEISE

Verwenden Sie zum Deaktivieren der dedssp-Authentifizierung das `Disable-WSManCredSSP` Cmdlet.

## VERWANDTE LINKS

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)

