---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: 59e70f75ac9d822db00419d84055d92a3882c11d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596760"
---
# New-CimSession

## ZUSAMMENFASSUNG

Erstellt eine CIM-Sitzung.

## SYNTAX

### "Kredentialparameterset" (Standard)

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### Certificateparameterset

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## DESCRIPTION

Das- `New-CimSession` Cmdlet erstellt eine CIM-Sitzung. Eine CIM-Sitzung ist ein Client seitiges Objekt, das eine Verbindung mit einem lokalen Computer oder einem Remote Computer darstellt. Die CIM-Sitzung enthält Informationen über die Verbindung, z. b. **Computername**, das verwendete Protokoll oder verschiedene Bezeichner.

Dieses Cmdlet gibt ein CIM-Sitzungs Objekt zurück, das von allen anderen CIM-Cmdlets verwendet werden kann.

## BEISPIELE

### Beispiel 1: Erstellen einer CIM-Sitzung mit Standardoptionen

In diesem Beispiel wird eine lokale CIM-Sitzung mit Standardoptionen erstellt. Wenn **Computername** nicht angegeben ist, wird `New-CimSession` von eine DCOM-Sitzung auf dem lokalen Computer erstellt.

```powershell
New-CimSession
```

### Beispiel 2: Erstellen einer CIM-Sitzung für einen bestimmten Computer

Dieses Beispiel erstellt eine CIM-Sitzung auf dem Computer, der von **Computername** angegeben wird.
Standardmäßig `New-CimSession` wird von eine WSMAN-Sitzung erstellt, wenn **Computername** angegeben wird.

```powershell
New-CimSession -ComputerName Server01
```

### Beispiel 3: Erstellen einer CIM-Sitzung auf mehreren Computern

Dieses Beispiel erstellt eine CIM-Sitzung für jeden Computer, der von **Computername** angegeben wird, in der durch Trennzeichen getrennten Liste.

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### Beispiel 4: Erstellen einer CIM-Sitzung mit einem anzeigen Amen

In diesem Beispiel wird eine Remote-CIM-Sitzung für jeden Computer, der in **Computername** angegeben ist, in der durch Trennzeichen getrennten Liste erstellt und den neuen Sitzungen ein Anzeige Name zugewiesen, indem der **Name** angegeben wird.

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

Sie können den anzeigen Amen einer CIM-Sitzung verwenden, um in anderen CIM-Cmdlets auf die Sitzung zu verweisen, z. b. " [Get-cimsession](Get-CimSession.md)".

### Beispiel 5: Erstellen einer CIM-Sitzung auf einem Computer mithilfe eines PSCredential-Objekts

In diesem Beispiel wird eine CIM-Sitzung auf dem Computer **namens** erstellt, der das von " **Credential**" angegebene **PSCredential** -Objekt verwendet, und der durch die **Authentifizierung** angegebene Authentifizierungstyp.

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

Sie können ein **PSCredential** -Objekt mit dem [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) Cmdlet erstellen.

### Beispiel 6: Erstellen einer CIM-Sitzung auf einem Computer mit einem bestimmten Port

Dieses Beispiel erstellt eine CIM-Sitzung auf dem Computer, der von **Computername** unter Verwendung des durch den **Port** angegebenen TCP-Ports angegeben wird.

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### Beispiel 7: Erstellen einer CIM-Sitzung mithilfe von DCOM

Dieses Beispiel erstellt eine CIM-Sitzung unter Verwendung des verteilten com-Protokolls (DCOM) anstelle von WSMAN.

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## PARAMETERS

### -Authentifizierung

Gibt den für die Anmelde Informationen des Benutzers verwendeten Authentifizierungstyp an. Zulässige Werte für diesen Parameter:

- Standard
- Digest
- Aushandeln
- Basic
- Kerberos
- Quot ntlmdomain
- CredSsp

Der Authentifizierungstyp **ntlmdomain** kann nicht für die Verbindung mit dem lokalen Computer verwendet werden. Die **kredssp** -Authentifizierung ist nur in Windows Vista, Windows Server 2008 und neueren Versionen von Windows verfügbar.

