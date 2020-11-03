---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: 10f086c3fc2090681f669d481eb880d81ea9d245
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216407"
---
# New-PSSessionOption

## ZUSAMMENFASSUNG
Erstellt ein Objekt, das erweiterte Optionen für eine PSSession enthält.

## SYNTAX

```
New-PSSessionOption [-MaximumRedirection <Int32>] [-NoCompression] [-NoMachineProfile] [-Culture <CultureInfo>]
 [-UICulture <CultureInfo>] [-MaximumReceivedDataSizePerCommand <Int32>] [-MaximumReceivedObjectSize <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-MaxConnectionRetryCount <Int32>]
 [-ApplicationArguments <PSPrimitiveDictionary>] [-OpenTimeout <Int32>] [-CancelTimeout <Int32>]
 [-IdleTimeout <Int32>] [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <AuthenticationMechanism>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [-IncludePortInSPN] [<CommonParameters>]
```

## DESCRIPTION

Das- `New-PSSessionOption` Cmdlet erstellt ein Objekt, das erweiterte Optionen für eine vom Benutzer verwaltete Sitzung ( **PSSession** ) enthält. Sie können das-Objekt als Wert des **sessionoption** -Parameters von Cmdlets verwenden, die eine **PSSession** erstellen, `New-PSSession` z `Enter-PSSession` . b `Invoke-Command` ., und.

Ohne Parameter `New-PSSessionOption` generiert ein Objekt, das die Standardwerte für alle Optionen enthält. Da alle Eigenschaften bearbeitet werden können, können Sie das resultierende Objekt als Vorlage verwenden und Standardoptionsobjekte für Ihr Unternehmen erstellen.

Sie können ein Sitzungs Options Objekt auch in der `$PSSessionOption` Preference-Variablen speichern. Die Werte dieser Variablen richten neue Standardwerte für die Sitzungsoptionen ein. Sie sind gültig, wenn keine Sitzungsoptionen für die Sitzung festgelegt sind, und haben Vorrang vor Optionen, die in der Sitzungskonfiguration festgelegt sind. Durch Angabe von Sitzungsoptionen oder einem Sitzungsoptionsobjekt in einem Cmdlet, das eine Sitzung erstellt, können Sie sie jedoch überschreiben. Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).

Wenn Sie ein Sitzungsoptionsobjekt in einem Cmdlet verwenden, das eine Sitzung erstellt, haben die Sitzungsoptionswerte Vorrang vor Standardwerten für Sitzungen, die in der $PSSessionOption-Einstellungsvariablen und der Sitzungskonfiguration festgelegt sind. Allerdings haben sie nicht Vorrang vor Höchstwerten, Kontingenten oder Grenzwerten, die in der Sitzungskonfiguration festgelegt sind. Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

## BEISPIELE

### Beispiel 1: Erstellen einer Standard Sitzungs Option

Mit diesem Befehl wird ein Sitzungs Options Objekt erstellt, das alle Standardwerte aufweist.

```powershell
New-PSSessionOption
```

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

### Beispiel 2: Konfigurieren einer Sitzung mithilfe eines Sitzungs Options Objekts

In diesem Beispiel wird gezeigt, wie Sie eine Sitzung mit einem Sitzungsoptionsobjekt konfigurieren.

```powershell
$pso = New-PSSessionOption -Culture "fr-fr" -MaximumReceivedObjectSize 10MB
New-PSSession -ComputerName Server01 -SessionOption $pso
```

Mit dem ersten Befehl wird ein neues Sitzungs Options Objekt erstellt und im Wert der Variablen gespeichert `$pso` . Der zweite Befehl verwendet das `New-PSSession` Cmdlet, um eine Sitzung auf dem Remote Computer Server01 zu erstellen. Der Befehl verwendet das Sitzungs Options Objekt im Wert der `$pso` Variablen als Wert des **sessionoption** -Parameters des-Befehls.

### Beispiel 3: Starten einer interaktiven Sitzung

Dieser Befehl verwendet das `Enter-PSSession` Cmdlet, um eine interaktive Sitzung mit dem Server01-Computer zu starten.

