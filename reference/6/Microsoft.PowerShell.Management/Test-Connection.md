---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 54ba1d7db60db7b4bb64f3161bba9c1fba124219
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212196"
---
# Test-Connection

## ZUSAMMENFASSUNG
Sendet ICMP-Echo Anforderungs Pakete (Pings) an einen oder mehrere Computer.

## SYNTAX

### Pingcount (Standard)

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### Pingfort setzt

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### Detectionofmtusize

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### TraceRoute

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### Connectionbytcpport

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## DESCRIPTION

Das `Test-Connection` -Cmdlet sendet ICMP (Internet Control Message Protocol)-Echo Anforderungs Pakete (Pings) an einen oder mehrere Remote Computer und gibt die Echo Antwort Antworten zurück. Mit diesem Cmdlet können Sie ermitteln, ob ein bestimmter Computer über ein IP-Netzwerk kontaktiert werden kann.

Sie können mit den Parametern von `Test-Connection` sowohl den sendenden als auch den empfangenden Computer angeben, den Befehl als Hintergrund Auftrag ausführen, ein Timeout und eine Anzahl von Pings festlegen und die Verbindung und die Authentifizierung konfigurieren.

Im Gegensatz zum vertrauten **Ping** -Befehl `Test-Connection` gibt ein **testconnectioncommand + pingreport** -Objekt zurück, das Sie in PowerShell untersuchen können. Der **quiet** -Parameter gibt für jede getestete Verbindung einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück. Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.

## BEISPIELE

### Beispiel 1: Senden von ECHO Anforderungen an einen Remote Computer

In diesem Beispiel werden Echo Request-Pakete vom lokalen Computer an den Server01-Computer gesendet.

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
Pinging Server01 [10.59.137.44] with 32 bytes of data:
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Ping complete.