> [!CAUTION]
> Die Authentifizierung des Sicherheits Diensts für Anmelde Informationen (Security Service Provider, kredssp) ist für Befehle konzipiert, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. auf eine Remote Netzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: CredentialParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Certifiupethumschlag-Print

Gibt das digitale Zertifikat für öffentliche Schlüssel (X. 509) eines Benutzerkontos an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie das- [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) Cmdlet oder das-Cmdlet im PowerShell-Zertifikat Anbieter.

Weitere Informationen finden Sie unter [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).

```yaml
Type: System.String
Parameter Sets: CertificateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Gibt den Namen des Computers an, auf dem die CIM-Sitzung erstellt werden soll. Geben Sie entweder einen einzelnen Computernamen oder mehrere Computernamen durch Kommas getrennt an.

Wenn **Computername** nicht angegeben ist, wird eine CIM-Sitzung zum lokalen Computer erstellt. Sie können den Wert für Computername in einem der folgenden Formate angeben:

- Mindestens ein NetBIOS-Name
- Mindestens eine IP-Adresse
- Mindestens ein voll qualifizierter Domänen Name.

Wenn sich der Computer in einer anderen Domäne als der Benutzer befindet, müssen Sie den voll qualifizierten Domänen Namen angeben.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Wenn **Credential** nicht angegeben ist, wird das aktuelle Benutzerkonto verwendet.

Geben Sie den Wert für die Anmelde Informationen in einem der folgenden **Formate an:**

- Ein Benutzername: "USER01"
- Ein Domänen Name und ein Benutzername: "Domain01\User01"
- Ein Benutzer Prinzipal Name: " User@Domain.com "
- Ein PSCredential-Objekt, z. b. ein vom Cmdlet zurück gegebenes Objekt [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) .

Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt einen anzeigen Amen für die CIM-Sitzung an.

Sie können den Namen verwenden, um auf die CIM-Sitzung zu verweisen, wenn Sie andere Cmdlets verwenden, z. b. das Cmdlet " [Get-cimsession](Get-CimSession.md) ".
Der Name muss für den Computer oder die aktuelle Sitzung nicht eindeutig sein.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Operationtimeoutsec

Die Dauer, für die das Cmdlet auf eine Antwort vom Server wartet.

Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.

Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port

Gibt den Netzwerkport an dem für diese Verbindung verwendeten Remotecomputer an. Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören. Die Standardports sind 5985 (der WinRM-Port für HTTP) und 5986 (der WinRM-Port für HTTPS).

Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren. Verwenden Sie die folgenden Befehle, um den Listener zu konfigurieren:

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

Verwenden Sie den **Port**-Parameter nur, wenn es unbedingt notwendig ist. Die Porteinstellung im Befehl gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird. Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sessionoption

Legt Erweiterte Optionen für die neue CIM-Sitzung fest. Geben Sie den Namen eines **cimsessionoption** -Objekts ein, das mit dem [`New-CimSessionOption`](New-CimSessionOption.md) Cmdlet erstellt wurde.

```yaml
Type: Microsoft.Management.Infrastructure.Options.CimSessionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Skiptestconnection

Standardmäßig stellt das `New-CimSession` Cmdlet aus zwei Gründen eine Verbindung mit einem Remote WS-Management-Endpunkt her: um zu überprüfen, ob der Remote Server die mit dem **Port** -Parameter angegebene Portnummer überwacht und die angegebenen Konto Anmelde Informationen zu überprüfen. Die Überprüfung erfolgt mit einem Standard WS-Identity Vorgang. Sie können den Switch-Parameter **skiptestconnection** hinzufügen, wenn der Remote WS-Management-Endpunkt WS-Identifizierungs Server nicht verwenden kann, oder um die Daten Übertragungszeit zu verringern.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Keine

Dieses Cmdlet akzeptiert keine Eingaben.

## AUSGABEN

### Microsoft.Management.Infrastructure.CimSession

## HINWEISE

## VERWANDTE LINKS

[Get-ChildItem](../Microsoft.Powershell.Management/Get-ChildItem.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Get-Item](../Microsoft.Powershell.Management/Get-Item.md)

[Get-CimSession](Get-CimSession.md)

[Remove-CimSession](Remove-CimSession.md)

[New-CimSessionOption](New-CimSessionOption.md)

[about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)

