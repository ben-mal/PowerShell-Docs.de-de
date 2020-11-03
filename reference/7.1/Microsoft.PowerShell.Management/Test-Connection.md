---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 6a03d5a644e3d4be515a93a702d0ef0aff23a8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212188"
---
# Test-Connection

## ZUSAMMENFASSUNG
Sendet ICMP-Echo Anforderungs Pakete (Pings) an einen oder mehrere Computer.

## SYNTAX

### Defaultping (Standard)

```
Test-Connection [-TargetName] <string[]> [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Count <int>] [-Delay <int>] [-BufferSize <int>]
 [-DontFragment] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### Repeatping

```
Test-Connection [-TargetName] <string[]> -Repeat [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Delay <int>] [-BufferSize <int>] [-DontFragment]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### Mtusizedetect

```
Test-Connection [-TargetName] <string[]> -MtuSize [-IPv4] [-IPv6] [-ResolveDestination]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### TraceRoute

```
Test-Connection [-TargetName] <string[]> -Traceroute [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### TcpPort

```
Test-Connection [-TargetName] <string[]> -TcpPort <int> [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

## DESCRIPTION

Das `Test-Connection` -Cmdlet sendet ICMP (Internet Control Message Protocol)-Echo Anforderungs Pakete (Pings) an einen oder mehrere Remote Computer und gibt die Echo Antwort Antworten zurück. Mit diesem Cmdlet können Sie ermitteln, ob ein bestimmter Computer über ein IP-Netzwerk kontaktiert werden kann.

Sie können mit den Parametern von `Test-Connection` sowohl den sendenden als auch den empfangenden Computer angeben, den Befehl als Hintergrund Auftrag ausführen, ein Timeout und eine Anzahl von Pings festlegen und die Verbindung und die Authentifizierung konfigurieren.

Im Gegensatz zum vertrauten **Ping** -Befehl `Test-Connection` gibt ein **testconnectioncommand + Pingstatus** -Objekt zurück, das Sie in PowerShell untersuchen können. Der **quiet** -Parameter gibt für jede getestete Verbindung einen **booleschen** Wert in einem **System. Boolean** -Objekt zurück. Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.

## BEISPIELE

### Beispiel 1: Senden von ECHO Anforderungen an einen Remote Computer

In diesem Beispiel werden Echo Request-Pakete vom lokalen Computer an den Server01-Computer gesendet.

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
   Destination: Server01

Ping Source           Address                   Latency BufferSize Status
                                                   (ms)        (B)
---- ------           -------                   ------- ---------- ------
   1 ADMIN1           10.59.137.44                   24         32 Success
   2 ADMIN1           10.59.137.44                   39         32 Success
   3 ADMIN1           *                               *          * TimedOut
   4 ADMIN1           10.59.137.44                   28         32 Success
```

`Test-Connection` verwendet den **TargetName** -Parameter, um den Server01-Computer anzugeben. Der **IPv4** -Parameter gibt das Protokoll für den Test an.

Eine Reihe von **Test ConnectionCommand + Pingstatus** -Objekten wird an den Ausgabestream gesendet, ein Objekt pro Ping-Antwort vom Zielcomputer.

### Beispiel 2: Senden von ECHO Anforderungen an mehrere Computer

In diesem Beispiel werden Pings vom lokalen Computer an mehrere Remote Computer gesendet.

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### Beispiel 3: Verwenden von Parametern zum Anpassen des Test Befehls

In diesem Beispiel werden die Parameter von verwendet `Test-Connection` , um den Befehl anzupassen. Der lokale Computer sendet einen Pingtest an einen Remote Computer.

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

`Test-Connection` verwendet den **TargetName** -Parameter, um Server01 anzugeben. Der **count** -Parameter gibt an, dass drei Pings mit einer **Verzögerung** von 2-Sekunden-Intervallen an den Server01-Computer gesendet werden.

Sie können diese Optionen verwenden, wenn die Ping-Antwort erwartungsgemäß länger als üblich dauert, entweder aufgrund einer erweiterten Hopanzahl oder einer Netzwerk Bedingung mit hohem Datenverkehr.

### Beispiel 4: Ausführen eines Tests als Hintergrund Auftrag

Dieses Beispiel zeigt, wie Sie einen `Test-Connection` Befehl als PowerShell-Hintergrund Auftrag ausführen.

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content -Path "Servers.txt") }
$Results = Receive-Job $job -Wait
```

Der `Start-Job` Befehl verwendet das `Test-Connection` Cmdlet, um viele Computer in einem Unternehmen zu pingen.
Der Wert des **TargetName** -Parameters ist ein `Get-Content` Befehl, der eine Liste mit Computernamen aus der `Servers.txt` Datei liest. Der Befehl verwendet das `Start-Job` Cmdlet, um den Befehl als Hintergrund Auftrag auszuführen, und speichert den Auftrag in der `$job` Variablen.

Der `Receive-Job` -Befehl wird an den, `-Wait` bis der Auftrag abgeschlossen ist, und ruft dann die Ergebnisse ab und speichert Sie in der `$Results` Variablen.

### Beispiel 5: Erstellen einer Sitzung nur, wenn ein Verbindungstest erfolgreich ist

In diesem Beispiel wird nur dann eine Sitzung auf dem Computer Server01 erstellt, wenn mindestens eines der an den Computer gesendeten Pings erfolgreich ist.

```powershell
if (Test-Connection -TargetName Server01 -Quiet) { New-PSSession -ComputerName Server01 }
```

Das `Test-Connection` Cmdlet Pingt den `Server01` Computer mit dem angegebenen **quiet** -Parameter.
Der resultierende Wert ist, `$True` Wenn eine der vier Pings erfolgreich ist. Wenn keines der Pings erfolgreich ist, ist der Wert `$False` .

Wenn der `Test-Connection` Befehl den Wert zurückgibt `$True` , verwendet der Befehl das `New-PSSession` Cmdlet, um die **PSSession** zu erstellen.

### Beispiel 6: Verwenden des traceroute-Parameters

Mit dem Parameter **traceroute** , der in PowerShell 6,0 eingeführt wurde, wird eine Route zwischen dem lokalen Computer und dem Remote Ziel, das Sie angeben, mit dem **TargetName** -Parameter zugeordnet.

```powershell
Test-Connection -TargetName www.google.com -Traceroute
```

```Output
   Target: google.com

