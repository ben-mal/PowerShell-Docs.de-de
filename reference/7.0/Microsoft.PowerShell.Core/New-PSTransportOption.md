---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pstransportoption?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSTransportOption
ms.openlocfilehash: b8493931e6390dfb6a3c4becb5a9f51d79df0574
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218492"
---
# New-PSTransportOption

## ZUSAMMENFASSUNG
Erstellt ein Objekt, das erweiterte Optionen für eine Sitzungskonfiguration enthält.

## SYNTAX

```
New-PSTransportOption [-MaxIdleTimeoutSec <Int32>] [-ProcessIdleTimeoutSec <Int32>] [-MaxSessions <Int32>]
 [-MaxConcurrentCommandsPerSession <Int32>] [-MaxSessionsPerUser <Int32>] [-MaxMemoryPerSessionMB <Int32>]
 [-MaxProcessesPerSession <Int32>] [-MaxConcurrentUsers <Int32>] [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [<CommonParameters>]
```

## DESCRIPTION

Das **New-PSTransportOption** -Cmdlet erstellt ein Objekt, das Transportoptionen für Sitzungskonfigurationen enthält.
Sie können das Objekt als Wert des *Transportoption* -Parameters von Cmdlets verwenden, die eine Sitzungs Konfiguration erstellen oder ändern, z. b. die Cmdlets Register-PSSessionConfiguration und Set-PSSessionConfiguration.

Sie können auch die Einstellungen für Transportoptionen ändern, indem Sie die Werte der Sitzungskonfigurationseigenschaften im Laufwerk „WSMan:“ bearbeiten.
Weitere Informationen finden Sie unter WSMAN Provider.

Die Sitzungs Konfigurationsoptionen stellen die Sitzungs Werte dar, die auf Serverseite festgelegt sind, oder das Ende einer Remote Verbindung.
Das Client seitige oder sende Ende der Verbindung kann die Sitzungs Optionswerte festlegen, wenn die Sitzung erstellt wird, oder wenn der Client die Verbindung mit der Sitzung trennt oder wiederherstellt.
Sofern nicht anders angegeben, haben die clientseitigen Werte bei einem Wertekonflikt Vorrang.
Allerdings dürfen die clientseitigen Werte die maximalen, in der Sitzungskonfiguration festgelegten Werte und Kontingente nicht überschreiten.

Ohne Parameter generiert **New-pstransportoption** ein Transport Options Objekt, das NULL-Werte für alle Optionen enthält.
Wenn Sie einen Parameter auslassen, verfügt das Objekt über einen NULL-Wert für die Eigenschaft, die vom Parameter dargestellt wird.
Ein NULL-Wert hat keine Auswirkung auf die Sitzungs Konfiguration.

Weitere Informationen zu Sitzungs Optionen finden Sie unter New-pssessionoption.
Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Generieren einer Standard Transport Option

```powershell
New-PSTransportOption
```

```Output
ProcessIdleTimeoutSec           :
MaxIdleTimeoutSec               :
MaxSessions                     :
MaxConcurrentCommandsPerSession :
MaxSessionsPerUser              :
MaxMemoryPerSessionMB           :
MaxProcessesPerSession          :
MaxConcurrentUsers              :
IdleTimeoutSec                  :
OutputBufferingMode             :
```

Dieser Befehl führt **New-pstransportoption** ohne Parameter aus.
Die Ausgabe zeigt, dass das Cmdlet ein Transport Options Objekt generiert, das NULL-Werte für alle Eigenschaften hat.

### Beispiel 2: Get-Sitzungs Konfigurationsoptionen

In diesem Beispiel wird gezeigt, wie ein Transport Options Objekt zum Festlegen von Sitzungs Konfigurationsoptionen verwendet wird.

```powershell
$t = New-PSTransportOption -MaxSessions 40
Register-PSSessionConfiguration -Name ITTasks -TransportOption $t
Get-PSSessionConfiguration -Name ITTasks | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITTasks
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 40
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 2
Name                          : ITTasks
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
Enabled                       : True
MaxShellsPerUser              : 25
Permission                    :
```

Der erste Befehl verwendet das **New-PSTransportOption** -Cmdlet, um ein Transportoptionsobjekt zu erstellen, das in der $t-Variablen gespeichert wird. Der Befehl verwendet den *MaxSessions* -Parameter, um die maximale Anzahl von Sitzungen auf 40 zu erhöhen.

Der zweite Befehl verwendet das **Register-PSSessionConfiguration** -Cmdlet, um die ITTasks-Sitzungskonfiguration zu erstellen. Der Befehl verwendet den  *TransportOption* -Parameter, um das Transportoptionsobjekt in der $t-Variablen anzugeben.

