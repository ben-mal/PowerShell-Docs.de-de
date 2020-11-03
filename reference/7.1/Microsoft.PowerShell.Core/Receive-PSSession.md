---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-PSSession
ms.openlocfilehash: 71a17d71cf7bfdbc6ef14d0eb6949a366cb8c233
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218780"
---
# Receive-PSSession

## ZUSAMMENFASSUNG

Ruft die Ergebnisse von Befehlen in getrennten Sitzungen ab.

## SYNTAX

### Sitzung (Standard)

```
Receive-PSSession [-Session] <PSSession> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Id

```
Receive-PSSession [-Id] <Int32> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Computer Sitzungsname

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Computerinstanceid

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Connectionurisessionname

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Connectionuriinstanceid

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Receive-PSSession -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Sessionname

```
Receive-PSSession -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Receive-PSSession` Cmdlet ruft die Ergebnisse von Befehlen ab, die in PowerShell-Sitzungen ( **PSSession** ) ausgeführt werden, die getrennt wurden. Wenn die Sitzung zurzeit verbunden ist, ruft `Receive-PSSession` die Ergebnisse von Befehlen ab, die beim Trennen der Sitzung ausgeführt wurden. Wenn die Sitzung weiterhin getrennt ist, stellt `Receive-PSSession` eine Verbindung mit der Sitzung her, setzt alle angehaltenen Befehle fort und ruft die Ergebnisse der Befehle ab, die in der Sitzung ausgeführt werden.

Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.

Sie können einen `Receive-PSSession` zusätzlich zu oder anstelle eines `Connect-PSSession` Befehls verwenden.
`Receive-PSSession` kann eine Verbindung mit einer getrennten oder wieder verbundenen Sitzung herstellen, die in anderen Sitzungen oder auf anderen Computern gestartet wurde.

`Receive-PSSession` funktioniert bei **pssessions** , die mithilfe des- `Disconnect-PSSession` Cmdlets oder des `Invoke-Command` **indisconnectedsession** -Parameters absichtlich getrennt wurden. Oder nicht versehentlich durch eine Netzwerk Unterbrechung getrennt.

Wenn Sie mit dem `Receive-PSSession` Cmdlet eine Verbindung mit einer Sitzung herstellen, in der keine Befehle ausgeführt oder angehalten werden, wird eine Verbindung `Receive-PSSession` mit der Sitzung hergestellt, es werden jedoch keine Ausgaben oder Fehler zurückgegeben.

Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).

In einigen Beispielen werden Verteilung verwendet, um die Zeilenlänge zu verringern und die Lesbarkeit zu verbessern. Weitere Informationen finden Sie unter [about_Splatting](./About/about_Splatting.md).

## BEISPIELE

### Beispiel 1: Herstellen einer Verbindung mit einer PSSession

In diesem Beispiel wird eine Verbindung mit einer Sitzung auf einem Remote Computer hergestellt, und die Ergebnisse von Befehlen, die in einer Sitzung ausgeführt werden, werden abgerufen.

```powershell
Receive-PSSession -ComputerName Server01 -Name ITTask
```

Der `Receive-PSSession` gibt den Remote Computer mit dem **Computername** -Parameter an. Der **Name** -Parameter identifiziert die ittask-Sitzung auf dem Server01-Computer. Das Beispiel ruft die Ergebnisse der Befehle ab, die in der ittask-Sitzung ausgeführt wurden.

Da der Befehl den **outtarget** -Parameter nicht verwendet, werden die Ergebnisse in der Befehlszeile angezeigt.

### Beispiel 2: erhalten der Ergebnisse aller Befehle für getrennte Sitzungen

In diesem Beispiel werden die Ergebnisse aller Befehle abgerufen, die in allen getrennten Sitzungen auf zwei Remote Computern ausgeführt werden.

Wenn eine Sitzung nicht getrennt wurde oder Befehle nicht ausgeführt werden, wird von keine `Receive-PSSession` Verbindung mit der Sitzung hergestellt, und es werden keine Ausgaben oder Fehler zurückgegeben.

```powershell
Get-PSSession -ComputerName Server01, Server02 | Receive-PSSession
```