Hop Hostname                  Ping Latency Status           Source       TargetAddress
                                      (ms)
--- --------                  ---- ------- ------           ------       -------------
  1 172.20.0.1                   1       4 Success          Lira         172.217.9.174
  1 172.20.0.1                   2       3 Success          Lira         172.217.9.174
  1 172.20.0.1                   3       2 Success          Lira         172.217.9.174
  2 12.108.153.193               1       3 Success          Lira         172.217.9.174
  2 12.108.153.193               2       3 Success          Lira         172.217.9.174
  2 12.108.153.193               3       2 Success          Lira         172.217.9.174
  3 12.244.85.177                1      11 Success          Lira         172.217.9.174
  3 12.244.85.177                2      12 Success          Lira         172.217.9.174
  3 12.244.85.177                3      12 Success          Lira         172.217.9.174
  4 *                            1      14 DestinationNetw… Lira         172.217.9.174
  4 *                            2       * TimedOut         Lira         172.217.9.174
  4 *                            3      20 DestinationNetw… Lira         172.217.9.174
  5 *                            1       * TimedOut         Lira         172.217.9.174
  5 *                            2      15 DestinationNetw… Lira         172.217.9.174
  5 *                            3       * TimedOut         Lira         172.217.9.174
  6 *                            1      18 DestinationNetw… Lira         172.217.9.174
  6 *                            2       * TimedOut         Lira         172.217.9.174
  6 *                            3      16 DestinationNetw… Lira         172.217.9.174
  7 *                            1       * TimedOut         Lira         172.217.9.174
  7 *                            2       * TimedOut         Lira         172.217.9.174
  7 *                            3       * TimedOut         Lira         172.217.9.174
  8 *                            1       * TimedOut         Lira         172.217.9.174
  8 *                            2       * TimedOut         Lira         172.217.9.174
  8 *                            3       * TimedOut         Lira         172.217.9.174
  9 *                            1       * TimedOut         Lira         172.217.9.174
  9 *                            2       * TimedOut         Lira         172.217.9.174
  9 *                            3       * TimedOut         Lira         172.217.9.174
 10 *                            1       * TimedOut         Lira         172.217.9.174
 10 *                            2       * TimedOut         Lira         172.217.9.174
 10 *                            3       * TimedOut         Lira         172.217.9.174
 11 172.217.9.174                1      23 Success          Lira         172.217.9.174
 11 172.217.9.174                2      21 Success          Lira         172.217.9.174
 11 172.217.9.174                3      22 Success          Lira         172.217.9.174
