---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: d4f071b4c106735e622281f728b8632c211a813d
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218247"
---
# Connect-PSSession

## ZUSAMMENFASSUNG
Stellt die Verbindung mit getrennten Sitzungen wieder her.

## SYNTAX

### Name (Standard)

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Sitzung

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Computername

```
Connect-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Computernameguid

```
Connect-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ConnectionUri

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Connectionuriguid

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das **Connect-PSSession-** Cmdlet stellt erneut eine Verbindung mit vom Benutzer verwalteten Windows PowerShell-Sitzungen ( **pssessions** ) her, die getrennt wurden.
Es funktioniert für Sitzungen, die absichtlich getrennt werden, z. b. durch die Verwendung des Disconnect-PSSession-Cmdlets oder des *indisconnectedsession* -Parameters des Invoke-Command-Cmdlets, und von Benutzern, die versehentlich getrennt wurden, z. b. durch einen temporären Netzwerkausfall.

**Connect-PSSession** kann eine Verbindung mit einer getrennten Sitzung herstellen, die vom gleichen Benutzer gestartet wurde.
Dazu zählen diejenigen, die von anderen Sitzungen auf anderen Computern gestartet oder getrennt wurden.

**Connect-PSSession** kann jedoch keine Verbindung mit unterbrochenen oder geschlossenen Sitzungen oder interaktiven Sitzungen herstellen, die mit dem Cmdlet "Enter-PSSession" gestartet wurden.
Sie können auch keine Sitzungen mit Sitzungen verbinden, die von anderen Benutzern gestartet wurden, es sei denn, Sie geben die Anmeldeinformationen des Benutzers an, der die Sitzung erstellt hat.

Weitere Informationen zum Feature „Getrennte Sitzungen“ finden Sie unter [about_Remote_Disconnected_Sessions](About/about_Remote_Disconnected_Sessions.md).

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

Die Ausgabe zeigt, dass der Befehl erfolgreich ausgeführt wurde.
Der **Status** der Sitzung wird geöffnet, und die **Verfügbarkeit** ist verfügbar. Dies bedeutet, dass Sie Befehle in der Sitzung ausführen können.

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

Der erste Befehl verwendet das Cmdlet "Get-PSSession".
Ohne den *ComputerName* -Parameter  ruft der Befehl nur Sitzungen ab, die in der aktuellen Sitzung erstellt wurden.

Die Ausgabe zeigt, dass mit dem Befehl die Sitzung „Backups“ auf dem lokalen Computer abgerufen wird.
Der **Status** der Sitzung wird geöffnet, und die **Verfügbarkeit** ist verfügbar.

Der zweite Befehl verwendet das **Get-PSSession** -Cmdlet, um die **PSSession** -Objekte abzurufen, die in der aktuellen Sitzung erstellt wurden, und das **Disconnect-PSSession-** Cmdlet zum Trennen der Sitzungen.
Die Ausgabe zeigt, dass, die Sitzung „Backups“ getrennt wurde.
Der **Status** der Sitzung wird getrennt, und die **Verfügbarkeit** ist "None".

Der dritte Befehl verwendet das **Get-PSSession** -Cmdlet, um die **PSSession** -Objekte abzurufen, die in der aktuellen Sitzung erstellt wurden, und das **Connect-PSSession** -Cmdlet zum erneuten Verbinden der Sitzungen.
Die Ausgabe zeigt, dass, die Sitzung „Backups“ neu verbunden wurde.
Der **Status** der Sitzung wird geöffnet, und die **Verfügbarkeit** ist verfügbar.

Wenn Sie das **Connect-PSSession** -Cmdlet für eine Sitzung verwenden, die nicht getrennt ist, hat der Befehl keine Auswirkungen auf die Sitzung und generiert keine Fehler.

### Beispiel 3: Reihe von Befehlen in einem Unternehmens Szenario