`Get-PSSession` verwendet den **Computername** -Parameter, um die Remote Computer anzugeben. Die Objekte werden über die Pipeline an gesendet `Receive-PSSession` .

### Beispiel 3: erhalten der Ergebnisse eines Skripts, das in einer Sitzung ausgeführt wird

In diesem Beispiel wird das- `Receive-PSSession` Cmdlet verwendet, um die Ergebnisse eines Skripts zu erhalten, das in einer Remote Computersitzung ausgeführt wurde.

```powershell
$parms = @{
  ComputerName = "Server01"
  Name = "ITTask"
  OutTarget = "Job"
  JobName = "ITTaskJob01"
  Credential = "Domain01\Admin01"
}
Receive-PSSession @parms
```

```Output
Id     Name            State         HasMoreData     Location
--     ----            -----         -----------     --------
16     ITTaskJob01     Running       True            Server01
```

Der Befehl verwendet die Parameter **ComputerName** und **Name** , um die getrennte Sitzung zu identifizieren.
Er verwendet den **outtarget** -Parameter mit einem Wert von Job, um `Receive-PSSession` die Ergebnisse als Auftrag zurückzugeben. Der **Jobname** -Parameter gibt einen Namen für den Auftrag in der wieder verbundenen Sitzung an.
Der Parameter **Credential** führt den `Receive-PSSession` Befehl mit den Berechtigungen eines Domänen Administrators aus.

Die Ausgabe zeigt, dass `Receive-PSSession` die Ergebnisse als Auftrag in der aktuellen Sitzung zurückgegeben hat. Um die Auftrags Ergebnisse zu erhalten, verwenden Sie einen `Receive-Job` Befehl.

### Beispiel 4: Ergebnisse nach einem Netzwerkausfall erhalten

In diesem Beispiel wird das- `Receive-PSSession` Cmdlet verwendet, um die Ergebnisse eines Auftrags zu erhalten, nachdem ein Netzwerkausfall eine Sitzungs Verbindung unterbrochen hat. PowerShell versucht automatisch, die Sitzung einmal pro Sekunde in den nächsten vier Minuten erneut zu verbinden, und bricht den Aufwand nur ab, wenn alle Versuche im vierminütigen Intervall fehlschlagen.

```
PS> $s = New-PSSession -ComputerName Server01 -Name AD -ConfigurationName ADEndpoint
PS> $s

Id  Name   ComputerName    State        ConfigurationName     Availability
--  ----   ------------    -----        -----------------     ------------
8   AD      Server01       Opened       ADEndpoint               Available


PS> Invoke-Command -Session $s -FilePath \\Server12\Scripts\SharedScripts\New-ADResolve.ps1

Running "New-ADResolve.ps1"

# Network outage
# Restart local computer
# Network access is not re-established within 4 minutes


PS> Get-PSSession -ComputerName Server01

Id  Name   ComputerName    State          ConfigurationName      Availability
--  ----   ------------    -----          -----------------      ------------
1  Backup  Server01        Disconnected   Microsoft.PowerShell           None
8  AD      Server01        Disconnected   ADEndpoint                     None


PS> Receive-PSSession -ComputerName Server01 -Name AD -OutTarget Job -JobName AD

Job Id   Name      State         HasMoreData     Location
--       ----      -----         -----------     --------
16       ADJob     Running       True            Server01


PS> Get-PSSession -ComputerName Server01

Id  Name    ComputerName    State         ConfigurationName     Availability
--  ----    ------------    -----         -----------------     ------------
1  Backup   Server01        Disconnected  Microsoft.PowerShell          Busy
8  AD       Server01        Opened        ADEndpoint               Available
```

Das `New-PSSession` -Cmdlet erstellt eine Sitzung auf dem Server01-Computer und speichert die Sitzung in der `$s` Variablen. Die `$s` -Variable zeigt an, dass der **Status** geöffnet und die **Verfügbarkeit** verfügbar ist. Diese Werte geben an, dass Sie mit der Sitzung verbunden sind und Befehle in der Sitzung ausführen können.

