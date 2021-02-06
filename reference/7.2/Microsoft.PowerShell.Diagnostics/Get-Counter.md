---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-counter?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Counter
ms.openlocfilehash: 4aed8db557b2d623aba4cd7218524af9957674c9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599830"
---
# Get-Counter

## ZUSAMMENFASSUNG
Ruft die Leistungsindikatordaten von lokalen Computern und Remotecomputern ab.

## SYNTAX

### Getcounterset (Standard)

```
Get-Counter [[-Counter] <String[]>] [-SampleInterval <Int32>] [-MaxSamples <Int64>] [-Continuous]
 [-ComputerName <String[]>] [<CommonParameters>]
```

### Listsetset

```
Get-Counter [-ListSet] <String[]> [-ComputerName <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-Counter` Cmdlet werden Leistungsdaten des Leistungs Zählers direkt aus der Leistungs Überwachungs Instrumentation in der Windows-Betriebssystem Familie abgerufen. `Get-Counter` dient zum Abrufen von Leistungsdaten von einem lokalen Computer oder von Remote Computern.

Mit den `Get-Counter` Parametern können Sie einen oder mehrere Computer angeben, die Leistungs Indikatorensätze und die darin enthaltenen Instanzen auflisten, die Stichproben Intervalle festlegen und die maximale Anzahl von Stichproben angeben. Ohne Parameter ruft `Get-Counter` Leistungsindikator Daten für einen Satz von System Indikatoren ab.

Viele Indikatorensätze werden durch Zugriffs Steuerungs Listen (Access Control Lists, ACL) geschützt. Um alle Indikatorensätze anzuzeigen, öffnen Sie PowerShell mit der Option **als Administrator ausführen** .

Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt.

## BEISPIELE

### Beispiel 1: erhalten der Liste der Counter-Sets

In diesem Beispiel wird die Liste der Indikatorensätze des lokalen Computers abgerufen.

```powershell
Get-Counter -ListSet *
```

```Output
CounterSetName     : Processor
MachineName        : .
CounterSetType     : MultiInstance
Description        : The Processor performance object consists of counters that measure aspects ...
                     computer that performs arithmetic and logical computations, initiates ...
                     computer can have multiple processors.  The processor object represents ...
Paths              : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
PathsWithInstances : {\Processor(0)\% Processor Time, \Processor(1)\% Processor Time, ...
Counter            : {\Processor(*)\% Processor Time, \Processor(*)\% User Time, ...
```

`Get-Counter` verwendet den **listset** -Parameter mit einem Sternchen ( `*` ), um die Liste der Indikatorensätze zu erhalten.
Der Punkt ( `.` ) in der Spalte " **MachineName** " steht für den lokalen Computer.

### Beispiel 2: Angeben von sampleingeterval und maxsamples

In diesem Beispiel werden die gegen Daten für alle Prozessoren auf dem lokalen Computer abgerufen. Daten werden in Intervallen von zwei Sekunden erfasst, bis drei Stichproben vorhanden sind.

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 3
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/18/2019 14:39:56        \\Computer01\processor(_total)\% processor time :
                          20.7144271584086

6/18/2019 14:39:58        \\Computer01\processor(_total)\% processor time :
                          10.4391790575511

6/18/2019 14:40:01        \\Computer01\processor(_total)\% processor time :
                          37.5968799396998
```

`Get-Counter` verwendet den **Counter** -Parameter, um den Counter-Pfad anzugeben `\Processor(_Total)\% Processor Time` . Der Parameter " **sampleinterval** " legt ein Intervall von zwei Sekunden fest, um den Wert zu überprüfen. Mit " **maxsamples** " wird festgelegt, dass drei die maximale Anzahl von Wiederholungen für den Zählers ist.

### Beispiel 3: erhalten von kontinuierlichen Beispielen eines Zählers

In diesem Beispiel werden pro Sekunde kontinuierliche Beispiele für einen Gegentreffer abgerufen. Drücken Sie zum Abbrechen des Befehls <kbd>STRG</kbd> + <kbd>C</kbd>. Um ein längeres Intervall zwischen Stichproben anzugeben, verwenden Sie den Parameter **sampleingeterval** .

```powershell
Get-Counter -Counter "\Processor(_Total)\% Processor Time" -Continuous
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 15:35:03        \\Computer01\processor(_total)\% processor time :
                          43.8522842937022

