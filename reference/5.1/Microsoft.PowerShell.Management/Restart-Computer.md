---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 553b61c9669afab325e9feec101d701c2b9a7c83
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218263"
---
# Restart-Computer

## ZUSAMMENFASSUNG
Startet das Betriebssystem auf lokalen Computern und Remote Computern neu.

## SYNTAX

### Defaultset (Standard)

```
Restart-Computer [-DcomAuthentication <AuthenticationLevel>] [-Impersonation <ImpersonationLevel>]
 [-WsmanAuthentication <String>] [-Protocol <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Asjobset

```
Restart-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>]
 [-Impersonation <ImpersonationLevel>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Force] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Restart-Computer`Mit dem-Cmdlet wird das Betriebssystem auf dem lokalen Computer und auf dem Remote Computer neu gestartet.

Mit den Parametern von können Sie `Restart-Computer` die Neustart Vorgänge als Hintergrund Auftrag ausführen, die Authentifizierungs Ebenen und Alternative Anmelde Informationen angeben, die Vorgänge, die gleichzeitig ausgeführt werden, einschränken und einen sofortigen Neustart erzwingen.

Ab Windows PowerShell 3,0 können Sie warten, bis der Neustart beendet ist, bevor Sie den nächsten Befehl ausführen. Geben Sie ein Wartezeit-und Abfrageintervall an, und warten Sie, bis bestimmte Dienste auf dem neu gestarteten Computer verfügbar sind. Diese Funktion erleichtert die Verwendung von `Restart-Computer` in Skripts und Funktionen.

Sie können das WSMAN-Protokoll (WS-Management) verwenden, um den Computer neu zu starten, falls DCOM-Aufrufe (verteiltes Component Object Model) blockiert werden (z. b. durch eine Unternehmens Firewall). Weitere Informationen finden Sie unter [WS-Management-Protokoll](/windows/desktop/WinRM/ws-management-protocol).

Bei diesem Cmdlet ist Windows PowerShell-Remoting nur erforderlich, wenn Sie den **AsJob** -Parameter in einem Befehl verwenden.

## BEISPIELE

### Beispiel 1: Neustarten des lokalen Computers

`Restart-Computer` startet den lokalen Computer neu.

```powershell
Restart-Computer
```

### Beispiel 2: Neustarten mehrerer Computer

`Restart-Computer` Remote Computer und lokale Computer können neu gestartet werden. Der Computer **Name** -Parameter akzeptiert ein Array von Computernamen.

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### Beispiel 3: Neustarten von Computern als Hintergrund Auftrag

Diese Befehle führen einen `Restart-Computer` Befehl als Hintergrund Auftrag auf zwei Remote Computern aus und erhalten dann die Ergebnisse.

Da **AsJob** den Auftrag auf dem lokalen Computer erstellt und die Ergebnisse automatisch an den lokalen Computer zurückgibt, können Sie ihn `Receive-Job` als lokalen Befehl ausführen.

```powershell
$Job = Restart-Computer -ComputerName "Server01", "Server02" -AsJob
$Job | Receive-Job
```

`Restart-Computer` verwendet den **Computername** -Parameter zum Angeben von **Server01** und **Server02**. Der **AsJob** -Parameter führt den Befehl als Hintergrund Auftrag aus. Das Auftrags Objekt wird in der `$Job` Variablen gespeichert. `$Job` wird über die Pipeline an das `Receive-Job` Cmdlet gesendet, das die Ergebnisse abruft.

### Beispiel 4: Neustart eines Remote Computers

`Restart-Computer` startet einen Remote Computer mit angepassten Identitätswechsel-und Authentifizierungs Einstellungen neu.

```powershell
Restart-Computer -ComputerName Server01 -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

`Restart-Computer` verwendet den **Computername** -Parameter, um **Server01** anzugeben. Der Identitäts **Wechsel Parameter gibt** anonym an, um die Identität des Anforderers auszublenden. Der **dcomauthentication** -Parameter gibt packetintegrity als Authentifizierungs Ebene der Verbindung an.

### Beispiel 5: Erzwingen des Neustarts von Computern, die in einer Textdatei aufgeführt sind