Das- `Invoke-Command` Cmdlet führt ein Skript in der-Sitzung in der- `$s` Variable aus. Die Skriptausführung beginnt, und es werden Daten zurückgegeben, aber die Sitzung wird durch einen Netzwerkausfall unterbrochen. Der Benutzer muss die Sitzung beenden und den lokalen Computer neu starten.

Wenn der Computer neu gestartet wird, startet der Benutzer PowerShell und führt einen `Get-PSSession` Befehl aus, um Sitzungen auf dem Server01-Computer zu erhalten. Die Ausgabe zeigt, dass die **AD** -Sitzung auf dem Server01-Computer weiterhin vorhanden ist. Der **Status** gibt an, dass die **AD** -Sitzung getrennt ist. Der **Verfügbarkeits** Wert None gibt an, dass die Sitzung nicht mit Client Sitzungen verbunden ist.

Das `Receive-PSSession` Cmdlet stellt erneut eine Verbindung mit der **AD** -Sitzung her und ruft die Ergebnisse des Skripts ab, das in der Sitzung ausgeführt wurde. Der Befehl verwendet den **outtarget** -Parameter, um die Ergebnisse in einem Auftrag mit dem Namen " **ADJob** " anzufordern. Der Befehl gibt ein Auftrags Objekt zurück, und die Ausgabe gibt an, dass das Skript noch ausgeführt wird.

Das- `Get-PSSession` Cmdlet wird verwendet, um den Auftragsstatus zu überprüfen. Die Ausgabe bestätigt, dass das `Receive-PSSession` Cmdlet erneut eine Verbindung mit der **AD** -Sitzung hergestellt hat, die nun geöffnet ist und für Befehle verfügbar ist. Und das Skript wird die Ausführung fortgesetzt, und die Skript Ergebnisse werden erhalten.

### Beispiel 5: Wiederherstellen der Verbindung mit getrennten Sitzungen

In diesem Beispiel wird das `Receive-PSSession` -Cmdlet zum erneuten Verbinden mit Sitzungen verwendet, die absichtlich getrennt wurden, und die Ergebnisse von Aufträgen, die in den Sitzungen ausgeführt wurden, erhalten.

```
PS> $parms = @{
      InDisconnectedSession = $True
      ComputerName = "Server01", "Server02", "Server30"
      FilePath = "\\Server12\Scripts\SharedScripts\Get-BugStatus.ps1"
      Name = "BugStatus"
      SessionOption = @{IdleTimeout = 86400000}
      ConfigurationName = "ITTasks"
    }
PS> Invoke-Command @parms
PS> Exit


PS> $s = Get-PSSession -ComputerName Server01, Server02, Server30 -Name BugStatus
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Disconnected  ITTasks                       None
8  ITTask  Server02        Disconnected  ITTasks                       None
2  ITTask  Server30        Disconnected  ITTasks                       None


PS> $Results = Receive-PSSession -Session $s
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Opened        ITTasks                  Available
8  ITTask  Server02        Opened        ITTasks                  Available
2  ITTask  Server30        Opened        ITTasks                  Available


PS> $Results

Bug Report - Domain 01
----------------------
ComputerName          BugCount          LastUpdated
--------------        ---------         ------------
Server01              121               Friday, December 30, 2011 5:03:34 PM
```

Mit dem- `Invoke-Command` Cmdlet wird ein Skript auf drei Remote Computern ausgeführt. Da das Skript Daten aus mehreren Datenbanken sammelt und zusammenfasst, nimmt es häufig eine längere Zeit an, bis das Skript abgeschlossen ist. Der Befehl verwendet den **indisconnectedsession** -Parameter, der die Skripts startet und die Sitzungen dann sofort trennt. Der **sessionoption** -Parameter erweitert den **IdleTimeout** -Wert der getrennten Sitzung. Getrennte Sitzungen gelten ab dem Zeitpunkt, an dem Sie getrennt sind, als Leerlauf. Es ist wichtig, das Leerlauf Timeout für lange genug festzulegen, damit die Befehle ausgeführt werden können, und Sie können erneut eine Verbindung mit der Sitzung herstellen. Sie können " **IdleTimeout** " nur festlegen, wenn Sie die PSSession erstellen, und diese nur ändern, wenn Sie die Verbindung mit der **PSSession** trennen. Sie können den **IdleTimeout** -Wert nicht ändern, wenn Sie eine Verbindung mit einer **PSSession** herstellen oder Ergebnisse empfangen. Nachdem der Befehl ausgeführt wurde, beendet der Benutzer PowerShell und schließt den Computer.