```
The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the **New-PSSession** cmdlet to create the ITTask session on the Server01 remote computer. The command uses the *ConfigurationName* parameter to specify the ITTasks session configuration. The command saves the sessions in the $s variable.
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks

 The second command **Invoke-Command** cmdlet to start a background job in the session in the $s variable. It uses the *FilePath* parameter to run the script in the background job.
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

The third command uses the Disconnect-PSSession cmdlet to disconnect from the session in the $s variable. The command uses the *OutputBufferingMode* parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session. It uses the *IdleTimeoutSec* parameter to extend the session time-out to 15 hours.When the command is completed, the administrator locks her computer and goes home for the evening.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts Windows PowerShell. The fourth command uses the Get-PSSession cmdlet to get the sessions on the Server01 computer. The command finds the ITTask session.The fifth command uses the **Connect-PSSession** cmdlet to connect to the ITTask session. The command saves the session in the $s variable.
PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

The sixth command uses the **Invoke-Command** cmdlet to run a Get-Job command in the session in the $s variable. The output shows that the job finished successfully.The seventh command uses the **Invoke-Command** cmdlet to run a Receive-Job command in the session in the $s variable in the session. The command saves the results in the $BackupSpecs variable.The eighth command uses the **Invoke-Command** cmdlet to runs another script in the session. The command uses the value of the $BackupSpecs variable in the session as input to the script.


PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

The ninth command disconnects from the session in the $s variable.The administrator closes Windows PowerShell and closes the computer. She can reconnect to the session on the next day and check the script status from her work computer.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

Diese Reihe von Befehlen zeigt, wie das **Connect-PSSession** -Cmdlet in einem Unternehmensszenario verwendet werden kann.
In diesem Fall startet ein Systemadministrator einen Auftrag mit langer Ausführungszeit in einer Sitzung auf einem Remotecomputer.
Nach dem Starten des Auftrags trennt der Administrator die Verbindung mit der Sitzung und kann nach Hause gehen.
Später am Abend meldet sich der Administrator bei Ihrem Heimcomputer an und überprüft, ob der Auftrag ausgeführt wird, bis er abgeschlossen ist.

## PARAMETERS

### -Zuweisung Richtung

Gibt an, dass dieses Cmdlet die Umleitung dieser Verbindung an einen alternativen URI zulässt.

Bei Verwendung des *ConnectionURI* -Parameters kann das Remoteziel eine Anweisung zum Umleiten an einen anderen URI zurückgeben.
Standardmäßig erfolgt mit Windows PowerShell keine Umleitung von Verbindungen, Sie können jedoch mit diesem Parameter die Umleitung von Verbindungen zulassen.

Sie können auch einschränken, wie oft die Verbindung umgeleitet wird, indem Sie den **MaximumConnectionRedirectionCount** -Optionswert der Sitzung ändern.
Verwenden Sie den Parameter *maximumredirect* des New-PSSessionOption-Cmdlets, oder legen Sie die **maximumconnectionredirectioncount** -Eigenschaft der **$PSSessionOption** Preference-Variablen fest.
Der Standardwert ist 5.

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

Gibt den Namen einer Anwendung an.
Dieses Cmdlet stellt nur Verbindungen mit Sitzungen her, die die angegebene Anwendung verwenden.

Geben Sie das Anwendungsnamensegment des Verbindungs-URI ein.
Im folgenden Verbindungs-URI lautet der Anwendungsname beispielsweise WSMAN: `http://localhost:5985/WSMAN` .
Der Anwendungsname einer Sitzung wird in der **Runspace.ConnectionInfo.AppName** -Eigenschaft der Sitzung gespeichert.

Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern.
Er ändert nicht die von der Sitzung verwendete Anwendung.

```yaml
Type: System.String
Parameter Sets: ComputerName, ComputerNameGuid
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
- Basic
- CredSSP
- Digest
- Kerberos
- Aushandeln
- NegotiateWithImplicitCredential

Der Standardwert ist Default.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in der MSDN Library.

Vorsicht: die Authentifizierung der Credential Security Support Provider (kredssp), bei der die Anmelde Informationen des Benutzers an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. den Zugriff auf eine Remote Netzwerkfreigabe.
Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.
Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
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

Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.
Sie können nur lokalen Benutzerkonten zugeordnet werden.
Sie funktionieren nicht mit Domänen Konten.

Verwenden Sie zum Abrufen eines Zertifikatfingerabdrucks den Befehl Get-Item oder Get-ChildItem im Windows PowerShell-Certificat:-Laufwerk.

```yaml
Type: System.String
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt die Computer an, auf denen die Sitzungen gespeichert sind.
Sitzungen werden auf dem Server gespeichert, der sich auf dem Server oder am Ende einer Verbindung befindet.
Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder einen vollqualifizierten Domänennamen eines Computers ein.
Platzhalterzeichen sind nicht zulässig.
Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.