```powershell
Enter-PSSession -ComputerName Server01 -SessionOption (New-PSSessionOption -NoEncryption -NoCompression)
```

Der Wert des **sessionoption** -Parameters ist ein `New-PSSessionOption` Befehl, der über die Parameter **NoEncryption** und **NoCompression** verfügt.

Der `New-PSSessionOption` Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er vor dem Befehl ausgeführt wird `Enter-PSSession` .

### Beispiel 4: Ändern eines Sitzungs Options Objekts

In diesem Beispiel wird veranschaulicht, dass Sie das Sitzungs Options Objekt ändern können. Alle Eigenschaften verfügen über Lese-/Schreibwerte.

```powershell
$a = New-PSSessionOption
$a.OpenTimeout
```

```Output
Days              : 0
Hours             : 0
Minutes           : 3
Seconds           : 0
Milliseconds      : 0
Ticks             : 1800000000
TotalDays         : 0.00208333333333333
TotalHours        : 0.05
TotalMinutes      : 3
TotalSeconds      : 180
TotalMilliseconds : 180000
```

```powershell
$a.UICulture = (Get-UICulture)
$a.OpenTimeout = (New-Timespan -Minutes 4)
$a.MaximumConnectionRedirectionCount = 1
$a
```

```Output
MaximumConnectionRedirectionCount : 1
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         : en-US
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:04:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

Verwenden Sie diese Methode, um ein Standardsitzungsobjekt für Ihr Unternehmen zu erstellen, und dann angepasste Versionen für bestimmte Verwendungszwecke anzulegen.

### Beispiel 5: Erstellen einer Einstellungs Variablen

Dieser Befehl erstellt eine Einstellungs `$PSSessionOption` Variable.

```powershell
$PSSessionOption = New-PSSessionOption -OpenTimeOut 120000
```

Wenn die Einstellungs `$PSSessionOption` Variable in der Sitzung auftritt, werden Standardwerte für Optionen in den Sitzungen festgelegt, die mit den `New-PSSession` `Enter-PSSession` Cmdlets, und erstellt werden `Invoke-Command` .

Um die `$PSSessionOption` Variable in allen Sitzungen verfügbar zu machen, fügen Sie Sie der PowerShell-Sitzung und Ihrem PowerShell-Profil hinzu.

Weitere Informationen zur Einstellungs `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).
Weitere Informationen zu Profilen finden Sie unter [about_Profiles](About/about_Profiles.md).

### Beispiel 6: erfüllen der Anforderungen an eine Remote Sitzungs Konfiguration

In diesem Beispiel wird gezeigt, wie ein **SessionOption** -Objekt verwendet wird, um die Anforderungen für eine Remotesitzungskonfiguration zu erfüllen.

```powershell
$skipCN = New-PSSessionOption -SkipCNCheck
New-PSSession -ComputerName 171.09.21.207 -UseSSL -Credential Domain01\User01 -SessionOption $SkipCN
```

Der erste Befehl verwendet das `New-PSSessionOption` Cmdlet, um ein Sitzungs Options Objekt zu erstellen, das über die **skipcncheck** -Eigenschaft verfügt. Der Befehl speichert das resultierende Sitzungs Objekt in der `$skipCN` Variablen.

Der zweite Befehl verwendet das `New-PSSession` Cmdlet, um eine neue Sitzung auf einem Remote Computer zu erstellen. Die `$skipCN` Check-Variable wird im Wert des **sessionoption** -Parameters verwendet.

Da der Computer anhand seiner IP-Adresse identifiziert wird, entspricht der Wert des Computer **Name** -Parameters keinem der allgemeinen Namen im Zertifikat, das für Secure Sockets Layer (SSL) verwendet wird. Demzufolge ist die **SkipCNCheck** -Option erforderlich.

### Beispiel 7: Bereitstellen von Argumenten für eine Remote Sitzung

In diesem Beispiel wird gezeigt, wie der **applicationarguments** -Parameter des `New-PSSessionOption` Cmdlets verwendet wird, um zusätzliche Daten für die Remote Sitzung verfügbar zu machen.