Am nächsten Tag nimmt der Benutzer Windows an, startet PowerShell und verwendet `Get-PSSession` , um die Sitzungen zu erhalten, in denen die Skripts ausgeführt wurden. Der Befehl identifiziert die Sitzungen nach Computername, Sitzungsname und Name der Sitzungs Konfiguration und speichert die Sitzungen in der `$s` Variablen. Der Wert der `$s` Variablen wird angezeigt und zeigt an, dass die Sitzungen getrennt sind, aber nicht ausgelastet sind.

`Receive-PSSession`Mit dem-Cmdlet wird eine Verbindung mit den Sitzungen in der Variablen hergestellt, und die Ergebnisse werden abgerufen `$s` .
Der Befehl speichert die Ergebnisse in der `$Results` Variablen. Die `$s` Variable wird angezeigt und zeigt, dass die Sitzungen verbunden sind und für Befehle verfügbar sind.

Das Skript führt dazu, dass die `$Results` Variable in der PowerShell-Konsole angezeigt wird. Wenn eines der Ergebnisse unerwartet ist, kann der Benutzer Befehle in den Sitzungen ausführen, um die Ursache zu ermitteln.

### Beispiel 6: Ausführen eines Auftrags in einer getrennten Sitzung

Dieses Beispiel zeigt, was mit einem Auftrag geschieht, der in einer getrennten Sitzung ausgeführt wird.

```
PS> $s = New-PSSession -ComputerName Server01 -Name Test
PS> $j = Invoke-Command -Session $s { 1..1500 | Foreach-Object {"Return $_"; sleep 30}} -AsJob
PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Running       True            Server01


PS> $s | Disconnect-PSSession

Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server01        Disconnected  Microsoft.PowerShell          None


PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Disconnected  True            Server01


PS> Receive-Job $j -Keep

Return 1
Return 2


PS> $s2 = Connect-PSSession -ComputerName Server01 -Name Test
PS> $j2 = Receive-PSSession -ComputerName Server01 -Name Test
PS> Receive-Job $j

Return 3
Return 4
```

Mit dem- `New-PSSession` Cmdlet wird die Test Sitzung auf dem Server01-Computer erstellt. Der Befehl speichert die Sitzung in der Variablen `$s`.

Das- `Invoke-Command` Cmdlet führt einen Befehl in der Sitzung in der `$s` Variablen aus. Der Befehl verwendet den **AsJob** -Parameter, um den Befehl als Auftrag auszuführen, und erstellt das Auftrags Objekt in der aktuellen Sitzung.
Der Befehl gibt ein Auftrags Objekt zurück, das in der `$j` Variablen gespeichert ist. Die- `$j` Variable zeigt das Auftrags Objekt an.

Das Sitzungs Objekt in der `$s` Variablen wird an die Pipeline gesendet, `Disconnect-PSSession` und die Sitzung wird getrennt.

Die `$j` Variable wird angezeigt und zeigt die Auswirkung der Trennung des Auftrags Objekts in der `$j` Variablen an. Der Status des Auftrags ist nun „Getrennt“.

Der `Receive-Job` wird für den Auftrag in der `$j` Variablen ausgeführt. Die Ausgabe zeigt, dass der Auftrag mit der Rückgabe der Ausgabe vor der Sitzung begonnen hat und der Auftrag getrennt wurde.

Das- `Connect-PSSession` Cmdlet wird in derselben Client Sitzung ausgeführt. Der Befehl stellt erneut eine Verbindung mit der Test Sitzung auf dem Computer Server01 her und speichert die Sitzung in der `$s2` Variablen.