6/19/2019 15:35:04        \\Computer01\processor(_total)\% processor time :
                          29.7896844697383

6/19/2019 15:35:05        \\Computer01\processor(_total)\% processor time :
                          29.4962645638135

6/19/2019 15:35:06        \\Computer01\processor(_total)\% processor time :
                          25.5901500127408
```

`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert anzugeben `\Processor\% Processor Time` .
Der **fortlaufende** Parameter gibt an, dass die Stichproben pro Sekunde angezeigt werden, bis der Befehl mit <kbd>STRG</kbd> + <kbd>C</kbd>beendet wird.

### Beispiel 4: alphabetische Liste der Indikatorensätze

In diesem Beispiel wird die Pipeline verwendet, um den Satz von Counter Listen zu erhalten und die Liste dann in alphabetischer Reihenfolge zu sortieren.

```powershell
Get-Counter -ListSet * |
  Sort-Object -Property CounterSetName |
    Format-Table CounterSetName, CounterSetType -AutoSize
```

```Output
CounterSetName                        CounterSetType
--------------                        --------------
.NET CLR Data                         SingleInstance
.NET Data Provider for SqlServer      SingleInstance
AppV Client Streamed Data Percentage  SingleInstance
Authorization Manager Applications    SingleInstance
BitLocker                             MultiInstance
Bluetooth Device                      SingleInstance
Cache                                 SingleInstance
Client Side Caching                   SingleInstance
```

`Get-Counter` verwendet den **listset** -Parameter mit einem Sternchen ( `*` ), um eine komplette Liste von Indikatorensätzen zu erhalten. Die **CounterSet** -Objekte werden über die Pipeline gesendet. `Sort-Object` verwendet den **Property** -Parameter, um anzugeben, dass die Objekte nach **countersetname** sortiert werden. Die Objekte werden über die Pipeline an gesendet `Format-Table` . Der **AutoSize** -Parameter passt die Spaltenbreite an, um das Abschneiden zu minimieren.

Der Punkt ( `.` ) in der Spalte " **MachineName** " steht für den lokalen Computer.

### Beispiel 5: Ausführen eines Hintergrund Auftrags zum erhalten von Counter-Daten

In diesem Beispiel `Start-Job` führt einen `Get-Counter` Befehl als Hintergrund Auftrag auf dem lokalen Computer aus.
Verwenden Sie das-Cmdlet, um die Leistungsdaten der Ausgabe des Auftrags anzuzeigen `Receive-Job` .

```powershell
Start-Job -ScriptBlock {Get-Counter -Counter "\LogicalDisk(_Total)\% Free Space" -MaxSamples 1000}
```

```Output
Id     Name  PSJobTypeName   State    HasMoreData  Location   Command
--     ----  -------------   -----    -----------  --------   -------
1      Job1  BackgroundJob   Running  True         localhost  Get-Counter -Counter
```

`Start-Job` verwendet den **ScriptBlock** -Parameter, um einen `Get-Counter` Befehl auszuführen. `Get-Counter` verwendet den **Counter** -Parameter, um den Counter-Pfad anzugeben `\LogicalDisk(_Total)\% Free Space` . Der Parameter " **maxsamples** " gibt an, dass 1000 Stichproben des Zählers erhalten werden.

### Beispiel 6: erhalten von gegen Daten von mehreren Computern

In diesem Beispiel wird eine Variable verwendet, um Leistungsdaten der Leistungsdaten von zwei Computern zu erhalten.