```powershell
$team = @{Team="IT"; Use="Testing"}
$TeamOption = New-PSSessionOption -ApplicationArguments $team
$s = New-PSSession -ComputerName Server01 -SessionOption $TeamOption
Invoke-Command -Session $s {$PSSenderInfo.ApplicationArguments}
```

```Output
Name                 Value
----                 -----
Team                 IT
Use                  Testing
PSVersionTable       {CLRVersion, BuildVersion, PSVersion, WSManStackVersion...}
```

```powershell
Invoke-Command -Session $s {
  if ($PSSenderInfo.ApplicationArguments.Use -ne "Testing") {
    .\logFiles.ps1
  }
  else {
    "Just testing."
  }
}
```

```Output
Just testing.
```

Der erste Befehl erstellt eine Hash Tabelle mit zwei Schlüsseln: " **Team** " und " **use** ". Der Befehl speichert die Hash Tabelle in der `$team` Variablen. Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](about/about_Hash_Tables.md) (Informationen zu Hashtabellen).

Im nächsten Schritt `New-PSSessionOption` erstellt das Cmdlet mit dem **applicationarguments** -Parameter ein Sitzungs Options Objekt, das in der Variablen gespeichert ist `$team` . Wenn `New-PSSessionOption` das Sitzungs Options Objekt erstellt, wird die Hash Tabelle im Wert des **applicationarguments** -Parameters automatisch in ein Primitives Wörterbuch konvertiert, damit die Daten zuverlässig an die Remote Sitzung übermittelt werden können.

Mit dem- `New-PSSession` Cmdlet wird eine Sitzung auf dem Server01-Computer gestartet. Er verwendet den **sessionoption** -Parameter, um die Optionen in der `$teamOption` Variablen einzubeziehen.

Das `Invoke-Command` Cmdlet zeigt, dass die Daten in der `$team` Variablen für Befehle in der Remote Sitzung verfügbar sind. Die Daten werden in der **applicationarguments** -Eigenschaft der `$PSSenderInfo` automatischen Variable angezeigt.

Die letzte `Invoke-Command` zeigt, wie die Daten verwendet werden können.

## PARAMETERS

### -Applicationarguments

Gibt ein primitives Wörterbuch an, das an die Remotesitzung gesendet wird. Durch Befehle und Skripts in der Remote Sitzung, einschließlich Start Skripts in der Sitzungs Konfiguration, kann dieses Wörterbuch in der **applicationarguments** -Eigenschaft der `$PSSenderInfo` automatischen Variablen gefunden werden. Sie können diesen Parameter verwenden, um Daten an die Remotesitzung zu senden.

Weitere Informationen finden Sie unter [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md)und [about_Automatic_Variables](about/about_Automatic_Variables.md).