Mit dem- `Receive-PSSession` Cmdlet werden die Ergebnisse des Auftrags abgerufen, der in der Sitzung ausgeführt wurde. Da der Befehl in derselben Sitzung ausgeführt wird, werden `Receive-PSSession` die Ergebnisse standardmäßig als Auftrag zurückgegeben, und das gleiche Auftrags Objekt wird erneut verwendet. Der Befehl speichert den Auftrag in der `$j2` Variablen. Das- `Receive-Job` Cmdlet ruft die Ergebnisse des Auftrags in der `$j` Variablen ab.

## PARAMETERS

### -Zuweisung Richtung

Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an eine Alternative Uniform Resource Identifier (URI) zulässt.

Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben. Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um eine Umleitung der Verbindung zu ermöglichen.

Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern. Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der `$PSSessionOption` Preference-Variablen fest. Der Standardwert ist 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Gibt eine Anwendung an. Dieses Cmdlet stellt nur Verbindungen mit Sitzungen her, die die angegebene Anwendung verwenden.

Geben Sie das Anwendungsnamensegment des Verbindungs-URI ein. Im folgenden Verbindungs-URI ist WSMAN z. b. der Anwendungsname: `http://localhost:5985/WSMAN` .

Der Anwendungsname einer Sitzung wird in der **Runspace.ConnectionInfo.AppName** -Eigenschaft der Sitzung gespeichert.

Der Wert des Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern. Die von der Sitzung verwendete Anwendung wird nicht geändert.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Authentifizierung

Gibt den Mechanismus an, der zum Authentifizieren der Benutzer Anmelde Informationen im Befehl verwendet wird, um die Verbindung mit einer getrennten Sitzung wiederherzustellen. Zulässige Werte für diesen Parameter:

- Standard
- Basic
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential

Der Standardwert ist Default.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certifiupethumschlag-Print

Gibt das digitale Zertifikat für öffentliche Schlüssel (X.509) eines Benutzerkontos mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Zertifikate können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänen Konten.

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie einen- `Get-Item` `Get-ChildItem` Befehl oder den-Befehl im PowerShell- `Cert:` Laufwerk.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt den Computer an, auf dem die getrennte Sitzung gespeichert ist. Sitzungen werden auf dem Server, der sich auf dem Server befindet, oder am Ende einer Verbindung gespeichert. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Computers ein.
Platzhalter Zeichen sind nicht zulässig. Um den lokalen Computer anzugeben, geben Sie den Computernamen, einen Punkt ( `.` ), `$env:COMPUTERNAME` oder einen localhost ein.

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationName

Gibt den Namen einer Sitzungs Konfiguration an. Dieses Cmdlet stellt nur Verbindungen mit Sitzungen her, die die angegebene Sitzungs Konfiguration verwenden.

Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein. Wenn Sie nur den Konfigurationsnamen angeben, wird der folgende Schema-URI vorangestellt:

`http://schemas.microsoft.com/powershell`.

Der Konfigurationsname einer Sitzung befindet sich in der **ConfigurationName** -Eigenschaft der Sitzung.