```yaml
Type: System.String[]
Parameter Sets: ComputerName, ComputerNameGuid
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

Stellt nur eine Verbindung mit Sitzungen her, die die angegebene Sitzungskonfiguration verwenden.

Geben Sie einen Konfigurationsnamen oder den vollqualifizierten Ressourcen-URI für eine Sitzungskonfiguration ein.
Wenn Sie nur den Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt: `http://schemas.microsoft.com/powershell` .
Der Konfigurationsname einer Sitzung befindet sich in der **ConfigurationName** -Eigenschaft der Sitzung.

Der Wert dieses Parameters wird verwendet, um Sitzungen auszuwählen und zu filtern.
Er ändert nicht die von der Sitzung verwendete Sitzungskonfiguration.

Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Gibt die URIs der Verbindungs Endpunkte für die getrennten Sitzungen an.

Der URI muss vollqualifiziert sein.
Das Format dieser Zeichenfolge lautet wie folgt:

`\<Transport\>://\<ComputerName\>:\<Port\>/\<ApplicationName\>`

Der Standardwert lautet:

`http://localhost:5985/WSMAN`

Wenn Sie keinen Verbindungs-URI angeben, können Sie die Parameter " *US* " und " *Port* " verwenden, um die Verbindungs-URI-Werte anzugeben.

Gültige Werte für das **Transport** -Segment des URI sind „HTTP“ und „HTTPS“.
Wenn Sie einen Verbindungs-URI mit einem Transport Segment angeben, aber keinen Port angeben, wird die Sitzung mit Standardports erstellt: 80 für http und 443 für HTTPS.
Um die Standardports für Windows PowerShell-Remoting zu verwenden, geben Sie Port 5985 für HTTP bzw. 5986 für HTTPS an.

Wenn der Zielcomputer die Verbindung an einen anderen URI umleitet, verhindert Windows PowerShell die Umleitung, sofern Sie nicht den *AllowRedirection* -Parameter im Befehl verwenden.

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

Gibt ein Benutzerkonto mit der Berechtigung zum Herstellen einer Verbindung mit der getrennten Sitzung an.
Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** , oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.

Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.

> [!NOTE]
> Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Gibt die IDs der getrennten Sitzungen an.
Der *ID* -Parameter funktioniert nur, wenn die getrennte Sitzung zuvor mit der aktuellen Sitzung verbunden war.

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

Gibt den Netzwerkport auf dem Remotecomputer an, der für die Verbindungswiederherstellung mit der Sitzung verwendet wird.
Zum Herstellen einer Verbindung mit einem Remotecomputer muss der Remotecomputer den für die Verbindung verwendeten Port abhören.
Die Standardports sind 5985. Dies ist der WinRM-Port für http und 5986 (der WinRM-Port für HTTPS).

Bevor ein alternativer Port verwendet werden kann, müssen Sie den WinRM-Listener auf dem Remotecomputer für das Abhören an diesen Port konfigurieren.
Um den Listener zu konfigurieren, geben Sie die folgenden beiden Befehle an der Windows PowerShell-Eingabeaufforderung ein:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Verwenden Sie den *Port* -Parameter nur, wenn es unbedingt notwendig ist.
Der im Befehl festgelegte Port gilt für alle Computer oder Sitzungen, für die der Befehl ausgeführt wird.
Eine alternative Porteinstellung kann verhindern, dass der Befehl auf allen Computern ausgeführt wird.

