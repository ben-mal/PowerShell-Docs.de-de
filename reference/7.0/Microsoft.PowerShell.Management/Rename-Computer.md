---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: 2fc21594a4765a0901f61dba7b7f1a79f3259886
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346138"
---
# Rename-Computer

## ZUSAMMENFASSUNG
Benennt einen Computer um.

## SYNTAX

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Rename-Computer` Cmdlet benennt den lokalen Computer oder einen Remote Computer um.
Es benennt einen Computer in jedem Befehl um.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Umbenennen des lokalen Computers

Mit diesem Befehl wird der lokale Computer in umbenannt `Server044` und dann neu gestartet, damit die Änderung wirksam wird.

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### Beispiel 2: Umbenennen eines Remote Computers

Mit diesem Befehl wird der `Srv01` Computer in umbenannt `Server001` . Der Computer wird nicht neu gestartet.

Mit dem **domaincredential** -Parameter werden die Anmelde Informationen eines Benutzers angegeben, der über die Berechtigung zum Umbenennen von Computern in der Domäne verfügt.

Der **Force** -Parameter unterdrückt die Bestätigungsaufforderung.

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## PARAMETERS

### -ComputerName

Benennt den angegebenen Remotecomputer um.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein.
Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt ( `.` ) oder ein `localhost` .

Dieser Parameter beruht nicht auf PowerShell-Remoting.
Sie können den **Computername** -Parameter `Rename-Computer` auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Domaincredential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit der Domäne verfügt.
Zum Umbenennen eines der Domäne hinzugefügten Computers sind explizite Anmeldeinformationen erforderlich.

Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.

Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit dem durch den **ComputerName** -Parameter angegebenen Computer verfügt, mit dem **LocalCredential** -Parameter an.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.

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

### -Localcredential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Herstellen einer Verbindung mit dem durch den **ComputerName** -Parameter angegebenen Computer verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt.

Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

Geben Sie ein Benutzerkonto, das über die Berechtigung zum Herstellen einer Verbindung mit der Domäne verfügt, mit dem **DomainCredential** -Parameter an.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### -Newname

Gibt einen neuen Namen für den Computer an.
Dieser Parameter ist erforderlich.

Standard Namen dürfen Buchstaben ( `a-z` ), ( `A-Z` ), Zahlen ( `0-9` ) und Bindestriche ( `-` ), jedoch keine Leerzeichen oder Punkte ( `.` ) enthalten. Der Name darf nicht vollständig aus Ziffern bestehen und darf nicht länger als 63 Zeichen sein.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru

Gibt die Ergebnisse des Befehls zurück.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

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

### -Restart

Gibt an, dass mit diesem Cmdlet der umbenannte Computer neu gestartet wird.
Ein Neustart ist häufig erforderlich, damit die Änderung wirksam wird.

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

### -Wsmanauthentication

Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet. Zulässige Werte für diesen Parameter:

- **Basic**
- **CredSSP**
- **Standard**
- **Digest**
- **Kerberos**
- **Verhandelt**

Der Standardwert lautet **Default**.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!WARNING]
> Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern
> Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.
> Wenn der Remote Computer kompromittiert ist, können die an ihn weiter gegebenen Anmelde Informationen verwendet werden, um > die Netzwerksitzung zu steuern.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Keine

Dieses Cmdlet enthält keine Parameter, die eine Eingabe nach Wert annehmen. Sie können jedoch die Werte der Eigenschaften **ComputerName** und **NewName** von Objekten über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### Microsoft. PowerShell. Commands. computerchangeingefo

Dieses Cmdlet gibt ein **computerchangeinfo** -Objekt zurück, wenn Sie den **passthru** -Parameter angeben.
Andernfalls wird keine Ausgabe zurückgegeben.

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

## VERWANDTE LINKS

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