```powershell
$DiskReads = "\LogicalDisk(C:)\Disk Reads/sec"
$DiskReads | Get-Counter -ComputerName Server01, Server02 -MaxSamples 10
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/21/2019 10:51:04        \\Server01\logicaldisk(c:)\disk reads/sec :
                          0

                          \\Server02\logicaldisk(c:)\disk reads/sec :
                          0.983050344269146
```

Die `$DiskReads` Variable speichert den `\LogicalDisk(C:)\Disk Reads/sec` Counter-Pfad. Die `$DiskReads` Variable wird an die Pipeline gesendet `Get-Counter` . **Counter** ist der erste Positions Parameter und akzeptiert den in gespeicherten Pfad `$DiskReads` . **Computername** gibt die beiden Computer und **maxsamples** an, um 10 Stichproben von den einzelnen Computern zu erhalten.

### Beispiel 7: erhalten der Instanzwerte eines Zählers von mehreren zufälligen Computern

In diesem Beispiel wird der Wert eines Leistungs Zählers auf 50 zufälligen Remote Computern im Unternehmen abgerufen. Der **Computername** -Parameter verwendet zufällige Computernamen, die in einer Variablen gespeichert sind. Um die Computernamen in der Variablen zu aktualisieren, erstellen Sie die Variable neu.

Eine Alternative für die Servernamen im **Computername** -Parameter ist die Verwendung einer Textdatei. Beispiel:

`-ComputerName (Get-Random (Get-Content -Path C:\Servers.txt) -Count 50)`

Der Counter-Pfad enthält ein Sternchen ( `*` ) im Instanznamen, um die Daten für die einzelnen Prozessoren des Remote Computers zu erhalten.

```powershell
$Servers = Get-Random (Get-Content -Path C:\Servers.txt) -Count 50
$Counter = "\Processor(*)\% Processor Time"
Get-Counter -Counter $Counter -ComputerName $Servers
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/20/2019 12:20:35        \\Server01\processor(0)\% processor time :
                          6.52610319637854

                          \\Server01\processor(1)\% processor time :
                          3.41030663625782

                          \\Server01\processor(2)\% processor time :
                          9.64189975649925

                          \\Server01\processor(3)\% processor time :
                          1.85240835619747

                          \\Server01\processor(_total)\% processor time :
                          5.35768447160776
```

Das- `Get-Random` Cmdlet verwendet `Get-Content` , um in der Datei 50 zufällige Computernamen auszuwählen `Servers.txt` . Die Remote Computernamen werden in der `$Servers` Variablen gespeichert. Der `\Processor(*)\% Processor Time` Pfad des Zählers wird in der `$Counter` Variablen gespeichert. `Get-Counter` verwendet den **Counter** -Parameter, um die Indikatoren in der `$Counter` Variablen anzugeben. Der Computer **Name** -Parameter gibt die Computernamen in der `$Servers` Variablen an.

### Beispiel 8: Verwenden der Path-Eigenschaft zum erhalten von formatierten Pfadnamen

In diesem Beispiel wird die **path** -Eigenschaft eines Indikatorensatzes verwendet, um die formatierten Pfadnamen für die Leistungsindikatoren zu suchen.

Die Pipeline wird mit dem `Where-Object` Cmdlet verwendet, um eine Teilmenge der Pfadnamen zu suchen. Um nach einem Indikatorensatz eine komplette Liste von indikatorenpfaden zu suchen, entfernen Sie die Pipeline ( `|` ) und den `Where-Object` Befehl.

`$_`Ist eine automatische Variable für das aktuelle Objekt in der Pipeline.
Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

```powershell
(Get-Counter -ListSet Memory).Paths | Where-Object { $_ -like "*Cache*" }
```

```Output
\Memory\Cache Faults/sec
\Memory\Cache Bytes
\Memory\Cache Bytes Peak
\Memory\System Cache Resident Bytes
\Memory\Standby Cache Reserve Bytes
\Memory\Standby Cache Normal Priority Bytes
\Memory\Standby Cache Core Bytes
\Memory\Long-Term Average Standby Cache Lifetime (s)
```

