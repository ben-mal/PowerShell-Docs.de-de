---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: a8d3923db69a20cfada58391944b592cf999e6ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214335"
---
# Test-Connection

## ZUSAMMENFASSUNG
Sendet ICMP-Echo Anforderungs Pakete (Pings) an einen oder mehrere Computer.

## SYNTAX

### Standard (Standard)

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### `Source`

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### Quiet

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## DESCRIPTION

Das `Test-Connection` -Cmdlet sendet ICMP (Internet Control Message Protocol)-Echo Anforderungs Pakete (Pings) an einen oder mehrere Remote Computer und gibt die Echo Antwort Antworten zurück. Mit diesem Cmdlet können Sie ermitteln, ob ein bestimmter Computer über ein IP-Netzwerk kontaktiert werden kann.

Sie können mit den Parametern von `Test-Connection` sowohl den sendenden als auch den empfangenden Computer angeben, den Befehl als Hintergrund Auftrag ausführen, ein Timeout und eine Anzahl von Pings festlegen und die Verbindung und die Authentifizierung konfigurieren.

Im Gegensatz zum vertrauten **Ping** -Befehl `Test-Connection` gibt ein **Win32_PingStatus** Objekt zurück, das Sie in PowerShell untersuchen können. Der **quiet** -Parameter gibt für jede getestete Verbindung einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück. Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.

## BEISPIELE

### Beispiel 1: Senden von ECHO Anforderungen an einen Remote Computer

In diesem Beispiel werden Echo Request-Pakete vom lokalen Computer an den Server01-Computer gesendet.

```powershell
Test-Connection -ComputerName Server01
```

```Output
Source        Destination     IPV4Address     IPV6Address  Bytes    Time(ms)
------        -----------     -----------     -----------  -----    --------
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       1
```

`Test-Connection` verwendet den Computer **Name** -Parameter, um den Server01-Computer anzugeben.

### Beispiel 2: Senden von ECHO Anforderungen an mehrere Computer

In diesem Beispiel werden Pings vom lokalen Computer an mehrere Remote Computer gesendet.

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### Beispiel 3: Senden von ECHO Anforderungen von mehreren Computern an einen Computer

In diesem Beispiel werden Pings von unterschiedlichen Quell Computern an einen einzelnen Remote Computer, SERVER01, gesendet.

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

`Test-Connection` verwendet den **Credential** -Parameter, um die Anmelde Informationen eines Benutzers anzugeben, der über die Berechtigung zum Senden einer Ping-Anforderung von den Quell Computern verfügt. Verwenden Sie diesen Befehl, um die Wartezeit von Verbindungen von mehreren Punkten aus zu überprüfen.

### Beispiel 4: Verwenden von Parametern zum Anpassen des Test Befehls

In diesem Beispiel werden die Parameter von verwendet `Test-Connection` , um den Befehl anzupassen. Der lokale Computer sendet einen Pingtest an einen Remote Computer.

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

`Test-Connection` verwendet den **Computername** -Parameter, um Server01 anzugeben. Der **count** -Parameter gibt an, dass drei Pings mit einer **Verzögerung** von 2-Sekunden-Intervallen an den Server01-Computer gesendet werden.

Sie können diese Optionen verwenden, wenn die Ping-Antwort erwartungsgemäß länger als üblich dauert, entweder aufgrund einer erweiterten Hopanzahl oder einer Netzwerk Bedingung mit hohem Datenverkehr.

### Beispiel 5: Ausführen eines Tests als Hintergrund Auftrag

Dieses Beispiel zeigt, wie Sie einen `Test-Connection` Befehl als PowerShell-Hintergrund Auftrag ausführen.

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

Der `Test-Connection` Befehl pingt viele Computer in einem Unternehmen. Der Wert des **Computername** -Parameters ist ein `Get-Content` Befehl, der eine Liste mit Computernamen aus der liest `Servers.txt file` . Der Befehl verwendet den **AsJob** -Parameter, um den Befehl als Hintergrund Auftrag auszuführen, und speichert den Auftrag in der `$job` Variablen.

`if`Mit dem Befehl wird überprüft, ob der Auftrag noch nicht ausgeführt wird. Wenn der Auftrag nicht ausgeführt wird, werden `Receive-Job` die Ergebnisse abgerufen und in der `$Results` Variablen gespeichert.

### Beispiel 6: Pingen eines Remote Computers mit Anmelde Informationen