Der Wert des Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern. Die Sitzungs Konfiguration, die von der Sitzung verwendet wird, wird nicht geändert.

Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](./About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Gibt einen URI an, der den Verbindungs Endpunkt definiert, der zum erneuten Herstellen der Verbindung mit der getrennten Sitzung verwendet wird.

Der URI muss vollqualifiziert sein. Das Zeichen folgen Format lautet wie folgt:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

Der Standardwert lautet:

`http://localhost:5985/WSMAN`

Wenn Sie keinen Verbindungs-URI angeben, können Sie die Parameter " **US** ", " **Computername** ", " **Port** " und " **ApplicationName** " verwenden, um die Verbindungs-URI-Werte anzugeben.

Gültige Werte für das **Transport** -Segment des URI sind „HTTP“ und „HTTPS“. Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS. Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.

Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.

```yaml
Type: System.Uri
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases: URI, CU

Required: True
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Gibt die ID einer getrennten Sitzung an. Der **ID** -Parameter funktioniert nur, wenn die getrennte Sitzung zuvor mit der aktuellen Sitzung verbunden war.

Dieser Parameter ist gültig, aber nicht wirksam, wenn die Sitzung auf dem lokalen Computer gespeichert, aber nicht mit der aktuellen Sitzung verbunden ist.

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InstanceId

Gibt die Instanz-ID der getrennten Sitzung an. Die Instanz-ID ist eine GUID, die eine **PSSession** auf einem lokalen Computer oder einem Remote Computer eindeutig identifiziert. Die Instanz-ID wird in der **InstanceId-** Eigenschaft der **PSSession** gespeichert.

```yaml
Type: System.Guid
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jobname

Gibt einen anzeigen Amen für den Auftrag an, der `Receive-PSSession` zurückgibt.

`Receive-PSSession` Gibt einen Auftrag zurück, wenn der Wert des **outtarget** -Parameters "Job" ist oder der Auftrag, der in der getrennten Sitzung ausgeführt wird, in der aktuellen Sitzung gestartet wurde.

Wenn der Auftrag, der in der getrennten Sitzung ausgeführt wird, in der aktuellen Sitzung gestartet wurde, verwendet PowerShell das ursprüngliche Auftrags Objekt in der Sitzung erneut und ignoriert den Wert des **Jobname** -Parameters.

Wenn der Auftrag, der in der getrennten Sitzung ausgeführt wird, in einer anderen Sitzung gestartet wurde, erstellt PowerShell ein neues Auftrags Objekt. Es wird ein Standardname verwendet, aber Sie können diesen Parameter verwenden, um den Namen zu ändern.

Wenn der Standardwert oder der explizite Wert des **outtarget** -Parameters nicht "Job" ist, ist der Befehl erfolgreich, aber der **Jobname** -Parameter hat keine Auswirkungen.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt den Anzeigenamen der getrennten Sitzung an.

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ConnectionUriSessionName, SessionName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Outtarget

Bestimmt, wie die Sitzungsergebnisse zurückgegeben werden. Zulässige Werte für diesen Parameter:

- **Auftrag**. Gibt die Ergebnisse asynchron in ein Auftragsobjekt zurück. Sie können den **JobName** -Parameter verwenden, um einen Namen oder einen neuen Namen für den Auftrag festzulegen.
- **Host**. Gibt die Ergebnisse (synchron) an die Befehlszeile zurück. Wenn der Befehl fortgesetzt wird oder die Ergebnisse aus einer großen Anzahl von Objekten bestehen, kann die Antwort verzögert werden.

Der Standardwert des **outtarget** -Parameters ist Host. Wenn der Befehl, der in einer getrennten Sitzung empfangen wird, in der aktuellen Sitzung gestartet wurde, ist der Standardwert des **outtarget** -Parameters das Formular, in dem der Befehl gestartet wurde. Wenn der Befehl als Auftrag gestartet wurde, wird er standardmäßig als Auftrag zurückgegeben. Andernfalls wird Sie standardmäßig an das Host Programm zurückgegeben.

In der Regel zeigt das Hostprogramm die zurückgegebenen Objekte ohne Verzögerung in der Befehlszeile an, dieses Verhalten kann jedoch variieren.

```yaml
Type: Microsoft.PowerShell.Commands.OutTarget
Parameter Sets: (All)
Aliases:
Accepted values: Default, Host, Job

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Gibt den Netzwerkport des Remote Computers an, der zum erneuten Herstellen der Verbindung mit der Sitzung verwendet wird. Zum Herstellen einer Verbindung mit einem Remote Computer muss der Port, der von der Verbindung verwendet wird, überwacht werden. Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).

Vor der Verwendung eines alternativen Ports müssen Sie den WinRM-Listener auf dem Remote Computer so konfigurieren, dass er an diesem Port lauscht. Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der PowerShell-Eingabeaufforderung ein:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Verwenden Sie den **Port** -Parameter nur, wenn dies erforderlich ist. Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird. Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sitzung

Gibt die getrennte Sitzung an. Geben Sie eine Variable ein, die die **PSSession** oder einen Befehl enthält, der die **PSSession** erstellt oder abruft, z. b. einen- `Get-PSSession` Befehl.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Sessionoption

Gibt erweiterte Optionen für die Sitzung an. Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem `New-PSSessionOption` Cmdlet erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.

Die Standardwerte für die Optionen werden durch den Wert der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt. Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.

Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind. Allerdings haben Sie Vorrang vor maximalen Werten, Kontingenten oder Grenzwerten, die in der Sitzungs Konfiguration festgelegt sind.

Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` . Weitere Informationen zur **$PSSessionOption** Preference-Variablen finden Sie unter [about_Preference_Variables](./About/about_Preference_Variables.md). Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](./About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -US-

Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll zum Herstellen einer Verbindung mit der getrennten Sitzung verwendet. Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte. **UseSSL** ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-Verbindung anstatt über eine HTTP-Verbindung sendet.

Wenn Sie diesen Parameter verwenden und SSL nicht an dem Port verfügbar ist, der für den Befehl verwendet wird, schlägt der Befehl fehl.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: False
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

### System. Management. Automation. Runspaces. PSSession

Sie können Sitzungs Objekte über die Pipeline an dieses Cmdlet übergeben, z. b `Get-PSSession` . die vom Cmdlet zurückgegebenen Objekte.

### System.Int32

Sie können Sitzungs-IDs an dieses Cmdlet weiterreichen.

### System.Guid

Sie können die Instanz-IDs von Sitzungen dieses Cmdlets über die Pipeline übergeben.

### System.String

Sie können Sitzungs Namen an dieses Cmdlet weiterreichen.

## AUSGABEN

### System. Management. Automation. Job oder psobject

Mit diesem Cmdlet werden die Ergebnisse von Befehlen zurückgegeben, die ggf. in der getrennten Sitzung ausgeführt wurden. Wenn der Wert oder der Standardwert des **outtarget** -Parameters "Job" ist, wird `Receive-PSSession` ein Auftrags Objekt zurückgegeben. Andernfalls werden Objekte zurückgeben, die diese Befehlsergebnisse darstellen.

## HINWEISE

`Receive-PSSession` Ruft Ergebnisse nur aus Sitzungen ab, die getrennt wurden. Nur Sitzungen, die mit einem Computer verbunden sind, auf dem PowerShell 3,0 oder höhere Versionen ausgeführt werden, können getrennt und erneut verbunden werden.

Wenn die Befehle, die in der getrennten Sitzung ausgeführt wurden, keine Ergebnisse generiert haben oder die Ergebnisse bereits an eine andere Sitzung zurückgegeben wurden, `Receive-PSSession` generiert keine Ausgabe.

Der Ausgabepuffer Modus einer Sitzung bestimmt, wie die Befehle in der Sitzung die Ausgabe verwalten, wenn die Sitzung getrennt wird. Wenn der Wert der **outputbufferingmode** -Option der Sitzung Drop und der Ausgabepuffer voll ist, beginnt der Befehl mit dem Löschen der Ausgabe. `Receive-PSSession` Diese Ausgabe kann nicht wieder hergestellt werden. Weitere Informationen zur Option "Output bufferingmode" finden Sie in den Hilfe Artikeln für die Cmdlets " [New-pssessionoption](New-PSSessionOption.md) " und " [New-pstransportoption](New-PSTransportOption.md) ".

Sie können den Leerlauf Timeout Wert einer **PSSession** nicht ändern, wenn Sie eine Verbindung mit der **PSSession** herstellen oder Ergebnisse empfangen. Der **sessionoption** -Parameter von verwendet `Receive-PSSession` ein **sessionoption** -Objekt, das über einen **IdleTimeout** -Wert verfügt. Der **IdleTimeout** -Wert des **sessionoption** -Objekts und der **IdleTimeout** -Wert der `$PSSessionOption` Variablen werden jedoch ignoriert, wenn eine Verbindung mit einer **PSSession** hergestellt oder Ergebnisse empfangen werden.

- Sie können das Leerlauf Timeout einer **PSSession** festlegen und ändern, wenn Sie die **PSSession** erstellen, indem Sie die- `New-PSSession` oder- `Invoke-Command` Cmdlets verwenden und die Verbindung mit der **PSSession** trennen.
- Die **IdleTimeout** -Eigenschaft einer **PSSession** ist wichtig für getrennte Sitzungen, da Sie bestimmt, wie lange eine getrennte Sitzung auf dem Remote Computer beibehalten wird. Getrennte Sitzungen gelten vom Moment ihrer Trennung an als im Leerlauf, selbst wenn Befehle in der getrennten Sitzung ausgeführt werden.

Wenn Sie einen Auftrag in einer Remote Sitzung starten, indem Sie den **AsJob** -Parameter des `Invoke-Command` Cmdlets verwenden, wird das Auftrags Objekt in der aktuellen Sitzung erstellt, auch wenn der Auftrag in der Remote Sitzung ausgeführt wird. Wenn Sie die Remote Sitzung trennen, wird das Auftrags Objekt in der aktuellen Sitzung vom Auftrag getrennt. Das Auftrags Objekt enthält alle Ergebnisse, die an es zurückgegeben wurden, empfängt aber keine neuen Ergebnisse aus dem Auftrag in der getrennten Sitzung.

Wenn ein anderer Client eine Verbindung mit der Sitzung herstellt, die den laufenden Auftrag enthält, sind die Ergebnisse, die an das ursprüngliche Auftrags Objekt in der ursprünglichen Sitzung übermittelt wurden, in der neu verbundenen Sitzung nicht verfügbar. Nur Ergebnisse, die nicht an das ursprüngliche Auftragsobjekt übermittelt wurden, sind in der neu verbundenen Sitzung verfügbar.

Wenn Sie ein Skript in einer Sitzung starten und dann die Verbindung mit der Sitzung trennen, sind alle Ergebnisse, die das Skript vor der Trennung an die Sitzung übergibt, nicht für einen anderen Client verfügbar, der eine Verbindung mit der Sitzung herstellt.

Verwenden Sie den **indisconnectedsession** -Parameter des Cmdlets, um Datenverluste in Sitzungen zu vermeiden, die Sie trennen möchten `Invoke-Command` . Da dieser Parameter verhindert, dass Ergebnisse an die aktuelle Sitzung zurückgegeben werden, sind alle Ergebnisse verfügbar, wenn die Verbindung mit der Sitzung wiederhergestellt wird.

Sie können auch Datenverlust verhindern, indem Sie mit dem- `Invoke-Command` Cmdlet einen `Start-Job` Befehl in der Remote Sitzung ausführen. In diesem Fall wird das Auftragsobjekt in der Remotesitzung erstellt. Sie können das `Receive-PSSession` Cmdlet nicht verwenden, um die Auftrags Ergebnisse zu erhalten. Verwenden Sie stattdessen das `Connect-PSSession` Cmdlet, um eine Verbindung mit der Sitzung herzustellen, und verwenden Sie dann das `Invoke-Command` Cmdlet, um einen `Receive-Job` Befehl in der Sitzung auszuführen.

Wenn eine Sitzung, die einen laufenden Auftrag enthält, getrennt und die Verbindung wieder hergestellt wird, wird das ursprüngliche Auftrags Objekt nur dann wieder verwendet, wenn der Auftrag getrennt und wieder mit der gleichen Sitzung verbunden wird und der Befehl zum Wiederherstellen der Verbindung keinen neuen Auftrags Namen angibt. Wenn die Sitzung erneut mit einer anderen Client Sitzung verbunden ist oder ein neuer Auftrags Name angegeben wird, erstellt PowerShell ein neues Auftrags Objekt für die neue Sitzung.

Wenn Sie eine **PSSession** trennen, wird der Sitzungs Status getrennt, und die Verfügbarkeit ist None.

- Der Wert der **State** Eigenschaft bezieht sich auf die aktuelle Sitzung. Der Wert "getrennt" bedeutet, dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist. Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist. Sie kann mit einer anderen Sitzung verbunden sein.
  Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.
- Ein **Availability** -Wert von None gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann. Der Wert ausgelastet gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.
- Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate](/dotnet/api/system.management.automation.runspaces.runspacestate) in der MSDN Library.
- Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

## VERWANDTE LINKS

[about_PSSessions](./About/about_PSSessions.md)

[about_Remote](./About/about_Remote.md)

[about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md)

[about_Session_Configurations](./About/about_Session_Configurations.md)

[Connect-PSSession](Connect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Remove-PSSession](Remove-PSSession.md)