`Get-Counter` verwendet den **listset** -Parameter, um den Arbeits **Speicher** -Counter Set anzugeben. Der Befehl wird in Klammern eingeschlossen, sodass die **Pfade** -Eigenschaft jeden Pfad als Zeichenfolge zurückgibt. Die Objekte werden über die Pipeline an gesendet `Where-Object` . `Where-Object`verwendet die `$_` -Variable, um jedes-Objekt zu verarbeiten, und verwendet den- `-like` Operator, um Übereinstimmungen für die Zeichenfolge `*Cache*` Die Sternchen ( `*` ) sind Platzhalter für beliebige Zeichen.

### Beispiel 9: Verwenden der pathswithinstance-Eigenschaft zum erhalten von formatierten Pfadnamen

In diesem Beispiel werden die Namen der formatierten Pfadnamen abgerufen, die die Instanzen für die Leistungsindikatoren " **PhysicalDisk** " enthalten.

```powershell
(Get-Counter -ListSet PhysicalDisk).PathsWithInstances
```

```Output
\PhysicalDisk(0 C:)\Current Disk Queue Length
\PhysicalDisk(_Total)\Current Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Time
\PhysicalDisk(_Total)\% Disk Time
\PhysicalDisk(0 C:)\Avg. Disk Queue Length
\PhysicalDisk(_Total)\Avg. Disk Queue Length
\PhysicalDisk(0 C:)\% Disk Read Time
\PhysicalDisk(_Total)\% Disk Read Time
```

`Get-Counter` verwendet den **listset** -Parameter, um den Indikators " **PhysicalDisk** " anzugeben. Der Befehl wird in Klammern eingeschlossen, sodass die **pathswithinstance** -Eigenschaft jede Pfad Instanz als Zeichenfolge zurückgibt.

### Beispiel 10: erhalten eines einzelnen Werts für jeden Leistungs Besatz in einem Leistungs Satz

In diesem Beispiel wird ein einzelner Wert für jeden Leistungs Besatz im Arbeits **Speicher** -Leistungs Satz des lokalen Computers zurückgegeben.

```powershell
$MemCounters = (Get-Counter -ListSet Memory).Paths
Get-Counter -Counter $MemCounters
```

```Output
Timestamp                 CounterSamples
---------                 --------------
6/19/2019 12:05:00        \\Computer01\memory\page faults/sec :
                          868.772077545597

                          \\Computer01\memory\available bytes :
                          9031176192

                          \\Computer01\memory\committed bytes :
                          8242982912

                          \\Computer01\memory\commit limit :
                          19603333120
```

`Get-Counter` verwendet den **listset** -Parameter, um den Arbeits **Speicher** -Counter Set anzugeben. Der Befehl wird in Klammern eingeschlossen, sodass die **Pfade** -Eigenschaft jeden Pfad als Zeichenfolge zurückgibt. Die Pfade werden in der `$MemCounters` Variablen gespeichert. `Get-Counter` verwendet den **Counter** -Parameter, um die Counter-Pfade in der `$MemCounters` Variablen anzugeben.

### Beispiel 11: Anzeigen der Eigenschaftswerte eines Objekts

Die Eigenschaftswerte im **PerformanceCounter Sample** -Objekt stellen die einzelnen Daten Beispiele dar. In diesem Beispiel verwenden wir die Eigenschaften des **Counter Samples** -Objekts, um die Daten zu überprüfen, auszuwählen, zu sortieren und zu gruppieren.

```powershell
$Counter = "\\Server01\Process(Idle)\% Processor Time"
$Data = Get-Counter $Counter
$Data.CounterSamples | Format-List -Property *
```

```Output
Path             : \\Server01\process(idle)\% processor time
InstanceName     : idle
CookedValue      : 198.467899571389
RawValue         : 14329160321003
SecondValue      : 128606459528326201
MultipleCount    : 1
CounterType      : Timer100Ns
Timestamp        : 6/19/2019 12:20:49
Timestamp100NSec : 128606207528320000
Status           : 0
DefaultScale     : 0
TimeBase         : 10000000
```