Dieses Beispiel erzwingt einen sofortigen Neustart der Computer, die in der-Datei aufgeführt sind `Domain01.txt` . Die Computernamen aus der Textdatei werden in einer Variablen gespeichert. Der **Force** -Parameter erzwingt einen sofortigen Neustart, und der **throttlelimit** -Parameter schränkt die Anzahl gleichzeitiger Verbindungen ein.

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force -ThrottleLimit 10
```

`Get-Content` verwendet den **path** -Parameter, um eine Liste der Computernamen aus einer Textdatei, **Domain01.txt** , zu erhalten. Die Computernamen werden in der Variablen gespeichert `$Names` . `Get-Credential` fordert Sie zur Eingabe eines Benutzernamens und Kennworts auf und speichert die Werte in der Variablen `$Creds` . `Restart-Computer` verwendet die Parameter " **Computername** " und " **Credential** " mit ihren Variablen. Der **Force** -Parameter bewirkt einen sofortigen Neustart der einzelnen Computer. Der **throttlelimit** -Parameter schränkt den Befehl auf 10 gleichzeitige Verbindungen ein.

### Beispiel 6: Neustarten eines Remote Computers und warten auf PowerShell

`Restart-Computer` startet den Remote Computer neu und wartet dann bis zu 5 Minuten (300 Sekunden) darauf, dass PowerShell auf dem neu gestarteten Computer verfügbar wird, bevor es fortgesetzt wird.

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

`Restart-Computer` verwendet den **Computername** -Parameter, um **Server01** anzugeben. Der **Wait** -Parameter wartet, bis der Neustart abgeschlossen ist. Der **für** gibt an, dass PowerShell Befehle auf dem Remote Computer ausführen kann. Der **Timeout** -Parameter gibt eine Wartezeit von fünf Minuten an. Der **Verzögerungs** Parameter fragt den Remote Computer alle zwei Sekunden ab, um zu bestimmen, ob er neu gestartet wird.

### Beispiel 7: Neustarten eines Computers mithilfe des WSMAN-Protokolls

`Restart-Computer` der Remote Computer wird mit dem WSMAN-Protokoll anstelle der standardmäßigen DCOM neu gestartet. Die Kerberos-Authentifizierung bestimmt, ob der aktuelle Benutzer über die Berechtigung zum Neustarten des Remote Computers verfügt.

Diese Einstellungen sind für Unternehmen konzipiert, in denen DCOM-basierte Neustarts fehlschlagen, da DCOM blockiert ist. Beispielsweise durch eine Firewall.

```powershell
Restart-Computer -ComputerName Server01 -Protocol WSMan -WsmanAuthentication Kerberos
```

`Restart-Computer` verwendet den **Computername** -Parameter, um den Remote Computer anzugeben, **Server01**.
Der **Protokoll** Parameter gibt an, dass das WSMAN-Protokoll verwendet werden soll. Der **wsmanauthentication** -Parameter gibt die Authentifizierungsmethode als **Kerberos** an.

## PARAMETERS

### -AsJob

Gibt an, dass `Restart-Computer` als Hintergrund Auftrag ausgeführt wird.

Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. Unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell öffnen, indem Sie die Option **als Administrator ausführen** verwenden. Weitere Informationen finden Sie unter [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

Wenn Sie den **AsJob** -Parameter angeben, gibt der Befehl sofort ein Objekt zurück, das den Hintergrund Auftrag darstellt. Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird. Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben. Verwenden Sie die **Job** -Cmdlets, um den Auftrag zu verwalten. Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.

Weitere Informationen zu Windows PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt einen Computernamen oder ein durch Trennzeichen getrenntes Array von Computernamen an. `Restart-Computer` nimmt **Computername** -Objekte aus der Pipeline oder den Variablen an.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen eines Remotecomputers ein. Geben Sie den Computernamen, einen Punkt oder einen localhost ein, um den lokalen Computer anzugeben `.` .

Dieser Parameter beruht nicht auf PowerShell-Remoting. Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

Wenn der **Computername** -Parameter nicht angegeben ist, wird `Restart-Computer` der lokale Computer neu gestartet.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -Dcomauthentication

Gibt die Authentifizierungs Ebene an, die für die WMI-Verbindung verwendet wird. `Restart-Computer` verwendet WMI.

Gültige Werte sind:

- **Rückruf** : com-Authentifizierung auf aufrufsebene
- **Connect** : com-Authentifizierung auf Verbindungs Ebene
- **Standard** : Windows-Authentifizierung
- **None** : keine com-Authentifizierung
- **Paket** : com-Authentifizierung auf Paketebene.
- **Packetintegrity** : com-Authentifizierung auf Paket Integritäts Ebene
- **PacketPrivacy** : com-Authentifizierung auf Paketdaten Schutz Ebene.
- **Unverändert** : die Authentifizierungs Ebene entspricht dem vorherigen Befehl.

Weitere Informationen finden Sie unter [AuthenticationLevel-Enumeration](/dotnet/api/system.management.authenticationlevel).

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verzögerung

Gibt die Häufigkeit von Abfragen in Sekunden an. PowerShell fragt den durch den **for** -Parameter angegebenen Dienst ab, um zu bestimmen, ob der Dienst nach dem Neustart des Computers verfügbar ist.

Dieser Parameter ist nur in Verbindung mit den **Wait** -und **for** -Parametern gültig.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

Wenn der **Delay** -Parameter nicht angegeben wird, `Restart-Computer` verwendet eine Verzögerung von fünf Sekunden.

```yaml
Type: System.Int16
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Für

Gibt das Verhalten von PowerShell an, da es darauf wartet, dass der angegebene Dienst oder das Feature nach dem Neustart des Computers verfügbar wird. Dieser Parameter ist nur mit dem **Wait** -Parameter gültig.

Zulässige Werte für diesen Parameter:

- **Standard** : wartet darauf, dass PowerShell neu gestartet wird.
- **PowerShell** : kann Befehle in einer PowerShell-Remote Sitzung auf dem Computer ausführen.
- **WMI** : empfängt eine Antwort auf eine Win32_ComputerSystem Abfrage für den Computer.
- **WinRM** : kann mithilfe von WS-Management eine Remote Sitzung mit dem Computer herstellen.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: DefaultSet
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Erzwingt einen sofortigen Neustart des Computers.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identitätswechsel

Gibt die Identitätswechsel Ebene an, die dieses Cmdlet zum Abrufen von WMI verwendet. `Restart-Computer` verwendet WMI.
Zulässige Werte für diesen Parameter:

- **Standard** : Standard Identitätswechsel. Trotz des Namens ist dies nicht der Standardwert.
- **Anonymous** : Blendet die Identität des Aufrufers aus.
- **Identifizieren** : ermöglicht es Objekten, die Anmelde Informationen des Aufrufers abzufragen.
- Identität **annehmen: ermöglicht** es Objekten, die Anmelde Informationen des Aufrufers zu verwenden.

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Gibt an, welches Protokoll zum Neustarten der Computer verwendet werden soll. Gültige Werte sind **WSMAN** und **DCOM**.

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.
Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

Wenn der **throttlelimit** -Parameter nicht angegeben oder der Wert 0 verwendet wird, `Restart-Computer` verwendet maximal 32 gleichzeitige Verbindungen.

```yaml
Type: System.Int32
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout

Gibt die Dauer des Wartevorgangs in Sekunden an. Wenn das Timeout abläuft, `Restart-Computer` kehrt zur Eingabeaufforderung zurück, auch wenn die Computer nicht neu gestartet werden.

Der **Timeout** -Parameter ist nur mit dem **Wait** -Parameter gültig. **Timeout** überschreibt den unbegrenzten warte Zeitraum des **Wait** -Parameters.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: DefaultSet
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

`Restart-Computer` unterdrückt die PowerShell-Eingabeaufforderung und blockiert die Pipeline, bis die Computer neu gestartet wurden. Sie können diesen Parameter in einem Skript verwenden, um Computer neu zu starten und die Verarbeitung anschließend fortzusetzen, wenn der Neustart abgeschlossen ist.

Der **Wait** -Parameter wartet unbegrenzt, bis der Computer neu gestartet wird. Mit **Timeout** können Sie die zeitliche Steuerung und die Parameter **für** und **Verzögerung** anpassen, um zu warten, bis bestimmte Dienste auf den neu gestarteten Computern verfügbar sind.

Der **Wait** -Parameter ist nicht gültig, wenn Sie den lokalen Computer neu starten. Wenn der Wert des **Computername** -Parameters die Namen der Remote Computer und des lokalen Computers enthält, `Restart-Computer` generiert einen Fehler ohne Abbruch auf dem lokalen Computer, wartet **jedoch auf** den Neustart der Remote Computer.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wsmanauthentication

Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren. Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

Die zulässigen Werte für diesen Parameter sind: **Basic** , **kredssp** , **default** , **Digest** , **Kerberos** und **Aushandlungs**.

Weitere Informationen finden Sie unter [authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!WARNING]
> Die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehreren Ressourcen erfordern Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs. Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Restart-Computer` .

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

Zeigt, was geschieht, wenn die ausgeführt wird `Restart-Computer` . Das- `Restart-Computer` Cmdlet wird nicht ausgeführt.

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

### System.String

`Restart-Computer` nimmt Computernamen aus der Pipeline oder den Variablen an.

In Windows PowerShell 2.0 nimmt der **ComputerName** -Parameter Eingaben über die Pipeline nur nach Eigenschaftenname an. In Windows PowerShell 3,0 und höher nimmt der **Computername** -Parameter Eingaben aus der Pipeline nach Wert.

## AUSGABEN

### Keine, System. Management. Automation. remotingjob

Wenn Sie den **AsJob** -Parameter angeben, wird `Restart-Computer` ein Auftrags Objekt zurückgegeben. Andernfalls wird keine Ausgabe generiert.

## HINWEISE

- `Restart-Computer` nur auf Computern, auf denen Windows ausgeführt wird, ist es erforderlich, dass WinRM und WMI ein System Herunterfahren, einschließlich des lokalen Systems.
- `Restart-Computer` verwendet die [Win32Shutdown-Methode](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) der WMI- [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) Klasse (Windows-Verwaltungsinstrumentation).  Diese Methode erfordert, dass die **SeShutdownPrivilege** -Berechtigung für das Benutzerkonto aktiviert ist, mit dem der Computer neu gestartet wird.

In Windows PowerShell 2,0 funktioniert der **AsJob** -Parameter nicht zuverlässig, wenn Sie Remote Computer neu starten oder beenden. In Windows PowerShell 3.0 wurde die Implementierung geändert, um dieses Problem zu beheben.

## VERWANDTE LINKS

[Informationen zu Windows-Remoteverwaltung](/windows/desktop/WinRM/about-windows-remote-management)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[WS-Verwaltungsprotokoll](/windows/desktop/WinRM/ws-management-protocol)