Der dritte Befehl verwendet das Cmdlet "Get-PSSessionConfiguration", um die ittasks-Sitzungs Konfigurationen zu erhalten, und das Format-List-Cmdlet, um alle Eigenschaften des Sitzungs Konfigurations Objekts in einer Liste anzuzeigen. Die Ausgabe zeigt, dass der Wert der **MaxShells** -Eigenschaft der Sitzungskonfiguration 40 ist.

### Beispiel 3: Festlegen einer Transport Option

Dieser Befehl zeigt, wie sich die Einstellung einer Transportoption in einer Sitzungskonfiguration auf Sitzungen auswirkt, die die Sitzungskonfiguration verwenden.

```powershell
$t = New-PSTransportOption -IdleTimeoutSec 3600
Set-PSSessionConfiguration -Name ITTasks -TransportOption $t
$s = New-PSSession -Name MyITTasks -ConfigurationName ITTasks
$s | Format-List -Property *
```

```Output
State                  : Opened
IdleTimeout            : 3600000
OutputBufferingMode    : Block
ComputerName           : localhost
ConfigurationName      : ITTasks
InstanceId             : 4110c3f5-68ea-40fa-9bbf-04a433dbb02d
Id                     : 1
Name                   : MyITTasks
Availability           : Available
ApplicationPrivateData : {PSVersionTable}
Runspace               : System.Management.Automation.RemoteRunspace
```

Der erste Befehl verwendet das **New-PSTransportOption** -Cmdlet, um ein Transportoptionsobjekt zu erstellen. Der Befehl verwendet den *IdleTimeoutSec* -Parameter zum Festlegen des **IdleTimeoutSec** -Eigenschaftswerts des Objekts auf eine Stunde (3.600 Sekunden). Der Befehl speichert das Transportoptionsobjekt in der $t-Variablen.

Der zweite Befehl verwendet das Cmdlet "Set-PSSessionConfiguration", um die Transport Optionen der ittasks-Sitzungs Konfiguration zu ändern. Der Befehl verwendet den  *TransportOption* -Parameter, um das Transportoptionsobjekt in der $t-Variablen anzugeben.

Der dritte Befehl verwendet das Cmdlet "New-PSSession", um die myittasks-Sitzung auf dem lokalen Computer zu erstellen. Der Befehl verwendet die **ConfigurationName** -Eigenschaft, um die ITTasks-Sitzungskonfiguration anzugeben. Der Befehl speichert die Sitzung in der $s Variable. Beachten Sie, dass der Befehl den *sessionoption* -Parameter von **New-PSSession** nicht verwendet, um eine benutzerdefinierte Leerlaufzeit Überschreitung für die Sitzung festzulegen. Wenn dies der Fall ist, hat der in der Sitzungs Option festgelegte Leerlauf Timeout Wert Vorrang vor dem in der Sitzungs Konfiguration festgelegten Leerlauf Timeout.

Der vierte Befehl verwendet das Cmdlet "Format-List", um alle Eigenschaften der Sitzung in der $s Variablen in einer Liste anzuzeigen. Die Ausgabe zeigt, dass die Sitzung eine Leerlaufzeit von einer Stunde (360.000 Millisekunden) aufweist.

## PARAMETERS

### -Idletimeoutsec

Bestimmt, wie lange die einzelnen Sitzungen geöffnet bleiben, wenn der Remote Computer keine Kommunikation vom lokalen Computer empfängt.
Dies schließt das Taktsignal ein.
Wenn das Intervall abläuft, wird die Sitzung geschlossen.

Der Wert für das Leerlauf Timeout ist von großer Wichtigkeit, wenn der Benutzer die Verbindung zu einer Sitzung trennen und wiederherstellen möchte.
Der Benutzer kann die Verbindung nur wiederherstellen, wenn für die Sitzung keine Zeitüberschreitung eingetreten ist.

Der *idletimeoutsec* -Parameter entspricht der **idletimeoutms** -Eigenschaft einer Sitzungs Konfiguration.

Geben Sie einen Wert in Sekunden ein.
Der Standardwert beträgt 7.200 Sekunden (2 Stunden).
Der minimale Wert beträgt 60 Sekunden (1 Minute).
Der Höchstwert ist der Wert der **IdleTimeout** -Eigenschaft von shellobjekten in der WSMAN-Konfiguration ( `WSMan:\\\<ComputerName\>\Shell\IdleTimeout` ).
Der Standardwert beträgt 7.200.000 Millisekunden (2 Stunden).