Source     Destination Replies
------     ----------- -------
Server01   Server01    {System.Net.NetworkInformation.PingReply, System.Net.NetworkInformation ...
```

`Test-Connection` verwendet den **TargetName** -Parameter, um den Server01-Computer anzugeben. Der **IPv4** -Parameter gibt das Protokoll für den Test an.

Die Ping-Ausgabe wird an den **Informationsdaten** Strom gesendet, während das **testconnectioncommand + pingreport** -Objekt an den **Success** -Stream gesendet wurde. Weitere Informationen zu den Ausgabestreams finden Sie unter [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).

### Beispiel 2: Senden von ECHO Anforderungen an mehrere Computer

In diesem Beispiel werden Pings vom lokalen Computer an mehrere Remote Computer gesendet.

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### Beispiel 3: Senden von ECHO Anforderungen von mehreren Computern an einen Computer

In diesem Beispiel werden Pings von unterschiedlichen Quell Computern an einen einzelnen Remote Computer, SERVER01, gesendet.

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

Verwenden Sie diesen Befehl, um die Wartezeit von Verbindungen von mehreren Punkten aus zu überprüfen.

### Beispiel 4: Verwenden von Parametern zum Anpassen des Test Befehls

In diesem Beispiel werden die Parameter von verwendet `Test-Connection` , um den Befehl anzupassen. Der lokale Computer sendet einen Pingtest an einen Remote Computer.

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

`Test-Connection` verwendet den **TargetName** -Parameter, um Server01 anzugeben. Der **count** -Parameter gibt an, dass drei Pings mit einer **Verzögerung** von 2-Sekunden-Intervallen an den Server01-Computer gesendet werden.

Sie können diese Optionen verwenden, wenn die Ping-Antwort erwartungsgemäß länger als üblich dauert, entweder aufgrund einer erweiterten Hopanzahl oder einer Netzwerk Bedingung mit hohem Datenverkehr.

### Beispiel 5: Ausführen eines Tests als Hintergrund Auftrag

Dieses Beispiel zeigt, wie Sie einen `Test-Connection` Befehl als PowerShell-Hintergrund Auftrag ausführen.

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

Der `Start-Job` Befehl verwendet das `Test-Connection` Cmdlet, um viele Computer in einem Unternehmen zu pingen.
Der Wert des **TargetName** -Parameters ist ein `Get-Content` Befehl, der eine Liste mit Computernamen aus der `Servers.txt` Datei liest. Der Befehl verwendet das `Start-Job` Cmdlet, um den Befehl als Hintergrund Auftrag auszuführen, und speichert den Auftrag in der `$job` Variablen.

`if`Mit dem Befehl wird überprüft, ob der Auftrag noch nicht ausgeführt wird. Wenn der Auftrag nicht ausgeführt wird, werden `Receive-Job` die Ergebnisse abgerufen und in der `$Results` Variablen gespeichert.

### Beispiel 6: Erstellen einer Sitzung nur, wenn ein Verbindungstest erfolgreich ist

In diesem Beispiel wird nur dann eine Sitzung auf dem Computer Server01 erstellt, wenn mindestens eines der an den Computer gesendeten Pings erfolgreich ist.

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

Der `if` Befehl verwendet das `Test-Connection` Cmdlet, um den Server01-Computer zu pingen. Der Befehl verwendet den **quiet** -Parameter, der einen **booleschen** Wert anstelle eines **testconnectioncommand + pingreport** -Objekts zurückgibt.

Der Wert ist, `$True` Wenn eine der vier Pings erfolgreich ist. Wenn keines der Pings erfolgreich ist, ist der Wert `$False` .

Wenn der `Test-Connection` Befehl den Wert zurückgibt `$True` , verwendet der Befehl das `New-PSSession` Cmdlet, um die **PSSession** zu erstellen.

### Beispiel 7: Verwenden des traceroute-Parameters

Ab PowerShell 6,0 ordnet der **traceroute** -Parameter eine Route zwischen dem lokalen Computer und dem Remote Ziel zu, das Sie mit dem **TargetName** -Parameter angeben.

```powershell
Test-Connection -TargetName www.microsoft.com -Traceroute | ForEach-Object {
  $_ | Format-Table Source, DestinationAddress, DestinationHost
  $_.Replies | ForEach-Object {
      $_ | Format-Table Hop, ReplyRouterAddress
      $_.PingReplies | Format-Table
  }
}
```

```Output
Tracing route to www.microsoft.com [96.6.27.90] over a maximum of 128 hops:
  1   0 ms   0 ms   0 ms   192.168.0.3 [192.168.0.3]
  2   0 ms   0 ms   0 ms   192.168.1.1 [192.168.1.1]
  3   3 ms   29 ms   4 ms   96.6.27.90 [96.6.27.90]
Trace complete.

Source      DestinationAddress DestinationHost   Replies
------      ------------------ ---------------   -------
SERVER01    96.6.27.90         www.microsoft.com {, , }

Hop ReplyRouterAddress
--- ------------------
  1 192.168.0.3

    Status Address      RoundtripTime Options Buffer
    ------ -------      ------------- ------- ------
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  2 192.168.1.1

    Status Address     RoundtripTime Options Buffer
    ------ -------     ------------- ------- ------
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  3 96.6.27.90

 Status Address    RoundtripTime Options                                   Buffer
 ------ -------    ------------- -------                                   ------
Success 96.6.27.90             3 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             2 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             4 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
```

Der `Test-Connection` Befehl verwendet den **traceroute** -Parameter. Die Ergebnisse, bei denen es sich `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` um-Objekte handelt, werden an das `ForEach-Object` Cmdlet weitergeleitet. `ForEach-Object` erstellt eine strukturierte Ausgabe der enthaltenen `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` Objekte und nachfolgenden `[System.Net.NetworkInformation.PingReply]` Objekte.

## PARAMETERS

### -BufferSize

Gibt die Größe des mit diesem Befehl gesendeten Puffers in Bytes an. Der Standardwert ist 32.

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Anzahl

Gibt die Anzahl der zu sendenden Echoanforderungen an. Der Standardwert ist 4.

```yaml
Type: System.Int32
Parameter Sets: PingCount
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verzögerung

Gibt das Intervall zwischen Pings in Sekunden an.

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DontFragment

Dieser Parameter legt das Flag " **nicht Fragment** " im IP-Header fest. Sie können diesen Parameter mit dem **bufferSize** -Parameter verwenden, um den Pfad der MTU-Größe zu testen. Weitere Informationen zu Path MTU finden Sie im Artikel zur Ermittlung der [MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) in Wikipedia.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4

Erzwingt, dass das Cmdlet das IPv4-Protokoll für den Test verwendet.

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

### -IPv6

Erzwingt, dass das Cmdlet das IPv6-Protokoll für den Test verwendet.

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

### -MaxHops

Legt die maximale Anzahl von Hops fest, die eine ICMP-Anforderungs Nachricht senden kann. Der Standardwert wird vom Betriebssystem gesteuert. Der Standardwert für Windows 10 ist 128 Hops.

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ping

Bewirkt, dass das Cmdlet einen Pingtest durchführen kann. Dies ist die Standardaktion.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: Ping test
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quiet

Der **quiet** -Parameter gibt einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück. Durch die Verwendung dieses Parameters werden alle Fehler unterdrückt.

Jede getestete Verbindung gibt einen **booleschen** Wert zurück. Wenn der **TargetName** -Parameter mehrere Computer angibt, wird ein Array von **booleschen** Werten zurückgegeben.

Wenn **ein** Ping erfolgreich ist, `$True` wird zurückgegeben.

Wenn **alle** Pings fehlschlagen, `$False` wird zurückgegeben.

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

### -Resolvedestination

Bewirkt, dass das Cmdlet versucht, den DNS-Namen des Ziels aufzulösen.

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

### -Source

Gibt die Namen der Computer an, von denen der Ping stammt. Geben Sie eine durch Trennzeichen getrennte Liste von Computernamen ein. Die Standardeinstellung ist der lokale Computer.

```yaml
Type: System.String
Parameter Sets: PingCount, PingContinues, TraceRoute, ConnectionByTCPPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName

Gibt die zu testenden Computer an. Geben Sie die Computernamen oder IP-Adressen im IPv4- oder IPv6-Format ein. Platzhalter Zeichen sind nicht zulässig. Dieser Parameter ist erforderlich. **Computername** ist ein Alias für diesen Parameter.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ComputerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TcpPort

Gibt die TCP-Portnummer an, die im TCP-Verbindungstest verwendet werden soll. Mit dem-Cmdlet wird versucht, eine TCP-Verbindung mit dem angegebenen Port auf dem Ziel herzustellen.

```yaml
Type: System.Int32
Parameter Sets: ConnectionByTCPPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeoutSeconds

Legt den Timeout Wert für den Test fest. Der Test schlägt fehl, wenn eine Antwort nicht empfangen wird, bevor das Timeout abläuft. Der Standardwert beträgt fünf Sekunden.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5 seconds
Accept pipeline input: False
Accept wildcard characters: False
```

### -Traceroute

Bewirkt, dass das Cmdlet einen traceroute-Test durchführen kann. Wenn dieser Parameter verwendet wird, gibt das Cmdlet ein- `TestConnectionCommand+TraceRouteResult` Objekt zurück.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TraceRoute
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wird fortgesetzt

Bewirkt, dass das Cmdlet immer dann Ping-Anforderungen sendet. Dieser Parameter kann nicht mit dem **count** -Parameter verwendet werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mtusizedetect

Dieser Parameter wird verwendet, um den Pfad der MTU-Größe zu ermitteln. Das-Cmdlet gibt ein **PingReply # mtusize** -Objekt zurück, das den Pfad der MTU-Größe zum Ziel enthält. Weitere Informationen zu Path MTU finden Sie im Artikel zur Ermittlung der [MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) in Wikipedia.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetectionOfMTUSize
Aliases:

Required: True
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

### Testconnectioncommand + pingreport, testconnectioncommand + tracerouteresult, Boolean, PingReply # mtusize

Wenn Sie den **quiet** -Parameter angeben, wird ein **boolescher** Wert zurückgegeben. Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben. Andernfalls wird `Test-Connection` für jeden Ping ein **testconnectioncommand + pingreport** -Objekt zurückgegeben.

## HINWEISE

## VERWANDTE LINKS

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