Dieser Befehl verwendet das `Test-Connection` Cmdlet, um einen Remote Computer zu pingen.

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

Der Befehl verwendet den **Credential** -Parameter, um ein Benutzerkonto anzugeben, das über die Berechtigung zum Pingen des Remote Computers und den Identitäts **Wechsel Parameter zum** Ändern der Identitätswechsel Ebene zur **Identifizierung** verfügt.

### Beispiel 7: Erstellen einer Sitzung nur dann, wenn ein Verbindungstest erfolgreich ist

In diesem Beispiel wird nur dann eine Sitzung auf dem Computer Server01 erstellt, wenn mindestens eines der an den Computer gesendeten Pings erfolgreich ist.

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

Der `if` Befehl verwendet das `Test-Connection` Cmdlet, um den Server01-Computer zu pingen. Der Befehl verwendet den **quiet** -Parameter, der anstelle eines **Win32_PingStatus** Objekts einen **booleschen** Wert zurückgibt. Der Wert ist `$True` , wenn eine der vier Pings erfolgreich ist und ist, andernfalls `$False` .

Wenn der `Test-Connection` Befehl den Wert zurückgibt `$True` , verwendet der Befehl das `New-PSSession` Cmdlet, um die **PSSession** zu erstellen.

## PARAMETERS

### -AsJob

Gibt an, dass dieses Cmdlet als Hintergrund Auftrag ausgeführt wird.

Um diesen Parameter verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein. unter Windows Vista und höheren Versionen des Windows-Betriebssystems müssen Sie PowerShell mit der Option **als Administrator ausführen** öffnen. Weitere Informationen finden Sie unter [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).

Wenn Sie den **AsJob** -Parameter angeben, gibt der Befehl sofort ein Objekt zurück, das den Hintergrund Auftrag darstellt. Sie können die Sitzung weiterhin verwenden, während der Auftrag abgeschlossen wird. Der Auftrag wird auf dem lokalen Computer erstellt, und die Ergebnisse von Remotecomputern werden automatisch an den lokalen Computer zurückgegeben. Um die Auftragsergebnisse abzurufen, verwenden Sie das Cmdlet `Receive-Job`.