```yaml
Type: System.Int32
Parameter Sets: ComputerName, ComputerNameGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sitzung

Gibt die getrennten Sitzungen an.
Geben Sie eine Variable ein, die die **PSSession** -Objekte enthält, oder einen Befehl, der die **PSSession** -Objekte erstellt oder abruft, z. b. einen Get-PSSession Befehl.

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

Gibt erweiterte Optionen für die Sitzung an.
Geben Sie ein **sessionoption** -Objekt ein, z. b. ein Objekt, das Sie mit dem Cmdlet "New-PSSessionOption" erstellen, oder eine Hash Tabelle, in der die Schlüssel Sitzungs Optionsnamen und die Werte Sitzungs Optionswerte sind.

Die Standardwerte für die Optionen werden durch den Wert der $PSSessionOption-Einstellungsvariablen bestimmt, sofern festgelegt.
Andernfalls werden die Standardwerte durch Optionen festgelegt, die in der Sitzungskonfiguration festgelegt sind.

Die Sitzungsoptionswerte haben Vorrang vor Standardwerten für Sitzungen, die in der $PSSessionOption-Einstellungsvariablen und in der Sitzungskonfiguration festgelegt sind.
Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind.

Eine Beschreibung der Sitzungs Optionen, die die Standardwerte enthalten, finden Sie unter New-pssessionoption.
Weitere Informationen zur **$PSSessionOption** Preference-Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).
Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
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

WS-Management verschlüsselt alle Windows PowerShell-Inhalte, die über das Netzwerk übertragen werden.
Der Parameter " *eessl* " ist ein zusätzlicher Schutz, der die Daten über eine HTTPS-Verbindung anstelle einer HTTP-Verbindung sendet.

Wenn Sie diesen Parameter verwenden, aber SSL auf dem Port, der für den Befehl verwendet wird, nicht verfügbar ist, schlägt der Befehl fehl.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, ComputerNameGuid
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

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen finden Sie unter "about_CommonParameters" (https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. Runspaces. PSSession

Sie können eine Sitzung ( **PSSession** ) über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### System. Management. Automation. Runspaces. PSSession

Dieses Cmdlet gibt ein Objekt zurück, das die Sitzung darstellt, mit der die Verbindung wieder hergestellt wird.

## HINWEISE

* **Connect-PSSession** stellt erneut eine Verbindung mit Sitzungen her, die getrennt sind, d. h. Sitzungen mit dem Wert "getrennt" für die Eigenschaft " **State** ". Nur Sitzungen, die mit einem Computer verbunden sind, auf dem Windows PowerShell 3,0 oder höhere Versionen ausgeführt werden, können getrennt und wieder verbunden werden.
* Wenn Sie **Connect-PSSession** für eine Sitzung verwenden, die nicht getrennt ist, hat der Befehl keine Auswirkungen auf die Sitzung und generiert keine Fehler.
* Getrennte Loopback Sitzungen mit interaktiven Tokens, die mit dem *enablenetworkaccess* -Parameter erstellt werden, können nur von dem Computer wieder hergestellt werden, auf dem die Sitzung erstellt wurde. Diese Einschränkung schützt den Computer vor böswilligem Zugriff.
* Der Wert der **State** -Eigenschaft einer **PSSession** ist relativ zur aktuellen Sitzung.
Daher bedeutet der Wert " **getrennt** ", dass die **PSSession** nicht mit der aktuellen Sitzung verbunden ist. Dies bedeutet jedoch nicht, dass die **PSSession** von allen Sitzungen getrennt ist. Sie kann mit einer anderen Sitzung verbunden sein. Um festzustellen, ob Sie eine Sitzungsverbindung herstellen bzw. wiederherstellen können, verwenden Sie die **Availability** -Eigenschaft.

  Ein **Availability** -Wert von None gibt an, dass eine Verbindung mit der Sitzung hergestellt werden kann.
Der Wert ausgelastet gibt an, dass keine Verbindung mit der **PSSession** hergestellt werden kann, da Sie mit einer anderen Sitzung verbunden ist.

  Weitere Informationen zu den Werten der **State** -Eigenschaft von Sitzungen finden Sie unter [runspacestate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) in der MSDN Library.

  Weitere Informationen zu den Werten der **Availability** -Eigenschaft von Sitzungen finden Sie unter [runspaceavailability-Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) in der MSDN Library.

* Wenn Sie eine Verbindung mit der **PSSession** herstellen, können Sie den Timeout Wert für das Leerlauf einer **PSSession** nicht ändern. Der *SessionOption* -Parameter von **Connect-PSSession** benötigt ein **SessionOption** -Objekt, das einen **IdleTimeout** -Wert hat. Der **IdleTimeout** -Wert des **sessionoption** -Objekts und der **IdleTimeout** -Wert der $PSSessionOption-Variablen werden jedoch beim Herstellen einer Verbindung mit einer **PSSession** ignoriert.

  Sie können das Leerlauf Timeout einer **PSSession** festlegen und ändern, wenn Sie die **PSSession** erstellen, indem Sie die Cmdlets **New-PSSession** oder **aufrufen-Command** verwenden und die Verbindung mit der **PSSession** trennen.

  Die **IdleTimeout** -Eigenschaft einer **PSSession** ist wichtig für getrennte Sitzungen, da Sie bestimmt, wie lange eine getrennte Sitzung auf dem Remote Computer beibehalten wird.
Getrennte Sitzungen gelten vom Moment ihrer Trennung an als im Leerlauf, selbst wenn Befehle in der getrennten Sitzung ausgeführt werden.

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
