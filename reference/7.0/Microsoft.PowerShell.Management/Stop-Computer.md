---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: 9ba056a7c85b62ac02137959a5586fdd87d9ceb4
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346308"
---
# Stop-Computer

## ZUSAMMENFASSUNG
Beendet den lokalen Computer und Remotecomputer (fährt sie herunter).

## SYNTAX

### Alle

```
Stop-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem `Stop-Computer` -Cmdlet werden der lokale Computer und Remote Computer heruntergefahren.

Mit den Parametern von können Sie `Stop-Computer` die Authentifizierungs Ebenen und Alternative Anmelde Informationen angeben und ein sofortiges Herunterfahren erzwingen.

## BEISPIELE

### Beispiel 1: Herunterfahren des lokalen Computers

In diesem Beispiel wird der lokale Computer heruntergefahren.

```powershell
Stop-Computer -ComputerName localhost
```

### Beispiel 2: Herunterfahren von zwei Remote Computern und dem lokalen Computer

In diesem Beispiel werden zwei Remote Computer und der lokale Computer angehalten.

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

`Stop-Computer` verwendet den **Computername** -Parameter, um zwei Remote Computer und den lokalen Computer anzugeben. Jeder Computer wird heruntergefahren.

### Beispiel 3: Herunterfahren von Remote Computern als Hintergrund Auftrag

In diesem Beispiel wird `Stop-Computer` als Hintergrund Auftrag auf zwei Remote Computern ausgeführt.

Der Background-Operator `&` führt den `Stop-Computer` Befehl als Hintergrund Auftrag aus. Weitere Informationen finden Sie unter [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" &
$results = $j | Receive-Job
$results
```

`Stop-Computer` verwendet den **Computername** -Parameter, um zwei Remote Computer anzugeben. Der `&` Background-Operator führt den Befehl als Hintergrund Auftrag aus. Die Auftrags Objekte werden in der `$j` Variablen gespeichert.

Die Auftrags Objekte in der `$j` Variablen werden an die Pipeline gesendet `Receive-Job` , die die Auftrags Ergebnisse abruft. Die-Objekte werden in der- `$results` Variable gespeichert. Die `$results` Variable zeigt die Auftrags Informationen in der PowerShell-Konsole an.

### Beispiel 4: Herunterfahren eines Remote Computers

In diesem Beispiel wird ein Remote Computer mithilfe der angegebenen Authentifizierung heruntergefahren.

```powershell
Stop-Computer -ComputerName "Server01" -WsmanAuthentication Kerberos
```

`Stop-Computer` verwendet den **Computername** -Parameter, um den Remote Computer anzugeben. Der **wsmanauthentication** -Parameter gibt an, dass Kerberos verwendet werden soll, um eine Remote Verbindung herzustellen.

### Beispiel 5: Herunterfahren von Computern in einer Domäne

In diesem Beispiel erzwingen die Befehle ein sofortiges Herunterfahren aller Computer in einer angegebenen Domäne.

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -Credential $c
```

`Get-Content` verwendet den **path** -Parameter, um eine Datei im aktuellen Verzeichnis mit der Liste der Domänen Computer zu erhalten. Die-Objekte werden in der- `$s` Variable gespeichert.

`Get-Credential` verwendet den **Credential** -Parameter, um die Anmelde Informationen eines Domänen Administrators anzugeben. Die Anmelde Informationen werden in der `$c` Variablen gespeichert.

`Stop-Computer` fährt die Computer herunter, die mit der Liste der Computer des Computer **Name** -Parameters in der Variablen angegeben werden `$s` . Der **Force** -Parameter erzwingt ein sofortiges Herunterfahren. Mit dem **Credential** -Parameter werden die in der Variablen gespeicherten Anmelde Informationen übermittelt `$c` .

## PARAMETERS

### -ComputerName

Gibt die zu stoppenden Computer an. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, die IP-Adresse oder den vollqualifizierten Domänennamen eines Computers oder mehrerer Computer in einer durch Trennzeichen getrennten Liste ein. Geben Sie den Computernamen oder localhost ein, um den lokalen Computer anzugeben.

Dieser Parameter beruht nicht auf PowerShell-Remoting. Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt ein sofortiges Herunterfahren des Computers.

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

### -Wsmanauthentication

Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet. Der Standardwert lautet **Default**.

Zulässige Werte für diesen Parameter:

- Einfach
- CredSSP
- Standard
- Digest
- Kerberos
- Negotiate

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

Dieser Parameter wurde in PowerShell 3,0 eingeführt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
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

### Keine

Eingaben können nicht an dieses Cmdlet übergeben werden.

## AUSGABEN

### Keine

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

Dieses Cmdlet funktioniert nur unter Windows und verwendet die **Win32Shutdown** -Methode der WMI-Klasse **Win32_OperatingSystem** . Diese Methode erfordert, dass die **SeShutdownPrivilege** -Berechtigung für das Benutzerkonto aktiviert ist, mit dem der Computer neu gestartet wird.

## VERWANDTE LINKS

[Rename-Computer](Rename-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Test-Connection](Test-Connection.md)