Weitere Informationen zu PowerShell-Hintergrund Aufträgen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) und [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -BufferSize

Gibt die Größe des mit diesem Befehl gesendeten Puffers in Bytes an. Der Standardwert ist 32.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt die zu pingenden Computer an. Geben Sie die Computernamen oder IP-Adressen im IPv4- oder IPv6-Format ein. Platzhalterzeichen sind nicht zulässig. Dieser Parameter ist erforderlich.

Dieser Parameter beruht nicht auf PowerShell-Remoting. Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

> [!NOTE]
> Der **Computername** -Parameter wird in PowerShell 6,0 und höher in " **TargetName** " umbenannt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, IPAddress, __SERVER, Server, Destination

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Anzahl

Gibt die Anzahl der zu sendenden Echoanforderungen an. Der Standardwert ist 4.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Senden einer Ping-Anforderung vom Quellcomputer verfügt. Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. einen aus dem `Get-Credential` Cmdlet.

Der **Credential** -Parameter ist nur gültig, wenn der **Source** -Parameter im Befehl verwendet wird. Die Anmelde Informationen wirken sich nicht auf den Zielcomputer aus.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Source
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Dcomauthentication

Gibt die Authentifizierungs Ebene an, die dieses Cmdlet mit WMI verwendet.
`Test-Connection` verwendet WMI.
Zulässige Werte für diesen Parameter:

- **Default** . Windows-Authentifizierung
- **Keine** . Keine COM-Authentifizierung
- **Verbinden** Sie sich. COM-Authentifizierung auf Verbindungsebene
- **Aufgerufen** wird. COM-Authentifizierung auf Aufrufebene
- **Paket** . COM-Authentifizierung auf Paketebene
- **Packetintegrity** . COM-Authentifizierung auf Paketintegritätsebene.
- **PacketPrivacy** . COM-Authentifizierung auf Paketdaten Schutz Ebene
- **Unverändert** . Identisch mit dem vorherigen Befehl

Der Standardwert ist **Packet** , das den Enumerationswert **4** aufweist. Weitere Informationen zu den Werten dieses Parameters finden Sie unter [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) -Enumeration.

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet (enumerated value of 4)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verzögerung

Gibt das Intervall zwischen Pings in Sekunden an.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1 (second)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identitätswechsel

Gibt die Identitätswechsel Ebene an, die verwendet werden soll, wenn dieses Cmdlet WMI aufruft. `Test-Connection` verwendet WMI.

Die zulässigen Werte für diesen Parameter lauten wie folgt:

- **Default** . Standardidentitätswechsel.
- **Anonym** . Blendet die Identität des Aufrufers aus
- **Identifizieren** Sie. Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers abzufragen.
- Identität **annehmen.** Ermöglicht es Objekten, die Anmeldeinformationen des Aufrufers zu verwenden.

Der Standard **Wert ist "** Identitätswechsel".

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Gibt ein Protokoll an. Die zulässigen Werte für diesen Parameter sind "DCOM" und "wsman".

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quiet

Der **quiet** -Parameter gibt einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück. Durch die Verwendung dieses Parameters werden alle Fehler unterdrückt.

Jede getestete Verbindung gibt einen **booleschen** Wert zurück. Wenn der **Computername** -Parameter mehrere Computer angibt, wird ein Array von **booleschen** Werten zurückgegeben.

Wenn **ein** Ping erfolgreich ist, `$True` wird zurückgegeben.

Wenn **alle** Pings fehlschlagen, `$False` wird zurückgegeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Quiet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Gibt die Namen der Computer an, von denen der Ping stammt. Geben Sie eine durch Trennzeichen getrennte Liste von Computernamen ein. Die Standardeinstellung ist der lokale Computer.

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: FCN, SRC

Required: True
Position: 1
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Gibt die maximale Anzahl von gleichzeitigen Verbindungen an, die zum Ausführen dieses Befehls hergestellt werden können.
Wenn Sie diesen Parameter weglassen oder den Wert %%amp;quot;0%%amp;quot; eingeben, wird der Standardwert %%amp;quot;32%%amp;quot; verwendet.

Die Drosselungsgrenze gilt nur für den aktuellen Befehl und nicht für die Sitzung oder den Computer.

```yaml
Type: System.Int32
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeto Live

Gibt an, wie oft ein Paket maximal weitergeleitet werden kann. Bei jedem Hop in Gateways, Routern usw. wird der Wert von " **Timeto Live** " um 1 reduziert. Bei Null wird das Paket verworfen, und es wird ein Fehler zurückgegeben.
In **Windows** ist der Standardwert **128** . Der Alias des **timetelive** -Parameters ist **TTL** .

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: 128 in Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wsmanauthentication

Gibt den Mechanismus an, der verwendet wird, um die Benutzer Anmelde Informationen zu authentifizieren, wenn dieses Cmdlet das WSMAN-Protokoll verwendet.
Zulässige Werte für diesen Parameter:

- Basic
- CredSSP
- Standard
- Digest
- Kerberos
- Negotiate

Der Standardwert ist Default.

Weitere Informationen zu den Werten dieses Parameters finden Sie unter [authenticationmechanism-Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).

Vorsicht: die Authentifizierung des Anmelde Informations Diensts (Credential Security Service Provider, kredssp), in der die Benutzer Anmelde Informationen an einen Remote Computer übergeben werden, der authentifiziert werden soll, wurde für Befehle entworfen, die eine Authentifizierung auf mehr als einer Ressource erfordern, z. b. auf eine Remote Netzwerkfreigabe
Dieser Mechanismus erhöht das Sicherheitsrisiko des Remotevorgangs.
Wenn die Sicherheit des Remotecomputers gefährdet ist, können die an ihn übergebenen Anmeldeinformationen zum Steuern der Netzwerksitzung verwendet werden.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet übergeben werden.

## AUSGABEN

### System. Management. ManagementObject # root\cimv2\ Win32_PingStatus, System. Management. Automation. remotingjob, System. Boolean

Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den **AsJob** -Parameter angeben.

Wenn Sie den **quiet** -Parameter angeben, wird ein **boolescher** Wert zurückgegeben. Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben. Andernfalls wird `Test-Connection` für jeden Ping ein **Win32_PingStatus** -Objekt zurückgegeben.

## HINWEISE

Dieses Cmdlet verwendet die **Win32_PingStatus** -Klasse. Ein `Get-WMIObject Win32_PingStatus` Befehl entspricht einem `Test-Connection` Befehl.

Der **Quell** Parametersatz wurde in PowerShell 3,0 eingeführt.

## VERWANDTE LINKS

[Add-Computer](Add-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