```

Der `Test-Connection` Befehl wird mit dem **traceroute** -Parameter aufgerufen. Die Ergebnisse, bei denen es sich `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` um-Objekte handelt, werden an den **Erfolgs** Datenstrom ausgegeben.

## PARAMETERS

### -BufferSize

Gibt die Größe des mit diesem Befehl gesendeten Puffers in Bytes an. Der Standardwert ist 32.

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wiederholen

Bewirkt, dass das Cmdlet immer dann Ping-Anforderungen sendet. Dieser Parameter kann nicht mit dem **count** -Parameter verwendet werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RepeatPing
Aliases: Continuous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Anzahl

Gibt die Anzahl der zu sendenden Echoanforderungen an. Der Standardwert ist 4.

```yaml
Type: System.Int32
Parameter Sets: DefaultPing
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
Parameter Sets: DefaultPing, RepeatPing
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
Parameter Sets: DefaultPing, RepeatPing
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
Parameter Sets: DefaultPing, RepeatPing, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ping

Bewirkt, dass das Cmdlet einen Ping-Test durchführen kann. Dies ist der Standardmodus für das- `Test-Connection` Cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quiet

Der **quiet** -Parameter gibt einen **booleschen** Wert zurück. Durch die Verwendung dieses Parameters werden alle Fehler unterdrückt.

Jede getestete Verbindung gibt einen **booleschen** Wert zurück. Wenn der **TargetName** -Parameter mehrere Computer angibt, wird ein Array von **booleschen** Werten zurückgegeben.

Wenn **ein** Ping an ein bestimmtes Ziel erfolgreich `$True` ist, wird zurückgegeben.

Wenn **alle** Pings an ein bestimmtes Ziel fehlschlagen, `$False` wird zurückgegeben.

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

Bewirkt, dass das Cmdlet versucht, den DNS-Namen des Ziels aufzulösen. Wenn es in Verbindung mit dem **traceroute** -Parameter verwendet wird, werden die DNS-Namen aller zwischen Hosts nach Möglichkeit auch abgerufen.

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

**Hinweis:** Dieser Parameter ist in PowerShell, Version 6 und höher, nicht funktionsfähig.
Das Bereitstellen dieses Parameters hat keine Auswirkung auf den Befehl.

```yaml
Type: System.String
Parameter Sets: DefaultPing, RepeatPing, TraceRoute, TcpPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName

Gibt die zu testenden Computer an. Geben Sie die Computernamen oder IP-Adressen im IPv4- oder IPv6-Format ein.

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

Bewirkt, dass das Cmdlet einen traceroute-Test durchführen kann. Wenn dieser Parameter verwendet wird, gibt das Cmdlet ein- `TestConnectionCommand+TraceStatus` Objekt zurück.

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

### -Mtusize

Dieser Parameter wird verwendet, um den Pfad der MTU-Größe zu ermitteln. Das-Cmdlet gibt ein **PingReply # mtusize** -Objekt zurück, das den Pfad der MTU-Größe zum Ziel enthält. Weitere Informationen zu Path MTU finden Sie im Artikel zur Ermittlung der [MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) in Wikipedia.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MtuSizeDetect
Aliases: MtuSizeDetect

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -TcpPort

Gibt die TCP-Portnummer an, die im TCP-Verbindungstest verwendet werden soll. Mit dem-Cmdlet wird versucht, eine TCP-Verbindung mit dem angegebenen Port auf dem Ziel herzustellen.

Wenn eine Verbindung hergestellt werden kann, `$True` wird zurückgegeben.

Wenn eine Verbindung nicht hergestellt werden kann, `$False` wird zurückgegeben.

```yaml
Type: System.Int32
Parameter Sets: TcpPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet übergeben werden.

## AUSGABEN

### Testconnectioncommand + Pingstatus, testconnectioncommand + TRACESTATUS, Boolean, testconnectioncommand und pingmtustatus

Standardmäßig wird `Test-Connection` für jede Ping-Antwort ein **testconnectioncommand + Pingstatus** -Objekt zurückgegeben.

Wenn Sie den **traceroute** -Parameter angeben, gibt das Cmdlet ein **testconnectioncommand + TRACESTATUS** -Objekt für jede Ping-Antwort entlang der Route zurück.

Wenn Sie die Parameter " **quiet** " oder " **TcpPort** " angeben, wird ein **boolescher** Wert zurückgegeben. Wenn mehrere Verbindungen getestet werden, wird ein Array von **booleschen** Werten zurückgegeben.

## HINWEISE

## VERWANDTE LINKS

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)