Der Counter-Pfad wird in der `$Counter` Variablen gespeichert. `Get-Counter` Ruft eine Stichprobe der Gegenwerte ab und speichert die Ergebnisse in der `$Data` Variablen. Die `$Data` -Variable verwendet die **Counter Samples** -Eigenschaft, um die Eigenschaften des Objekts zu erhalten. Das Objekt wird über die Pipeline an gesendet `Format-List` . Der **Property** -Parameter verwendet ein Sternchen-Platzhalter Zeichen ( `*` ), um alle Eigenschaften auszuwählen.

### Beispiel 12: Array Werte des Leistungs Zählers

In diesem Beispiel speichert eine Variable die einzelnen Leistungs Zählers. Die **Counter Samples** -Eigenschaft ist ein Array, das bestimmte Indikatorwerte anzeigen kann.

Verwenden Sie, um die einzelnen Counter-Beispiele anzuzeigen `$Counter.CounterSamples` .

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples[0]
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              1.33997091699662
```

`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert anzugeben `\Processor(*)\% Processor Time` . Die Werte werden in der `$Counter` Variablen gespeichert.
`$Counter.CounterSamples[0]` zeigt den Arraywert für den ersten Wert des Leistungs Zählers an.

### Beispiel 13: Vergleichen von Leistungs Zählers Werten

Dieses Beispiel ermittelt die Prozessorzeit, die von den einzelnen Prozessoren auf dem lokalen Computer verwendet wird. Die **Counter Samples** -Eigenschaft wird verwendet, um die Indikator Daten mit einem angegebenen Wert zu vergleichen.

Verwenden Sie, um die einzelnen Counter-Beispiele anzuzeigen `$Counter.CounterSamples` .

```powershell
$Counter = Get-Counter -Counter "\Processor(*)\% Processor Time"
$Counter.CounterSamples | Where-Object { $_.CookedValue -lt "20" }
```

```Output
Path                                         InstanceName        CookedValue
----                                         ------------        -----------
\\Computer01\processor(0)\% processor time   0              12.6398025240208
\\Computer01\processor(1)\% processor time   1              15.7598095767344
```

`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert anzugeben `\Processor(*)\% Processor Time` . Die Werte werden in der `$Counter` Variablen gespeichert. Die in gespeicherten Objekte `$Counter.CounterSamples` werden über die Pipeline gesendet. `Where-Object` verwendet einen Skriptblock, um jeden Objektwert mit einem angegebenen Wert von 20 zu vergleichen. Der `$_.CookedValue` ist eine Variable für das aktuelle Objekt in der Pipeline. Leistungsindikatoren mit einem **cookedvalue** , der kleiner als 20 ist, werden angezeigt.

### Beispiel 14: Sortieren von Leistungsdaten des Leistungs Zählers

In diesem Beispiel wird gezeigt, wie Leistungs Leistungsdaten sortiert werden. In diesem Beispiel werden die Prozesse auf dem Computer gefunden, die die meiste Prozessorzeit im Beispiel verwenden.

```powershell
$Procs = Get-Counter -Counter "\Process(*)\% Processor Time"
$Procs.CounterSamples | Sort-Object -Property CookedValue -Descending |
   Format-Table -Property Path, InstanceName, CookedValue -AutoSize