```yaml
Type: System.Management.Automation.PSPrimitiveDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Canceltimeout

Bestimmt, wie lange PowerShell darauf wartet, dass ein Abbruch Vorgang (STRG + C) beendet wird, bevor Sie beendet wird.
Geben Sie einen Wert in Millisekunden ein.

Der Standardwert ist 60000 (eine Minute). Der Wert 0 (null) bedeutet, dass kein Timeout besteht; der Befehl wird auf unbestimmte Zeit fortgesetzt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: CancelTimeoutMSec

Required: False
Position: Named
Default value: 60000
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kultur

Gibt die Kultur an, die für die Sitzung verwendet werden soll. Geben Sie einen Kultur Namen im Format (z. b `<languagecode2>-<country/regioncode2>` `ja-JP` .), eine Variable mit einem **CultureInfo** -Objekt oder einen Befehl ein, der ein **CultureInfo** -Objekt abruft.

Der Standardwert ist `$Null` , und die im Betriebssystem festgelegte Kultur wird in der Sitzung verwendet.

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdleTimeout

Bestimmt, wie lange die Sitzung geöffnet bleibt, wenn der Remote Computer keine Kommunikation vom lokalen Computer empfängt. Dies schließt das Taktsignal ein. Wenn das Intervall abläuft, wird die Sitzung geschlossen.

Der Wert für das Leerlauf Timeout ist von großer Wichtigkeit, wenn Sie die Verbindung mit einer Sitzung trennen und wiederherstellen möchten. Sie können die Sitzung nur dann wiederherstellen, wenn kein Timeout aufgetreten ist.

Geben Sie einen Wert in Millisekunden ein. Der Mindestwert ist 60000 (1 Minute). Der Höchstwert ist der Wert der **MaxIdleTimeoutms** -Eigenschaft der Sitzungskonfiguration. Der Standardwert-1 legt kein Leerlauf Timeout fest.

Die Sitzung verwendet das Leerlauf Timeout, das in den Sitzungs Optionen festgelegt wird (sofern vorhanden). Wenn keine festgelegt ist (-1), verwendet die Sitzung den Wert der **idletimeoutms** -Eigenschaft der Sitzungs Konfiguration oder den Timeout Wert der WSMAN-Shell ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ), je nachdem, welcher Wert am kürzesten ist.

Überschreitet das Leerlaufzeitlimit in den Sitzungsoptionen den Wert der **MaxIdleTimeoutMs** -Eigenschaft der Sitzungskonfiguration, tritt bei dem Befehl zum Erstellen der Sitzung ein Fehler auf.

Der **idletimeoutms** -Wert der standardmäßigen **Microsoft. PowerShell** -Sitzungs Konfiguration beträgt 7,2 Millionen Millisekunden (2 Stunden). Der **maxidletimeoutms** -Wert beträgt 2147483647 Millisekunden ( \> 24 Tage). Der Standardwert des Leerlauf Timeouts () für WSMAN-Shell `WSMan:\<ComputerName>\Shell\IdleTimeout` beträgt 7,2 Millionen Millisekunden (2 Stunden).

Der Leerlauf Timeout Wert einer Sitzung kann auch geändert werden, wenn die Verbindung mit einer Sitzung getrennt oder eine Verbindung mit einer Sitzung wieder hergestellt wird. Weitere Informationen finden Sie unter `Disconnect-PSSession` und `Connect-PSSession`.

In Windows PowerShell 2.0 beträgt der Standardwert des **IdleTimeout** -Parameters 240000 (4 Minuten).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: IdleTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Includeportinspn

Schließt die Portnummer in den Dienst Prinzipal Namen (SPN) ein, die für die Kerberos-Authentifizierung verwendet wird, z `HTTP://<ComputerName>:5985` . b.. Mit dieser Option kann ein Client, der einen nicht standardmäßigen SPN verwendet, von einem Remotecomputer authentifiziert werden, der die Kerberos-Authentifizierung verwendet.

Diese Option wurde für Organisationen entwickelt, in denen mehrere Dienste, die die Kerberos-Authentifizierung unterstützen, unter verschiedenen Benutzerkonten ausgeführt werden. Beispielsweise kann eine IIS-Anwendung, die die Kerberos-Authentifizierung zulässt, erfordern, dass der Standard-SPN für ein Benutzerkonto registriert ist, das sich von dem Computer Konto unterscheidet. In solchen Fällen kann das PowerShell-Remoting Kerberos nicht für die Authentifizierung verwenden, da es einen SPN erfordert, der für das Computer Konto registriert ist. Um dieses Problem zu beheben, können Administratoren unterschiedliche SPNs erstellen, z. b. mit **Setspn.exe** , die für unterschiedliche Benutzerkonten registriert sind, und Sie können unterscheiden, indem Sie die Portnummer in den SPN einschließen.

