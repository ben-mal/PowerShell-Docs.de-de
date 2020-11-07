---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: 36a03257d8241dbe7e9c851a95eaaa3e3dbbda27
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345543"
---
# Connect-PSSession

## ZUSAMMENFASSUNG
Stellt die Verbindung mit getrennten Sitzungen wieder her.

## SYNTAX

### Name (Standard)

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
  [<CommonParameters>]
```

### Sitzung

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
  [<CommonParameters>]
```

### Computernameguid

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
  -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
  [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
  [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Computername

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
  [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
  [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
  [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Connectionuriguid

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
  -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
  [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>]
  [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ConnectionUri

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
  [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
  [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>]
  [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
  [<CommonParameters>]
```

### Id

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das `Connect-PSSession` Cmdlet stellt erneut eine Verbindung mit vom Benutzer verwalteten PowerShell-Sitzungen ( **pssessions** ) her, die getrennt wurden. Es funktioniert für Sitzungen, die absichtlich getrennt sind, z. b. durch Verwendung des `Disconnect-PSSession` Cmdlets oder des Parameters " **indisconnectedsession** " des `Invoke-Command` Cmdlets, und von Benutzern, die versehentlich getrennt wurden, z. b. durch einen temporären Netzwerkausfall.

`Connect-PSSession` kann eine Verbindung mit einer getrennten Sitzung herstellen, die vom gleichen Benutzer gestartet wurde. Dazu zählen diejenigen, die von anderen Sitzungen auf anderen Computern gestartet oder getrennt wurden.

Allerdings `Connect-PSSession` kann keine Verbindung mit unterbrochenen oder geschlossenen Sitzungen oder interaktiven Sitzungen hergestellt werden, die mithilfe des `Enter-PSSession` Cmdlets gestartet wurden. Sie können auch keine Sitzungen mit Sitzungen verbinden, die von anderen Benutzern gestartet wurden, es sei denn, Sie geben die Anmeldeinformationen des Benutzers an, der die Sitzung erstellt hat.

Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Wiederherstellen der Verbindung mit einer Sitzung

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

Mit diesem Befehl wird die Verbindung mit der ITTask-Sitzung auf dem Computer Server01 wiederhergestellt.

Die Ausgabe zeigt, dass der Befehl erfolgreich ausgeführt wurde. Der **Status** der Sitzung wird geöffnet, und die **Verfügbarkeit** ist verfügbar. Dies bedeutet, dass Sie Befehle in der Sitzung ausführen können.

### Beispiel 2: Auswirkung der Trennung und erneuten Verbindungs Herstellung

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

Dieses Beispiel zeigt die Auswirkungen des Trennens und Neuverbindens einer Sitzung.

Der erste Befehl verwendet das `Get-PSSession` Cmdlet. Ohne den **ComputerName** -Parameter  ruft der Befehl nur Sitzungen ab, die in der aktuellen Sitzung erstellt wurden.

Die Ausgabe zeigt, dass mit dem Befehl die Sitzung „Backups“ auf dem lokalen Computer abgerufen wird. Der **Status** der Sitzung wird geöffnet, und die **Verfügbarkeit** ist verfügbar.

Der zweite Befehl verwendet das `Get-PSSession` Cmdlet, um die **PSSession** -Objekte abzurufen, die in der aktuellen Sitzung erstellt wurden, und das `Disconnect-PSSession` Cmdlet zum Trennen der Sitzungen. Die Ausgabe zeigt, dass, die Sitzung „Backups“ getrennt wurde. Der **Status** der Sitzung wird getrennt, und die **Verfügbarkeit** ist "None".

Der dritte Befehl verwendet das `Get-PSSession` Cmdlet, um die **PSSession** -Objekte abzurufen, die in der aktuellen Sitzung erstellt wurden, und das `Connect-PSSession` Cmdlet zum erneuten Verbinden der Sitzungen. Die Ausgabe zeigt, dass, die Sitzung „Backups“ neu verbunden wurde. Der **Status** der Sitzung wird geöffnet, und die **Verfügbarkeit** ist verfügbar.

Wenn Sie das `Connect-PSSession` Cmdlet für eine Sitzung verwenden, die nicht getrennt ist, hat der Befehl keine Auswirkungen auf die Sitzung und generiert keine Fehler.

### Beispiel 3: Reihe von Befehlen in einem Unternehmens Szenario

Diese Reihe von Befehlen zeigt, wie das `Connect-PSSession` Cmdlet in einem Unternehmens Szenario verwendet werden kann. In diesem Fall startet ein Systemadministrator einen Auftrag mit langer Ausführungszeit in einer Sitzung auf einem Remotecomputer. Nach dem Starten des Auftrags trennt der Administrator die Verbindung mit der Sitzung und kann nach Hause gehen.
Später am Abend meldet sich der Administrator bei Ihrem Heimcomputer an und überprüft, ob der Auftrag ausgeführt wird, bis er abgeschlossen ist.

Der Administrator erstellt zunächst eine Sitzung auf einem Remote Computer und führt ein Skript in der Sitzung aus. Der erste Befehl verwendet das `New-PSSession` Cmdlet, um die ittask-Sitzung auf dem Remote Computer Server01 zu erstellen. Der Befehl verwendet den **ConfigurationName** -Parameter , um die Sitzungskonfiguration von ITTasks anzugeben. Der Befehl speichert die Sitzungen in der `$s` Variablen.

Das zweite Befehls- `Invoke-Command` Cmdlet zum Starten eines Hintergrund Auftrags in der Sitzung in der `$s` Variablen. Er verwendet den **FilePath** -Parameter, um das Skript im Hintergrundauftrag auszuführen.

Der dritte Befehl verwendet das `Disconnect-PSSession` Cmdlet, um die Verbindung mit der Sitzung in der Variablen zu trennen `$s` . Der Befehl verwendet den **OutputBufferingMode** -Parameter mit dem Wert Drop, um zu verhindern, dass das Skript blockiert wird, weil es die Ausgabe an die Sitzung liefern muss. Er verwendet den **idletimeoutsec** -Parameter, um das Sitzungs Timeout auf 15 Stunden zu verlängern. Wenn der Befehl abgeschlossen ist, sperrt der Administrator Ihren Computer und wechselt für den Abend zu Hause.

Zu einem späteren Zeitpunkt startet der Administrator Ihren Heimcomputer, meldet sich beim Unternehmensnetzwerk an und startet PowerShell. Der vierte Befehl verwendet das `Get-PSSession` Cmdlet, um die Sitzungen auf dem Server01-Computer zu erhalten. Der Befehl findet die ittask-Sitzung. Der fünfte Befehl verwendet das `Connect-PSSession` Cmdlet, um eine Verbindung mit der ittask-Sitzung herzustellen. Der Befehl speichert die Sitzung in der Variablen `$s`.

Der sechste Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Get-Job` Befehl in der Sitzung in der `$s` Variablen auszuführen. Die Ausgabe zeigt, dass der Auftrag erfolgreich abgeschlossen wurde. Der siebte Befehl verwendet das `Invoke-Command` Cmdlet, um einen Befehl in der Sitzung in der- `Receive-Job` `$s` Variable in der Sitzung auszuführen. Der Befehl speichert die Ergebnisse in der `$BackupSpecs` Variablen. Der achte Befehl verwendet das `Invoke-Command` Cmdlet zum Ausführen eines weiteren Skripts in der Sitzung. Der Befehl verwendet den Wert der `$BackupSpecs` Variablen in der Sitzung als Eingabe für das Skript.

```
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

Der neunte Befehl trennt die Verbindung mit der Sitzung in der `$s` Variablen. Der Administrator schließt PowerShell und schließt den Computer. Am nächsten Tag kann er die Sitzung neu verbinden und den Skriptstatus auf dem Computer am Arbeitsplatz überprüfen.

## PARAMETERS

### -Zuweisung Richtung

Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an einen alternativen URI zulässt.

Bei Verwendung des **ConnectionURI** -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben. Standardmäßig werden Verbindungen von PowerShell nicht umgeleitet, aber Sie können diesen Parameter verwenden, um die Umleitung der Verbindung zuzulassen.

Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern. Verwenden Sie den **maximumredirect** -Parameter des `New-PSSessionOption` Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der **$PSSessionOption** Preference-Variablen fest. Der Standardwert ist 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Gibt den Namen einer Anwendung an. Dieses Cmdlet stellt nur Verbindungen mit Sitzungen her, die die angegebene Anwendung verwenden.

Geben Sie das Anwendungsnamensegment des Verbindungs-URI ein. Im folgenden Verbindungs-URI lautet der Anwendungsname beispielsweise WSMAN: `http://localhost:5985/WSMAN` . Der Anwendungsname einer Sitzung wird in der **Runspace.ConnectionInfo.AppName** -Eigenschaft der Sitzung gespeichert.

Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern. Er ändert nicht die von der Sitzung verwendete Anwendung.

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Authentifizierung

Gibt den Mechanismus an, der zum Authentifizieren der Benutzer Anmelde Informationen im Befehl verwendet wird, um die Verbindung mit der getrennten Sitzung wiederherzustellen. Zulässige Werte für diesen Parameter:

- Standard
- Einfach
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential

Der Standardwert ist Default.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in der MSDN Library.

> [!CAUTION]
> Die CredSSP (Credential Security Support Provider)-Authentifizierung, bei der die Anmeldeinformationen des Benutzers zur Authentifizierung an einen Remotecomputer übergeben werden, ist für Befehle konzipiert, die die Authentifizierung auf mehr als einer Ressource erfordern, z. B. beim Zugriff auf eine Remotenetzwerkfreigabe. Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certifiupethumschlag-Print

Gibt das digitale Zertifikat für öffentliche Schlüssel (X.509) eines Benutzerkontos mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an. Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet. Sie können nur lokalen Benutzerkonten zugeordnet werden. Sie funktionieren nicht mit Domänen Konten.

Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie einen- `Get-Item` `Get-ChildItem` Befehl oder den-Befehl im PowerShell-Laufwerk "CERT:".

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt die Computer an, auf denen die Sitzungen gespeichert sind. Sitzungen werden auf dem Server gespeichert, der sich auf dem Server oder am Ende einer Verbindung befindet. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen vollqualifizierten Domänennamen eines Computers ein. Platzhalterzeichen sind nicht zulässig. Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameGuid, ComputerName
Aliases: Cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

Stellt nur eine Verbindung mit Sitzungen her, die die angegebene Sitzungskonfiguration verwenden.

Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein. Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/powershell` . Der Konfigurationsname einer Sitzung befindet sich in der **ConfigurationName** -Eigenschaft der Sitzung.

Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern. Er ändert nicht die von der Sitzung verwendete Sitzungskonfiguration.

Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Gibt die URIs der Verbindungs Endpunkte für die getrennten Sitzungen an.

Der URI muss vollqualifiziert sein. Das Format dieser Zeichenfolge lautet wie folgt:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

Der Standardwert lautet:

`http://localhost:5985/WSMAN`

Wenn Sie keinen Verbindungs-URI angeben, können Sie die Parameter " **US** " und " **Port** " verwenden, um die Verbindungs-URI-Werte anzugeben.

Gültige Werte für das **Transport** -Segment des URI sind „HTTP“ und „HTTPS“. Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS. Wenn Sie die Standardports für PowerShell-Remoting verwenden möchten, geben Sie Port 5985 für http oder 5986 für HTTPS an.

Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert PowerShell die Umleitung, es sei denn, Sie verwenden den Parameter " **Zuweisung** " im Befehl.

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. `User01` oder `Domain01\User01` , oder geben Sie ein `PSCredential` vom Cmdlet generiertes-Objekt ein `Get-Credential` . Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Gibt die IDs der getrennten Sitzungen an. Der **ID** -Parameter funktioniert nur, wenn die getrennte Sitzung zuvor mit der aktuellen Sitzung verbunden war.

Dieser Parameter ist gültig, aber nicht wirksam, wenn die Sitzung auf dem lokalen Computer gespeichert ist, aber nicht mit der aktuellen Sitzung verbunden wurde.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Gibt die Instanz-IDs von getrennten Sitzungen an.

Die Instanz-ID ist eine GUID, die eine **PSSession** auf einem lokalen Computer oder einem Remote Computer eindeutig identifiziert.

Die Instanz-ID wird in der **InstanceId-** Eigenschaft der **PSSession** gespeichert.

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt die Anzeigenamen von getrennten Sitzungen an.

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Gibt den Netzwerkport auf dem Remotecomputer an, der für die Verbindungswiederherstellung mit der Sitzung verwendet wird. Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören. Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).

Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren. Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der PowerShell-Eingabeaufforderung ein:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Verwenden Sie den **Port** -Parameter nur, wenn es unbedingt notwendig ist. Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird. Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.

```yaml
Type: System.Int32
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sitzung

Gibt die getrennten Sitzungen an. Geben Sie eine Variable ein, die die **PSSession** -Objekte enthält, oder einen Befehl, der die **PSSession** -Objekte erstellt oder abruft, z `Get-PSSession` . b. einen Befehl.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
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

Die Sitzungs Optionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der `$PSSessionOption` Preference-Variablen und in der Sitzungs Konfiguration festgelegt sind. Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.

Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter `New-PSSessionOption` . Weitere Informationen zur **$PSSessionOption** Preference-Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md). Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.
Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.

Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -US-

Gibt an, dass dieses Cmdlet das Secure Sockets Layer (SSL)-Protokoll zum Herstellen einer Verbindung mit der getrennten Sitzung verwendet. Standardmäßig wird SSL nicht verwendet.

WS-Management verschlüsselt alle über das Netzwerk übertragenen PowerShell-Inhalte. Der Parameter " **eessl** " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-Verbindung anstelle einer HTTP-Verbindung sendet.

Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. Runspaces. PSSession

Sie können eine Sitzung ( **PSSession** ) über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### System. Management. Automation. Runspaces. PSSession

Dieses Cmdlet gibt ein Objekt zurück, das die Sitzung darstellt, mit der die Verbindung wieder hergestellt wird.

## HINWEISE

- Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

- `Connect-PSSession` stellt nur eine Verbindung mit Sitzungen her, die getrennt sind, d. h. Sitzungen, deren Wert für die **State** -Eigenschaft getrennt ist. Nur Sitzungen, die mit einem Computer verbunden sind, auf dem Windows PowerShell 3,0 oder höhere Versionen ausgeführt werden, können getrennt und wieder verbunden werden.

- Wenn Sie `Connect-PSSession` in einer Sitzung verwenden, die nicht getrennt ist, hat der Befehl keine Auswirkungen auf die Sitzung und generiert keine Fehler.

- Getrennte Loopback Sitzungen mit interaktiven Tokens, die mit dem **enablenetworkaccess** -Parameter erstellt werden, können nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde. Diese Einschränkung schützt den Computer vor böswilligem Zugriff.

- Der Wert der **State** -Eigenschaft einer **PSSession** ist relativ zur aktuellen Sitzung.
  Daher bedeutet der Wert " **getrennt** ", dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist. Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist. Sie kann mit einer anderen Sitzung verbunden sein. Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.

  Ein **Availability** -Wert von None gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann. Der Wert ausgelastet gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.

  Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) in der MSDN Library.

  Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) in der MSDN Library.

- Wenn Sie eine Verbindung mit der **PSSession** herstellen, können Sie den Timeout Wert für das Leerlauf einer **PSSession** nicht ändern. Der **sessionoption** -Parameter von verwendet `Connect-PSSession` ein **sessionoption** -Objekt, das über einen **IdleTimeout** -Wert verfügt. Der **IdleTimeout** -Wert des **sessionoption** -Objekts und der **IdleTimeout** -Wert der `$PSSessionOption` Variablen werden jedoch beim Herstellen einer Verbindung mit einer **PSSession** ignoriert.

  Sie können das Leerlauf Timeout einer **PSSession** festlegen und ändern, wenn Sie die **PSSession** erstellen, indem Sie die- `New-PSSession` oder- `Invoke-Command` Cmdlets verwenden und die Verbindung mit der **PSSession** trennen.

  Die **IdleTimeout** -Eigenschaft einer **PSSession** ist wichtig für getrennte Sitzungen, da Sie bestimmt, wie lange eine getrennte Sitzung auf dem Remote Computer beibehalten wird. Getrennte Sitzungen gelten vom Moment ihrer Trennung an als im Leerlauf, selbst wenn Befehle in der getrennten Sitzung ausgeführt werden.

## VERWANDTE LINKS

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Receive-PSSession](Receive-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Remove-PSSession](Remove-PSSession.md)