```

```Output
Path                                                         InstanceName             CookedValue
----                                                         ------------             -----------
\\Computer01\process(_total)\% processor time                _total              395.464129650573
\\Computer01\process(idle)\% processor time                  idle                389.356575524695
\\Computer01\process(mssense)\% processor time               mssense             3.05377706293879
\\Computer01\process(csrss#1)\% processor time               csrss               1.52688853146939
\\Computer01\process(microsoftedgecp#10)\% processor time    microsoftedgecp     1.52688853146939
\\Computer01\process(runtimebroker#5)\% processor time       runtimebroker                      0
\\Computer01\process(settingsynchost)\% processor time       settingsynchost                    0
\\Computer01\process(microsoftedgecp#16)\% processor time    microsoftedgecp                    0
```

`Get-Counter` verwendet den **Counter** -Parameter, um den-Wert `\Process(*)\% Processor Time` für alle Prozesse auf dem lokalen Computer anzugeben. Das Ergebnis wird in der `$Procs` Variablen gespeichert. Die `$Procs` Variable mit der **Counter Samples** -Eigenschaft sendet die **PerformanceCounter Sample** -Objekte über die Pipeline. `Sort-Object` verwendet den **Property** -Parameter, um die Objekte nach **cookedvalue** in **absteigender** Reihenfolge zu sortieren. `Format-Table` verwendet den **Property** -Parameter, um die Spalten für die Ausgabe auszuwählen. Der **AutoSize** -Parameter passt die Spaltenbreite an, um das Abschneiden zu minimieren.

## PARAMETERS

### -ComputerName

Gibt einen Computernamen oder ein durch Trennzeichen getrenntes Array von **Remote** Computernamen an. Verwenden Sie den NetBIOS-Namen, eine IP-Adresse oder den voll qualifizierten Domänen Namen des Computers.

Um Leistungsdaten vom **lokalen** Computer zu erhalten, schließen Sie den **Computername** -Parameter aus.
Bei Ausgaben wie z. b. einem **listset** , das die **MachineName** -Spalte enthält, gibt ein Punkt ( `.` ) den lokalen Computer an.

`Get-Counter` beruht nicht auf PowerShell-Remoting. Sie können den **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Continuous

Wenn **Continuous** angegeben wird, werden `Get-Counter` Stichproben abgerufen, bis Sie <kbd>STRG</kbd> + <kbd>C</kbd>drücken. Stichproben werden pro Sekunde für jeden angegebenen Leistungswert abgerufen. Verwenden Sie den Parameter **sampleingeterval** , um das Intervall zwischen kontinuierlichen Stichproben zu erhöhen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Counter

Gibt den Pfad zu einem oder mehreren-gegen Pfaden an. Pfade sind Eingabe als durch Trennzeichen getrennte Arrays, Variablen oder Werte aus einer Textdatei. Sie können die Zeichen folgen für den Counter-Pfad über die Pipeline an senden `Get-Counter` .

Gegen Pfade verwenden die folgende Syntax:

`\\ComputerName\CounterSet(Instance)\CounterName`

`\CounterSet(Instance)\CounterName`

Beispiel:

`\\Server01\Processor(*)\% User Time`

`\Processor(*)\% User Time`

Der `\\ComputerName` ist in einem Leistungsdaten Wert Pfad optional. Wenn der Computername nicht in den-kontonfad eingeschlossen ist, wird von `Get-Counter` der lokale Computer verwendet.

Ein Sternchen ( `*` ) in der-Instanz ist ein Platzhalter Zeichen, um alle Instanzen des Zählers zu erhalten.

```yaml
Type: System.String[]
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Listset

Listet die Leistungs Indikatorensätze auf den Computern auf. Verwenden Sie ein Sternchen ( `*` ), um alle Indikatorensätze anzugeben. Geben Sie einen Namen oder eine durch Trennzeichen getrennte Zeichenfolge von Counter-Set-Namen ein. Sie können die Namen von Counter-Sets an die Pipeline senden.

Verwenden Sie den **listset** -Parameter, um einen Indikatorensatz für formatierte indikatorenpfade zu erhalten. Die **path** -und **pathswithinstance** -Eigenschaften der einzelnen Zählungen enthalten die einzelnen, als Zeichen folgen formatierten Counter-Pfade.

Sie können die Zeichen folgen für den Counter-Pfad in einer Variablen speichern oder die Pipeline verwenden, um die Zeichenfolge an einen anderen Befehl zu senden `Get-Counter` .

So senden Sie z. b. jeden **Prozessor** -Counter-Pfad an `Get-Counter` :

`Get-Counter -ListSet Processor | Get-Counter`

> [!NOTE]
> In PowerShell 7 `Get-Counter` kann die **Description** -Eigenschaft des Counter Sets nicht abrufen. Die **Beschreibung** ist auf festgelegt `$null` .

```yaml
Type: System.String[]
Parameter Sets: ListSetSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -Maxsamples

Gibt die Anzahl der Stichproben an, die aus den einzelnen angegebenen Leistungs Zählers entnommen werden. Um einen konstanten Datenstrom von Beispielen zu erhalten, verwenden Sie den **Continuous** -Parameter.

Wenn der Parameter " **maxsamples** " nicht angegeben wird, ruft `Get-Counter` nur ein Beispiel für jeden angegebenen Zählers ab.

Um ein großes Dataset zu erfassen, führen Sie `Get-Counter` als PowerShell-Hintergrund Auftrag aus. Weitere Informationen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).

```yaml
Type: System.Int64
Parameter Sets: GetCounterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sampleinterval

Gibt die Anzahl der Sekunden zwischen den Stichproben für die einzelnen angegebenen Leistungs Zählers an. Wenn der Parameter " **sampleinterval** " nicht angegeben wird, `Get-Counter` verwendet ein Intervall von einer Sekunde.

```yaml
Type: System.Int32
Parameter Sets: GetCounterSet
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

### System.String[]

`Get-Counter` akzeptiert Pipeline Eingaben für die Anzahl von Pfaden und Namen von Counter-Sets.

## AUSGABEN

### Microsoft. PowerShell. Commands. getcounter. CounterSet, Microsoft. PowerShell. Commands. getcounter. performancecountersampleset, Microsoft. PowerShell. Commands. getcounter. Performance Counter Sample

Um die Eigenschaften eines Objekts anzuzeigen, senden Sie die Ausgabe über die Pipeline an `Get-Member` . Die Objekttypen, die ausgegeben werden, lauten wie folgt:

**Listset** -Parameter: **Microsoft. PowerShell. Commands. getcounter. CounterSet**

**Counter** -Parameter: **Microsoft. PowerShell. Commands. getcounter. performancecountersampleset**

**Counter Samples** -Eigenschaft: **Microsoft. PowerShell. Commands. getcounter. Performance Counter Sample**

## HINWEISE

Wenn keine Parameter angegeben werden, `Get-Counter` wird ein Beispiel für jeden angegebenen Leistungs Bewert abgerufen. Verwenden Sie die Parameter **maxsamples** und **Continuous** , um weitere Beispiele zu erhalten.

`Get-Counter` verwendet ein Intervall von einer Sekunde zwischen Stichproben. Verwenden Sie den **sampleingeterval** -Parameter, um das Intervall zu erhöhen.

Die Werte **maxsamples** und **sampleinterval** gelten für alle Indikatoren auf den einzelnen Computern im Befehl. Wenn Sie unterschiedliche Werte für verschiedene Leistungsindikatoren festlegen möchten, geben Sie separate `Get-Counter` Befehle ein.

Wenn Sie in PowerShell 7 den **listset** -Parameter verwenden, `Get-Counter` kann die **Description** -Eigenschaft des Counter Sets nicht abrufen. Die **Beschreibung** ist auf festgelegt `$null` .

## VERWANDTE LINKS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md)

[Format-List](../Microsoft.PowerShell.Utility/Format-List.md)

[Format-Table](../Microsoft.PowerShell.Utility/Format-Table.md)

[Get-Member](../Microsoft.PowerShell.Utility/Get-Member.md)

[Receive-Job](../Microsoft.PowerShell.Core/Receive-Job.md)

[Start-Job](../Microsoft.PowerShell.Core/Start-Job.md)

[Where-Object](..//Microsoft.PowerShell.Core/Where-Object.md)