Weitere Informationen finden Sie unter [Übersicht über Setspn](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### -Maxconnectionretrycount

Gibt an, wie oft von PowerShell versucht wird, eine Verbindung mit einem Zielcomputer herzustellen, wenn der aktuelle Versuch aufgrund von Netzwerkproblemen fehlschlägt. Der Standardwert ist 5.

Dieser Parameter wurde für PowerShell-Version 5,0 hinzugefügt.

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

### -Maximumreceiveddatasizepercommand

Gibt die maximale Anzahl von Bytes an, die der lokale Computer von dem Remotecomputer in einem einzigen Befehl empfangen kann. Geben Sie einen Wert in Bytes ein. Standardmäßig besteht keine Größenbeschränkung für Daten.

Diese Option dient zum Schutz der Ressourcen auf dem Clientcomputer.

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

### -Maximumreceivedobjectsize

Gibt die maximale Größe eines Objekts an, das der lokale Computer vom Remotecomputer empfangen kann. Diese Option dient zum Schutz der Ressourcen auf dem Clientcomputer. Geben Sie einen Wert in Bytes ein.

In Windows PowerShell 2.0 besteht, wenn Sie diesen Parameter weglassen, keine Größenbeschränkung für Objekte. Ab Windows PowerShell 3.0 beträgt, wenn Sie diesen Parameter weglassen, der Standardwert 200 MB.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 200 MB
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maximumredirect

Bestimmt, wie oft PowerShell eine Verbindung an eine Alternative Uniform Resource Identifier (URI) umleitet, bevor die Verbindung fehlschlägt. Der Standardwert ist 5. Der Wert 0 (null) unterbindet sämtliche Umleitungen.

Diese Option wird in der Sitzung nur verwendet, wenn der Parameter " **Zuweisung** " in dem Befehl verwendet wird, der die Sitzung erstellt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoCompression

Deaktiviert die Paketkomprimierung in der Sitzung. Die Komprimierung verwendet mehr Prozessorzyklen, beschleunigt aber die Übertragung.

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

### -NoEncryption

Deaktiviert die Datenverschlüsselung.

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

### -Nomachineprofile

Verhindert das Laden des Windows-Benutzerprofils. Daraufhin wird die Sitzung möglicherweise schneller erstellt, aber benutzerspezifische Registrierungseinstellungen wie Umgebungsvariablen und Zertifikate sind in der Sitzung nicht verfügbar.

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

### -OpenTimeout

Bestimmt, wie lange der Clientcomputer auf das Einrichten der Sitzungsverbindung wartet. Wenn das Intervall abläuft, tritt bei dem Befehl zum Herstellen der Verbindung ein Fehler auf. Geben Sie einen Wert in Millisekunden ein.

Der Standardwert ist 180000 (3 Minuten). Der Wert 0 (null) bedeutet, dass kein Timeout besteht; der Befehl wird auf unbestimmte Zeit fortgesetzt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OpenTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationTimeout

Bestimmt die maximale Zeit, die ein Vorgang in der Sitzung ausgeführt werden kann. Wenn das Intervall abläuft, schlägt der Vorgang fehl. Geben Sie einen Wert in Millisekunden ein.

Der Standardwert ist 180000 (3 Minuten). Der Wert 0 (null) bedeutet, dass kein Timeout besteht; der Vorgang wird auf unbestimmte Zeit fortgesetzt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Outputbufferingmode

Bestimmt, wie die Befehlsausgabe in getrennten Sitzungen verwaltet wird, wenn sich der Ausgabepuffer füllt.

Wenn der Modus für die Ausgabepufferung in der Sitzung oder der Sitzungskonfiguration nicht festgelegt ist, ist der Standardwert **Block** . Benutzer können den Modus für die Ausgabepufferung auch beim Trennen der Sitzung ändern.

Wenn Sie diesen Parameter weglassen, ist der Wert von **outputbufferingmode** des Sitzungs Options Objekts "None". Ein Wert von **Block** oder **Drop** überschreibt die Transportoption des Modus für die Ausgabepufferung, die in der Sitzungskonfiguration festgelegt wurde. Zulässige Werte für diesen Parameter:

- Blockierung. Wenn der Ausgabepuffer voll ist, wird die Ausführung unterbrochen, bis der Puffer leer ist.
- Ablage. Wenn der Ausgabepuffer voll ist, wird die Ausführung fortgesetzt. Sobald neue Ausgabedaten gespeichert werden, wird die älteste Ausgabe verworfen.
- Keine Es wurde kein Ausgabepufferungsmodus angegeben.

Weitere Informationen zur Transport Option "Output bufferingmode" finden Sie unter `New-PSTransportOption` .

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxyaccesstype

Bestimmt, welcher Mechanismus verwendet wird, um den Hostnamen aufzulösen. Zulässige Werte für diesen Parameter:

- Ieconfig
- Winhttpconfig
- Auto Ermittlung
- Noproxyserver
- Keine

Der Standardwert lautet „Keine“.

Informationen zu den Werten dieses Parameters finden Sie unter [proxyaccesstype-Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype?redirectedfrom=MSDN&view=powershellsdk-1.1.0).

```yaml
Type: System.Management.Automation.Remoting.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: None, IEConfig, WinHttpConfig, AutoDetect, NoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy Authentifizierung

Gibt die Authentifizierungsmethode an, die für die Proxyauflösung verwendet wird. Die zulässigen Werte für diesen Parameter sind: **Basic** , **Digest** und **Aushandlungs** . Der Standardwert ist " **aushandeln** ".

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?redirectedfrom=MSDN&view=powershellsdk-1.1.0).

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Proxy Credential

Gibt die Anmeldeinformationen an, die für die Proxyauthentifizierung verwendet werden sollen. Geben Sie eine Variable ein, die ein **PSCredential** -Objekt enthält, oder einen Befehl, der ein **PSCredential** -Objekt abruft, z `Get-Credential` . b. einen Befehl. Wenn diese Option nicht festgelegt ist, werden keine Anmeldeinformationen angegeben.

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

### -Skipcacheck

Gibt an, dass der Client beim Herstellen einer Verbindung über HTTPS nicht überprüft, ob das Serverzertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certification Authority, ca) signiert wurde.

Verwenden Sie diese Option nur, wenn der Remotecomputer vertrauenswürdig ist, weil er einen anderen Mechanismus verwendet, z. B. wenn er Teil eines physisch sicheren und isolierten Netzwerks ist oder wenn der Remotecomputer in einer WinRM-Konfiguration als vertrauenswürdiger Host aufgeführt ist.

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

### -SkipCNCheck

Gibt an, dass der allgemeine Name des Zertifikats (Common Name, CN) des Servers nicht mit dem Hostnamen des Servers identisch sein muss. Diese Option wird nur bei Remotevorgängen verwendet, die das HTTPS-Protokoll verwenden.

Verwenden Sie diese Option nur für vertrauenswürdige Computer.

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

### -Skiprevocationcheck

Der Sperrstatus des Serverzertifikats wird nicht überprüft.

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

### -UICulture

Gibt die Kultur der Benutzeroberfläche an, die für die Sitzung verwendet werden soll.

Gültige Werte:

- Ein Kultur Name im- `<languagecode2>-<country/regioncode2>` Format, z. b. `ja-JP`
- Eine Variable, die ein **CultureInfo** -Objekt enthält.
- Ein Befehl, der ein **CultureInfo** -Objekt abruft, z. b. `Get-Culture`

Der Standardwert ist `$null` , und die Benutzeroberflächen Kultur, die beim Erstellen der Sitzung im Betriebssystem festgelegt wird, wird in der Sitzung verwendet.

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseUTF16

Gibt an, dass dieses Cmdlet die Anforderung im UTF16-Format anstatt im UTF8-Format codiert.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### System. Management. Automation. Remoting. pssessionoption

## HINWEISE

Wenn der **sessionoption** -Parameter in einem Befehl zum Erstellen einer **PSSession** nicht verwendet wird, werden die Sitzungs Optionen durch die Eigenschaftswerte der Einstellungs `$PSSessionOption` Variablen bestimmt, sofern festgelegt. Weitere Informationen zur- `$PSSessionOption` Variablen finden Sie unter [about_Preference_Variables](About/about_Preference_Variables.md).

Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab. Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.

## VERWANDTE LINKS

[Enter-PSSession](Enter-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)