Wenn ein Leerlauf Timeout Wert in den Sitzungs Optionen und in der Sitzungs Konfiguration festgelegt ist, hat der in den Sitzungs Optionen festgelegte Wert Vorrang, aber er darf den Wert der **maxidletimeoutms** -Eigenschaft der Sitzungs Konfiguration nicht überschreiten.
Um den Wert der **MaxIdleTimeoutMs** -Eigenschaft festzulegen, verwenden Sie den *MaxIdleTimeoutSec* -Parameter.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Maxconcurrentcommandspersession

Beschränkt die Anzahl der Befehle, die in jeder Sitzung gleichzeitig ausgeführt werden können, auf den angegebenen Wert.
Der Standardwert lautet „1000“.

Der *maxconcurrentcommandspersession* -Parameter entspricht der **maxconcurrentcommandspershell** -Eigenschaft einer Sitzungs Konfiguration.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Maxconcurrentusers

Beschränkt die Anzahl der Benutzer, die in jeder Sitzung Befehle gleichzeitig ausführen können, auf den angegebenen Wert.
Der Standardwert ist 5.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Maxidletimeoutsec

Schränkt die Leerlaufzeit Überschreitung für jede Sitzung auf den angegebenen Wert ein.
Der Standardwert ist \[ int \] :: MaxValue (~ 25 Tage).

Der Wert für das Leerlauf Timeout ist von großer Wichtigkeit, wenn der Benutzer die Verbindung zu einer Sitzung trennen und wiederherstellen möchte.
Der Benutzer kann die Verbindung nur wiederherstellen, wenn für die Sitzung keine Zeitüberschreitung eingetreten ist.

Der *maxidletimeoutsec* -Parameter entspricht der **maxidletimeoutms** -Eigenschaft einer Sitzungs Konfiguration.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Maxmemorypersessionmb

Beschränkt die Arbeitsspeichernutzung pro Sitzung auf den angegebenen Wert.
Geben Sie einen Wert in Megabytes ein.
Der Standardwert ist 1.024 MB (1 GB).

Der *maxmemorypersessionmb* -Parameter entspricht der **maxmemorypershellmb** -Eigenschaft einer Sitzungs Konfiguration.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Maxprocessespersession

Beschränkt die Anzahl der Prozesse, die pro Sitzung ausgeführt werden, auf den angegebenen Wert.
Der Standardwert ist 15.

Der *maxprocessespersession* -Parameter entspricht der **maxprocessespershell** -Eigenschaft einer Sitzungs Konfiguration.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxSessions

Beschränkt die Anzahl der Sitzungen, die die Sitzungskonfiguration verwenden.
Der Standardwert ist 25.

Der *MaxSessions* -Parameter entspricht der **MaxShells** -Eigenschaft einer Sitzungskonfiguration.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Maxsessionsperuser

Beschränkt die Anzahl der Sitzungen, die die Sitzungskonfiguration verwenden und unter den Anmeldeinformationen eines bestimmten Benutzers ausgeführt werden, auf den angegebenen Wert.
Der Standardwert ist 25.

Wenn Sie diesen Wert angeben, sollten Sie Bedenken, dass viele Benutzer möglicherweise die Anmelde Informationen eines "Ausführen als"-Benutzers verwenden.

Der *maxsessionsperuser* -Parameter entspricht der **maxshellsperuser** -Eigenschaft einer Sitzungs Konfiguration.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Outputbufferingmode

Bestimmt, wie die Befehlsausgabe in getrennten Sitzungen verwaltet wird, wenn sich der Ausgabepuffer füllt.
Zulässige Werte für diesen Parameter:

- Blockierung.
Wenn der Ausgabepuffer voll ist, wird die Ausführung unterbrochen, bis der Puffer leer ist.
- Ablage.
Wenn der Ausgabepuffer voll ist, wird die Ausführung fortgesetzt.
Sobald neue Ausgabedaten gespeichert werden, wird die älteste Ausgabe verworfen.
- Keine
Es wurde kein Ausgabepufferungsmodus angegeben.

Der Standardwert der **outputbufferingmode** -Eigenschaft von Sessions ist Block.

```yaml
Type: System.Nullable`1[System.Management.Automation.Runspaces.OutputBufferingMode]
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Processidletimeoutsec

Schränkt den Timeout Wert für jeden Host Prozess auf den angegebenen Wert ein.
Der Standardwert 0 (null) bedeutet, dass kein Timeout Wert für den Prozess vorhanden ist.

Andere Sitzungs Konfigurationen verfügen über prozessspezifische Timeout Werte.
Die **Microsoft. PowerShell. Workflow** -Sitzungs Konfiguration verfügt z. b. über einen prozessspezifischen Timeout Wert von 28800 Sekunden (8 Stunden).

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Microsoft. PowerShell. Commands. wsmanconfigurationoption

## HINWEISE

- Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab. Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.

## VERWANDTE LINKS

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)
