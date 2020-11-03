---
external help file: Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Diagnostics
ms.date: 11/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.diagnostics/get-winevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WinEvent
ms.openlocfilehash: a35fe7d46773f8d20ed0ca40ea856a0e9619a2b5
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209823"
---
# Get-WinEvent

## ZUSAMMENFASSUNG
Es ruft Ereignisse aus Ereignisprotokollen und Ereignisablaufverfolgung-Protokolldateien auf lokalen Computern und Remotecomputern ab.

## SYNTAX

### Getlogset (Standard)

```
Get-WinEvent [[-LogName] <String[]>] [-MaxEvents <Int64>] [-ComputerName <String>]
 [-Credential <PSCredential>] [-FilterXPath <String>] [-Force] [-Oldest] [<CommonParameters>]
```

### Listlogset

```
Get-WinEvent [-ListLog] <String[]> [-ComputerName <String>] [-Credential <PSCredential>] [-Force]
 [<CommonParameters>]
```

### Listproviderset

```
Get-WinEvent [-ListProvider] <String[]> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### Getproviderset

```
Get-WinEvent [-ProviderName] <String[]> [-MaxEvents <Int64>] [-ComputerName <String>]
 [-Credential <PSCredential>] [-FilterXPath <String>] [-Force] [-Oldest] [<CommonParameters>]
```

### Fileset

```
Get-WinEvent [-Path] <String[]> [-MaxEvents <Int64>] [-Credential <PSCredential>]
 [-FilterXPath <String>] [-Oldest] [<CommonParameters>]
```

### Hashqueryset

```
Get-WinEvent [-MaxEvents <Int64>] [-ComputerName <String>] [-Credential <PSCredential>]
 [-FilterHashtable] <Hashtable[]> [-Force] [-Oldest] [<CommonParameters>]
```

### Xmlqueryset

```
Get-WinEvent [-MaxEvents <Int64>] [-ComputerName <String>] [-Credential <PSCredential>]
 [-FilterXml] <XmlDocument> [-Oldest] [<CommonParameters>]
```

## DESCRIPTION

`Get-WinEvent`Mit dem-Cmdlet werden Ereignisse aus Ereignisprotokollen abgerufen, einschließlich klassischer Protokolle, z. b. der **System** -und **Anwendungs** Protokolle. Mit dem-Cmdlet werden Daten aus Ereignisprotokollen abgerufen, die von der in Windows Vista eingeführten Windows-Ereignisprotokoll Technologie generiert werden. Und Ereignisse in Protokolldateien, die von der **Ereignis Ablauf Verfolgung für Windows (ETW)** generiert werden. Standardmäßig `Get-WinEvent` gibt Ereignis Informationen in der Reihenfolge von "Latest" in "Latest" zurück.

`Get-WinEvent` Listet Ereignisprotokolle und Ereignisprotokoll Anbieter auf. Drücken Sie <kbd>STRG</kbd>C, um den Befehl zu unterbrechen + <kbd>C</kbd>. Sie können Ereignisse aus ausgewählten Protokollen oder aus von Ereignisanbietern generierten Protokollen abrufen. Und Sie können Ereignisse aus mehreren Quellen in einem einzelnen Befehl kombinieren.
`Get-WinEvent` ermöglicht das Filtern von Ereignissen mithilfe von XPath-Abfragen, strukturierten XML-Abfragen und Hash Tabellen Abfragen.

Wenn Sie PowerShell nicht als Administrator ausführen, werden möglicherweise Fehlermeldungen angezeigt, dass Sie keine Informationen zu einem Protokoll abrufen können.

## BEISPIELE

### Beispiel 1: alle Protokolle von einem lokalen Computer

Mit diesem Befehl werden alle Ereignisprotokolle auf dem lokalen Computer abgerufen. Die Protokolle werden in der Reihenfolge aufgelistet, in der Sie abgerufen werden `Get-WinEvent` . Klassische Protokolle werden zuerst abgerufen, gefolgt von den neuen Windows-Ereignisprotokollen.
Es ist möglich, dass der **RecordCount** eines Protokolls NULL (leer) oder 0 (null) ist.

```powershell
Get-WinEvent -ListLog *
```

```Output
LogMode   MaximumSizeInBytes RecordCount LogName
-------   ------------------ ----------- -------
Circular            15532032       14500 Application
Circular             1052672         117 Azure Information Protection
Circular             1052672        3015 CxAudioSvcLog
Circular            20971520             ForwardedEvents
Circular            20971520           0 HardwareEvents
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen vom Computer abgerufen. Der **listlog** -Parameter verwendet das Sternchen-Platzhalter Zeichen ( `*` ), um Informationen zu den einzelnen Protokollen anzuzeigen.

### Beispiel 2: Get the Classic Setup Log

Mit diesem Befehl wird ein **EventLogConfiguration** -Objekt abgerufen, das das klassische **Setup** Protokoll darstellt. Das-Objekt enthält Informationen zum Protokoll, z. b. Dateigröße, Anbieter, Dateipfad und gibt an, ob das Protokoll aktiviert ist.

```powershell
Get-WinEvent -ListLog Setup | Format-List -Property *
```

```Output
FileSize                       : 69632
IsLogFull                      : False
LastAccessTime                 : 3/13/2019 09:41:46
LastWriteTime                  : 3/13/2019 09:41:46
OldestRecordNumber             : 1
RecordCount                    : 23
LogName                        : Setup
LogType                        : Operational
LogIsolation                   : Application
IsEnabled                      : True
IsClassicLog                   : False
SecurityDescriptor             : O:BAG:SYD: ...
LogFilePath                    : %SystemRoot%\System32\Winevt\Logs\Setup.evtx
MaximumSizeInBytes             : 1052672
LogMode                        : Circular
OwningProviderName             : Microsoft-Windows-Eventlog
ProviderNames                  : {Microsoft-Windows-WUSA, Microsoft-Windows-ActionQueue...
ProviderLevel                  :
ProviderKeywords               :
ProviderBufferSize             : 64
ProviderMinimumNumberOfBuffers : 0
ProviderMaximumNumberOfBuffers : 64
ProviderLatency                : 1000
ProviderControlGuid            :
```

Das- `Get-WinEvent` Cmdlet verwendet den **listlog** -Parameter, um das **Setup** Protokoll anzugeben. Das Objekt wird über die Pipeline an das `Format-List` Cmdlet gesendet. `Format-List` verwendet den **Property** -Parameter mit dem Platzhalter Sternchen ( `*` ), um die einzelnen Eigenschaften anzuzeigen.

### Beispiel 3: erhalten von Ereignisprotokollen von einem Server

Mit diesem Befehl werden nur Ereignisprotokolle auf dem lokalen Computer abgerufen, die Ereignisse enthalten. Es ist möglich, dass das **RecordCount** eines Protokolls NULL oder NULL ist. Im Beispiel wird die- `$_` Variable verwendet. Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/about/about_automatic_variables.md).

```powershell
Get-WinEvent -ListLog * -ComputerName localhost | Where-Object { $_.RecordCount }
```

```Output
LogMode   MaximumSizeInBytes RecordCount LogName
-------   ------------------ ----------- -------
Circular            15532032       14546 Application
Circular             1052672         117 Azure Information Protection
Circular             1052672        2990 CxAudioSvcLog
Circular             1052672           9 MSFTVPN Setup
Circular             1052672         282 OAlerts
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen vom Computer abgerufen. Der **listlog** -Parameter verwendet das Sternchen-Platzhalter Zeichen ( `*` ), um Informationen zu den einzelnen Protokollen anzuzeigen. Der **Computername** -Parameter gibt an, dass die Protokolle vom lokalen Computer **localhost** angezeigt werden. Die Objekte werden über die Pipeline an das `Where-Object` Cmdlet gesendet. `Where-Object` verwendet `$_.RecordCount` , um nur Protokolle zurückzugeben, die-Daten enthalten. `$_` eine Variable, die das aktuelle Objekt in der Pipeline darstellt. **RecordCount** ist eine Eigenschaft des Objekts mit einem Wert ungleich NULL.

### Beispiel 4: erhalten von Ereignisprotokollen von mehreren Servern

In diesem Beispiel werden Objekte abgerufen, die die **Anwendungs** Ereignisprotokolle auf drei Computern darstellen: Server01, Server02 und Server03. Das Schlüsselwort " **foreach** " wird verwendet, da der **Computername** -Parameter nur einen Wert akzeptiert. Weitere Informationen finden Sie unter [about_Foreach](../Microsoft.PowerShell.Core/about/about_Foreach.md).

```powershell
$S = 'Server01', 'Server02', 'Server03'
ForEach ($Server in $S) {
  Get-WinEvent -ListLog Application -ComputerName $Server |
    Select-Object LogMode, MaximumSizeInBytes, RecordCount, LogName,
      @{name='ComputerName'; expression={$Server}} |
    Format-Table -AutoSize
}
```

```Output
 LogMode MaximumSizeInBytes RecordCount LogName     ComputerName
 ------- ------------------ ----------- -------     ------------
Circular           15532032       14577 Application Server01
Circular           15532032        9689 Application Server02
Circular           15532032        5309 Application Server03
```

Die-Variable `$S` speichert die Namen von drei Servern: **Server01** , **Server02** und **Server03** . Die **foreach** -Anweisung verwendet eine-Schleife, um jeden Server zu verarbeiten `($Server in $S)` . Der Skriptblock in den geschweiften Klammern ( `{ }` ) führt den `Get-WinEvent` Befehl aus. Der **listlog** -Parameter gibt das **Anwendungs** Protokoll an. Der **Computername** -Parameter verwendet die-Variable `$Server` , um Protokollinformationen von jedem Server zu erhalten.

Die Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet. `Select-Object` Ruft die Eigenschaften **Logmode** , **maximumsizeinbytes** , **RecordCount** , **logName** ab und verwendet einen berechneten Ausdruck, um den **Computernamen** mithilfe der `$Server` Variablen anzuzeigen. Die Objekte werden über die Pipeline an das `Format-Table` Cmdlet gesendet, um die Ausgabe in der PowerShell-Konsole anzuzeigen. Der **AutoSize** -Parameter formatiert die Ausgabe an den Bildschirm.

### Beispiel 5: erhalten von Ereignisprotokoll Anbietern und Protokollnamen

Dieser Befehl ruft die Ereignisprotokoll Anbieter und die Protokolle ab, in die Sie schreiben.

```powershell
Get-WinEvent -ListProvider *
```

```Output
Name     : .NET Runtime
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}

Name     : .NET Runtime Optimization Service
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen vom Computer abgerufen. Der **listprovider** -Parameter verwendet das Sternchen-Platzhalter Zeichen ( `*` ), um Informationen zu den einzelnen Anbietern anzuzeigen. In der Ausgabe ist der **Name** der Anbieter, und **loglinks** ist das Protokoll, in das der Anbieter schreibt.

### Beispiel 6: alle Ereignisprotokoll Anbieter, die in ein bestimmtes Protokoll schreiben

Dieser Befehl ruft alle Anbieter ab, die in das **Anwendungs** Protokoll schreiben.

```powershell
(Get-WinEvent -ListLog Application).ProviderNames
```

```Output
.NET Runtime
.NET Runtime Optimization Service
Application
Application Error
Application Hang
Application Management
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen vom Computer abgerufen. Der **listlog** -Parameter verwendet die- **Anwendung** , um-Objekte für dieses Protokoll zu erhalten. **Providernames** ist eine Eigenschaft des Objekts und zeigt die Anbieter an, die in das **Anwendungs** Protokoll schreiben.

### Beispiel 7: Get-Ereignisprotokoll-Anbieter Namen, die eine bestimmte Zeichenfolge enthalten

Mit diesem Befehl werden die Ereignisprotokoll Anbieter mit Namen abgerufen, die eine bestimmte Zeichenfolge im Namen des Anbieters enthalten.

```powershell
Get-WinEvent -ListProvider *Policy*
```

```Output
Name     : Group Policy Applications
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}

Name     : Group Policy Client
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}

Name     : Group Policy Data Sources
LogLinks : {Application}
Opcodes  : {}
Tasks    : {}
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen vom Computer abgerufen. Der **listprovider** -Parameter verwendet das Sternchen-Platzhalter Zeichen ( `*` ), um eine **Richtlinie** innerhalb des Anbieter namens zu suchen.

### Beispiel 8: erhalten von Ereignis-IDs, die vom Ereignis Anbieter generiert werden

Dieser Befehl listet die Ereignis-IDs auf, die der **Microsoft-Windows-GroupPolicy-** Ereignis Anbieter generiert, zusammen mit der Ereignis Beschreibung.

```powershell
(Get-WinEvent -ListProvider Microsoft-Windows-GroupPolicy).Events | Format-Table Id, Description
```

```Output
  Id  Description
  --  -----------
1500  The Group Policy settings for the computer were processed successfully...
1501  The Group Policy settings for the user were processed successfully...
4115  Group Policy Service started.
4116  Started the Group Policy service initialization phase.
4117  Group Policy Session started.
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen vom Computer abgerufen. Der Parameter " **listprovider** " gibt den Anbieter " **Microsoft-Windows-GroupPolicy** " an. Der Ausdruck wird in Runde Klammern eingeschlossen und verwendet die **Events** -Eigenschaft, um Objekte zu erhalten. Die Objekte werden über die Pipeline an das `Format-Table` Cmdlet gesendet. `Format-Table` zeigt die **ID** und **Beschreibung** der Ereignis Objekte an.

### Beispiel 9: erhalten von Protokollinformationen von Ereignis Objekteigenschaften

Dieses Beispiel zeigt, wie Sie Informationen über die Inhalte eines Protokolls mithilfe von Ereignis Objekteigenschaften erhalten.
Ereignis Objekte werden in einer Variablen gespeichert und dann gruppiert und nach **Ereignis-ID** und **Ebene** gezählt.

```powershell
$Event = Get-WinEvent -LogName 'Windows PowerShell'
$Event.Count
$Event | Group-Object -Property Id -NoElement | Sort-Object -Property Count -Descending
$Event | Group-Object -Property LevelDisplayName -NoElement
```

```Output
195

Count  Name
-----  ----
  147  600
   22  400
   21  601
    3  403
    2  103

Count  Name
-----  ----
    2  Warning
  193  Information
```

Das `Get-WinEvent` Cmdlet verwendet den **logName** -Parameter, um das **Windows PowerShell** -Ereignisprotokoll anzugeben. Die Ereignis Objekte werden in der `$Event` Variablen gespeichert. Die **count** -Eigenschaft von `$Event` zeigt die Gesamtzahl der protokollierten Ereignisse an.

Die `$Event` Variable wird an das Cmdlet über die Pipeline gesendet `Group-Object` . `Group-Object` verwendet den **Property** -Parameter, um die **ID** -Eigenschaft anzugeben und die Objekte nach dem Wert der Ereignis-ID zu zählen. Der **noelement** -Parameter entfernt andere Eigenschaften aus der Ausgabe der Objekte. Die gruppierten Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet. `Sort-Object` verwendet den **Property** -Parameter, um die Objekte nach **Anzahl** zu sortieren. Der **Absteig** Ende Parameter zeigt die Ausgabe nach Anzahl (von der höchsten zum niedrigsten) an. In der Ausgabe enthält die Spalte " **count** " die Gesamtzahl der einzelnen Ereignisse. Die Spalte **Name** enthält die gruppierten Ereignis-ID-Nummern.

Die `$Event` Variable wird an das Cmdlet über die Pipeline gesendet `Group-Object` . `Group-Object` verwendet den **Property** -Parameter, um die **leveldisplayname** -Eigenschaft anzugeben, und zählt die Objekte nach **leveldisplayname** . Die Objekte werden nach den Ebenen gruppiert, wie z. b. **Warnung** und **Information** .
Der **noelement** -Parameter entfernt andere Eigenschaften aus der Ausgabe. In der Ausgabe enthält die Spalte " **count** " die Gesamtzahl der einzelnen Ereignisse. Die Spalte **Name** enthält den gruppierten **leveldisplay Name** .

### Beispiel 10: erhalten von Fehlerereignissen, deren Name eine angegebene Zeichenfolge ist

Dieses Beispiel verwendet eine durch Trennzeichen getrennte Zeichenfolge von Protokollnamen. Die Ausgabe wird nach der Ebene gruppiert, wie z. b. Fehler oder Warnung und der Protokoll Name.

```powershell
Get-WinEvent -LogName *PowerShell*, Microsoft-Windows-Kernel-WHEA* |
  Group-Object -Property LevelDisplayName, LogName -NoElement |
    Format-Table -AutoSize
```

```Output
Count  Name
-----  ----
    1  Error, PowerShellCore/Operational
   26  Information, Microsoft-Windows-Kernel-WHEA/Operational
  488  Information, Microsoft-Windows-PowerShell/Operational
   77  Information, PowerShellCore/Operational
 9835  Information, Windows PowerShell
   19  Verbose, PowerShellCore/Operational
  444  Warning, Microsoft-Windows-PowerShell/Operational
  512  Warning, PowerShellCore/Operational
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen vom Computer abgerufen. Der **logName** -Parameter verwendet eine durch Kommas getrennte Zeichenfolge mit dem Platzhalter Sternchen ( `*` ), um die Protokollnamen anzugeben. Die Objekte werden über die Pipeline an das `Group-Object` Cmdlet gesendet. `Group-Object` verwendet den **Property** -Parameter, um die Objekte nach **leveldisplayname** und **logName** zu gruppieren. Der **noelement** -Parameter entfernt andere Eigenschaften aus der Ausgabe. Die gruppierten Objekte werden über die Pipeline an das `Format-Table` Cmdlet gesendet. `Format-Table` verwendet den **AutoSize** -Parameter, um die Spalten zu formatieren. Die **count** -Spalte enthält die Gesamtzahl der einzelnen Ereignisse. Die Spalte **Name** enthält die gruppierten **leveldisplayname** und **logName** .

### Beispiel 11: Ereignisse aus einem archivierten Ereignisprotokoll

`Get-WinEvent` kann Ereignis Informationen aus gespeicherten Protokolldateien erhalten. In diesem Beispiel wird ein archiviertes PowerShell-Protokoll verwendet, das auf dem lokalen Computer gespeichert ist.

```powershell
Get-WinEvent -Path 'C:\Test\Windows PowerShell.evtx'
```

```Output
   ProviderName: PowerShell

TimeCreated              Id LevelDisplayName  Message
-----------              -- ----------------  -------
3/15/2019 13:54:13      403 Information       Engine state is changed from Available to Stopped...
3/15/2019 13:54:13      400 Information       Engine state is changed from None to Available...
3/15/2019 13:54:13      600 Information       Provider "Variable" is Started...
3/15/2019 13:54:13      600 Information       Provider "Function" is Started...
3/15/2019 13:54:13      600 Information       Provider "FileSystem" is Started...
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen vom Computer abgerufen. Der **path** -Parameter gibt das Verzeichnis und den Dateinamen an.

### Beispiel 12: erhalten einer bestimmten Anzahl von Ereignissen aus einem archivierten Ereignisprotokoll

Diese Befehle erhalten eine bestimmte Anzahl von Ereignissen aus einem archivierten Ereignisprotokoll. `Get-WinEvent` verfügt über Parameter, die eine maximale Anzahl von Ereignissen oder die ältesten Ereignisse erhalten können. In diesem Beispiel wird ein archiviertes PowerShell-Protokoll verwendet, das in " **c:\test\powershellcore Operational. evtx** " gespeichert ist.

```powershell
Get-WinEvent -Path 'C:\Test\PowerShellCore Operational.evtx' -MaxEvents 100
```

```Output
   ProviderName: PowerShellCore

TimeCreated                 Id   LevelDisplayName  Message
-----------                 --   ----------------  -------
3/15/2019 09:54:54        4104   Warning           Creating Scriptblock text (1 of 1):...
3/15/2019 09:37:13       40962   Information       PowerShell console is ready for user input
3/15/2019 07:56:24        4104   Warning           Creating Scriptblock text (1 of 1):...
...
3/7/2019 10:53:22        40961   Information       PowerShell console is starting up
3/7/2019 10:53:22         8197   Verbose           Runspace state changed to Opening
3/7/2019 10:53:22         8195   Verbose           Opening RunspacePool
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen vom Computer abgerufen. Der **path** -Parameter gibt das Verzeichnis und den Dateinamen an. Der **maxevents** -Parameter gibt an, dass 100 Datensätze angezeigt werden, von der neuesten zum ältesten.

### Beispiel 13: Ereignis Ablauf Verfolgung für Windows

Die Ereignis Ablauf Verfolgung für Windows (ETW) schreibt Ereignisse in das Protokoll, wenn Ereignisse auftreten. Die Ereignisse werden in der Reihenfolge der ältesten in der neuesten Reihenfolge gespeichert. Eine archivierte etw-Datei wird als ( `.etl` z. b. " **tracelog. ETL** ") gespeichert.
Die Ereignisse werden in der Reihenfolge aufgelistet, in der Sie in das Protokoll geschrieben werden, sodass der *älteste* Parameter erforderlich ist.

```powershell
Get-WinEvent -Path 'C:\Tracing\TraceLog.etl' -Oldest |
  Sort-Object -Property TimeCreated -Descending |
    Select-Object -First 100
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen aus der archivierten Datei abgerufen. Der **path** -Parameter gibt das Verzeichnis und den Dateinamen an. Der **älteste** Parameter wird zum Ausgeben von Ereignissen in der Reihenfolge verwendet, in der Sie geschrieben werden. Die Objekte werden über die Pipeline an das `Sort-Object` Cmdlet gesendet und `Sort-Object` sortiert die Objekte in absteigender Reihenfolge nach dem Wert der **TimeCreated** -Eigenschaft. Die Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet, das die neuesten 100-Ereignisse anzeigt.

### Beispiel 14: Ereignisse aus einem Ereignis Ablauf Verfolgungs Protokoll

Dieses Beispiel zeigt, wie Sie die Ereignisse aus einer Ereignis Ablauf Verfolgungs Protokoll-Datei ( `.etl` ) und einer archivierten Windows PowerShell-Protokolldatei ( `.evtx` ) erhalten. Sie können mehrere Dateitypen in einem einzigen Befehl kombinieren.
Da die Dateien denselben Typ **.NET Framework** Objekts ( **EventLogRecord** ) enthalten, können Sie Sie mit denselben Eigenschaften filtern. Der Befehl erfordert den **ältesten** Parameter, da er aus einer `.etl` Datei liest, aber der **älteste** Parameter gilt für jede Datei.

```powershell
Get-WinEvent -Path 'C:\Tracing\TraceLog.etl', 'C:\Test\Windows PowerShell.evtx' -Oldest |
  Where-Object { $_.Id -eq '403' }
```

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen aus den archivierten Dateien abgerufen. Der **path** -Parameter verwendet eine durch Trennzeichen getrennte Liste, um jedes Datei Verzeichnis und den Dateinamen anzugeben. Der **älteste** Parameter wird zum Ausgeben von Ereignissen in der Reihenfolge verwendet, in der Sie geschrieben werden. Die Objekte werden über die Pipeline an das `Where-Object` Cmdlet gesendet. `Where-Object` verwendet einen Skriptblock, um nach Ereignissen mit und der **ID** **403** zu suchen. Die `$_` -Variable stellt das aktuelle Objekt in der Pipeline dar, und **ID** ist die Ereignis-ID-Eigenschaft.

### Beispiel 15: Filtern der Ergebnisse von Ereignisprotokollen

Dieses Beispiel zeigt eine Vielzahl von Methoden zum Filtern und Auswählen von Ereignissen aus einem Ereignisprotokoll. Alle diese Befehle erhalten Ereignisse, die in den letzten 24 Stunden aus dem **Windows PowerShell** -Ereignisprotokoll aufgetreten sind.
Die Filter Methoden sind effizienter als die Verwendung des- `Where-Object` Cmdlets. Filter werden beim Abrufen der Objekte angewendet. `Where-Object` Ruft alle-Objekte ab und wendet dann Filter auf alle-Objekte an.

```powershell
# Using the Where-Object cmdlet:
$Yesterday = (Get-Date) - (New-TimeSpan -Day 1)
Get-WinEvent -LogName 'Windows PowerShell' | Where-Object { $_.TimeCreated -ge $Yesterday }

# Using the FilterHashtable parameter:
$Yesterday = (Get-Date) - (New-TimeSpan -Day 1)
Get-WinEvent -FilterHashtable @{ LogName='Windows PowerShell'; Level=3; StartTime=$Yesterday }

# Using the FilterXML parameter:
$xmlQuery = @'
<QueryList>
  <Query Id="0" Path="Windows PowerShell">
    <Select Path="System">*[System[(Level=3) and
        TimeCreated[timediff(@SystemTime) &lt;= 86400000]]]</Select>
  </Query>
</QueryList>
'@
Get-WinEvent -FilterXML $xmlQuery

# Using the FilterXPath parameter:
$XPath = '*[System[Level=3 and TimeCreated[timediff(@SystemTime) &lt;= 86400000]]]'
Get-WinEvent -LogName 'Windows PowerShell' -FilterXPath $XPath
```

### Beispiel 16: Verwenden von "filterhashtable" zum erhalten von Ereignissen aus dem Anwendungsprotokoll

In diesem Beispiel wird der **filterhashtable** -Parameter verwendet, um Ereignisse aus dem **Anwendungs** Protokoll zu erhalten. Die Hash Tabelle verwendet **Schlüssel-Wert-** Paare. Weitere Informationen zum **filterhashtable** -Parameter finden Sie unter [Erstellen von Get-WinEvent-Abfragen mit filterhashtable](/powershell/scripting/samples/Creating-Get-WinEvent-queries-with-FilterHashtable).
Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/about/about_hash_tables.md) (Informationen zu Hashtabellen).

```powershell
$Date = (Get-Date).AddDays(-2)
Get-WinEvent -FilterHashtable @{ LogName='Application'; StartTime=$Date; Id='1003' }
```

Das `Get-Date` Cmdlet verwendet die **addDays** -Methode, um ein Datum zu erhalten, das zwei Tage vor dem aktuellen Datum liegt. Das Date-Objekt wird in der- `$Date` Variable gespeichert.

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen abgerufen. Der **filterhashtable** -Parameter wird verwendet, um die Ausgabe zu filtern. Der Schlüssel **logName** gibt den Wert als **Anwendungs** Protokoll an. Der **StartTime** -Schlüssel verwendet den Wert, der in der Variablen gespeichert ist `$Date` . Der **ID** -Schlüssel verwendet den Ereignis-ID-Wert **1003** .

### Beispiel 17: Verwenden von "filterhashtable" zum erhalten von Anwendungsfehlern

In diesem Beispiel wird der **filterhashtable** -Parameter verwendet, um Internet Explorer-Anwendungsfehler zu suchen, die innerhalb der letzten Woche aufgetreten sind.

```powershell
$StartTime = (Get-Date).AddDays(-7)
Get-WinEvent -FilterHashtable @{
  Logname='Application'
  ProviderName='Application Error'
  Data='iexplore.exe'
  StartTime=$StartTime
}
```

Das `Get-Date` Cmdlet verwendet die **addDays** -Methode, um ein Datum zu erhalten, das sieben Tage vor dem aktuellen Datum liegt. Das Date-Objekt wird in der- `$StartTime` Variable gespeichert.

Mit dem- `Get-WinEvent` Cmdlet werden Protokollinformationen abgerufen. Der **filterhashtable** -Parameter wird verwendet, um die Ausgabe zu filtern. Der Schlüssel **logName** gibt den Wert als **Anwendungs** Protokoll an. Der **providerName** -Schlüssel verwendet den Wert **Anwendungsfehler** , bei dem es sich um die **Quelle** des Ereignisses handelt. Der **Daten** Schlüssel verwendet den Wert **iexplore.exe** der **StartTime** -Schlüssel verwendet den Wert, der in der Variablen gespeichert ist `$StartTime` .

### Beispiel 18: Verwenden von suppresshashfilter zum Filtern von Anwendungsfehlern

Beispielsweise wird in diesem Beispiel der **filterhashtable** -Parameter verwendet, um Ereignisse aus dem **Anwendungs** Protokoll zu erhalten. Wir fügen jedoch den Schlüssel **suppresshashfilter** hinzu, um Ereignisse auf **Informations** Ebene herauszufiltern.

```powershell
$Date = (Get-Date).AddDays(-2)
$filter = @{
  LogName='Application'
  StartTime=$Date
  SuppressHashFilter=@{Level=4}
}
Get-WinEvent -FilterHashtable $filter
```

In diesem Beispiel ruft `Get-WinEvent` alle Ereignisse aus dem **Anwendungs** Protokoll der letzten zwei Tage ab, mit Ausnahme derjenigen, die die **Ebene** 4 (Informationen) aufweisen.

## PARAMETERS

### -ComputerName

Gibt den Namen des Computers an, von dem dieses Cmdlet Ereignisse aus den Ereignisprotokollen abruft. Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) des Computers ein. Der Standardwert ist der lokale Computer **localhost** . Dieser Parameter akzeptiert nur jeweils einen Computernamen.

Um Ereignisprotokolle von Remote Computern zu erhalten, konfigurieren Sie den Firewallport für den Ereignisprotokoll Dienst, um den Remote Zugriff zuzulassen.

Dieses Cmdlet beruht nicht auf PowerShell-Remoting. Sie können den **ComputerName** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.

```yaml
Type: System.String
Parameter Sets: GetLogSet, ListLogSet, ListProviderSet, GetProviderSet, HashQuerySet, XmlQuerySet
Aliases: Cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01** . Oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt. Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe eines Kennworts aufgefordert. Wenn Sie nur den Parameternamen eingeben, werden Sie aufgefordert, einen Benutzernamen und ein Kennwort einzugeben.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filterhashtable

Gibt eine Abfrage im Hash Tabellenformat an, um Ereignisse aus einem oder mehreren Ereignisprotokollen auszuwählen. Die Abfrage enthält eine Hash Tabelle mit einem oder mehreren **Schlüssel-Wert-** Paaren.

Hashtabellenabfragen haben die folgenden Regeln:

- Schlüssel und Werte Unterscheidung nach Groß-/Kleinschreibung.
- Platzhalter Zeichen sind nur in den Werten gültig, die mit den Schlüsseln **logName** und **providerName** verknüpft sind.
- Jeder Schlüssel kann in jeder Hash Tabelle nur einmal aufgelistet werden.
- Der **Pfadwert** nimmt Pfade zu `.etl` den `.evt` Protokolldateien, und an `.evtx` .
- Die Schlüssel " **logName** ", " **path** " und " **providerName** " können in derselben Abfrage verwendet werden.
- Der **UserID** -Schlüssel kann eine gültige Sicherheits-ID (SID) oder einen Domänen Kontonamen annehmen, der zum Erstellen eines gültigen **System. Security. Principal. NTAccount-Objekts** verwendet werden kann.
- Der **Datenwert** nimmt Ereignisdaten in einem unbenannten Feld an. Beispielsweise Ereignisse in den klassischen Ereignisprotokollen.
- `<named-data>` Key stellt ein benanntes Ereignis Datenfeld dar.

Wenn `Get-WinEvent` ein **Schlüssel-Wert-** paar nicht interpretieren kann, wird der Schlüssel als Name für die Ereignisdaten im Ereignis interpretiert.

Die gültigen `Get-WinEvent` **Schlüssel-Wert-** Paare lauten wie folgt:

- **LogName**=`<String[]>`
- **Provider Name**=`<String[]>`
- **ADS**=`<String[]>`
- **Keywords**=`<Long[]>`
- **Name**=`<Int32[]>`
- **Geringen**=`<Int32[]>`
- **StartTime**=`<DateTime>`
- **EndTime**=`<DateTime>`
- **UserID**=`<SID>`
- **Vorrats**=`<String[]>`
- `<named-data>`=`<String[]>`
- **Suppresshashfilter**=`<Hashtable>`

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: HashQuerySet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filterxml

Gibt eine strukturierte XML-Abfrage an, mit der dieses Cmdlet Ereignisse aus einem oder mehreren Ereignisprotokollen auswählt.

Um eine gültige XML-Abfrage zu generieren, verwenden Sie die Funktionen **benutzerdefinierte Ansicht erstellen** und **aktuellen Protokoll filtern** in Windows Ereignisanzeige. Verwenden Sie die Elemente im Dialogfeld, um eine Abfrage zu erstellen, und klicken Sie dann auf die Registerkarte „XML“, um die Abfrage im XML-Format anzuzeigen. Sie können den XML-Code auf der Registerkarte „XML“ in den Wert des **FilterXml** -Parameters kopieren. Weitere Informationen zu den Funktionen der Ereignisanzeige finden Sie in der Hilfe zur Ereignisanzeige.

Verwenden Sie eine XML-Abfrage, um eine komplexe Abfrage zu erstellen, die mehrere XPath-Anweisungen enthält. Das XML-Format ermöglicht es Ihnen auch, ein unter **drücken-XML** -Element zu verwenden, das Ereignisse aus der Abfrage ausschließt. Weitere Informationen zum XML-Schema für Ereignisprotokoll Abfragen finden Sie im Abschnitt [Abfrage Schema](/windows/win32/wes/queryschema-schema) und XML-Ereignis Abfragen der [Ereignis Auswahl](/previous-versions/aa385231(v=vs.85)).

Sie können auch ein unter **drücken** -Element mit dem **filterhashtable** -Parameter erstellen.

```yaml
Type: System.Xml.XmlDocument
Parameter Sets: XmlQuerySet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filterxpath

Gibt eine XPath-Abfrage an, mit der dieses Cmdlet Ereignisse aus einem oder mehreren Protokollen auswählt.

Weitere Informationen zur XPath-Sprache finden Sie unter [XPath-Referenz](/previous-versions/dotnet/netframework-4.0/ms256115(v=vs.100)) und im Abschnitt Auswahl Filter der [Ereignis Auswahl](/previous-versions/aa385231(v=vs.85)).

```yaml
Type: System.String
Parameter Sets: GetLogSet, GetProviderSet, FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Ruft Debug- und Analyseprotokolle sowie andere Ereignisprotokolle ab. Der **Force** -Parameter ist erforderlich, um ein Debug- oder Analyseprotokoll abzurufen, wenn der Wert des Name-Parameters Platzhalterzeichen enthält.

Standardmäßig schließt das `Get-WinEvent` Cmdlet diese Protokolle aus, es sei denn, Sie geben den vollständigen Namen eines Debug-oder Analyse Protokolls an.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetLogSet, ListLogSet, GetProviderSet, HashQuerySet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Listlog

Gibt die Ereignisprotokolle an. Geben Sie die Namen der Ereignisprotokolle in eine durch Kommas getrennte Liste ein. Platzhalter sind zulässig. Um alle Protokolle zu erhalten, verwenden Sie den Platzhalter Sternchen ( `*` ).

```yaml
Type: System.String[]
Parameter Sets: ListLogSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Listprovider

Gibt die Ereignisprotokoll Anbieter an, die von diesem Cmdlet abgerufen werden. Ein Ereignisprotokollanbieter ist ein Programm oder Dienst, der Ereignisse in das Ereignisprotokoll schreibt.

Geben Sie die Namen der Anbieter in eine durch Kommas getrennte Liste ein. Platzhalter sind zulässig. Um die Anbieter aller Ereignisprotokolle auf dem Computer zu erhalten, verwenden Sie das Sternchen-Platzhalter Zeichen ( `*` ).

```yaml
Type: System.String[]
Parameter Sets: ListProviderSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -LogName

Gibt die Ereignisprotokolle an, aus denen dieses Cmdlet Ereignisse aberhält. Geben Sie die Namen der Ereignisprotokolle in eine durch Kommas getrennte Liste ein. Platzhalter sind zulässig. Sie können Protokollnamen auch über die Pipeline an das `Get-WinEvent` Cmdlet übergeben.

> [!NOTE]
> PowerShell beschränkt nicht die Anzahl der Protokolle, die Sie anfordern können. Allerdings `Get-WinEvent` fragt das Cmdlet die Windows-API ab, die über eine Beschränkung von 256 verfügt. Dadurch kann es schwierig sein, alle Ihre Protokolle gleichzeitig zu filtern. Sie können dieses Problem umgehen, indem Sie eine `foreach` Schleife verwenden, um die einzelnen Protokolle wie folgt zu durchlaufen: `Get-WinEvent -ListLog * | ForEach-Object{ Get-WinEvent -LogName $_.Logname }`

```yaml
Type: System.String[]
Parameter Sets: GetLogSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Maxevents

Gibt die maximale Anzahl von Ereignissen an, die zurückgegeben werden. Geben Sie eine ganze Zahl ein, z.b. 100. Standardmäßig werden alle Ereignisse in den Protokollen oder Dateien zurückgegeben.

```yaml
Type: System.Int64
Parameter Sets: GetLogSet, GetProviderSet, FileSet, HashQuerySet, XmlQuerySet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Älteste

Geben Sie an, dass dieses Cmdlet die Ereignisse in der ältesten Reihenfolge abruft. Standardmäßig werden zuerst die neuesten Ereignisse zurückgegeben.

Dieser Parameter ist erforderlich, um Ereignisse aus `.etl` -und- `.evt` Dateien sowie aus Debug-und Analyse Protokollen zu erhalten. In diesen Dateien werden zuerst die ältesten Ereignisse aufgezeichnet, und es können auch nur die ältesten Ereignisse zuerst zurückgegeben werden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetLogSet, GetProviderSet, FileSet, HashQuerySet, XmlQuerySet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Gibt den Pfad zu den Ereignisprotokoll Dateien an, aus denen dieses Cmdlet Ereignisse erhält. Geben Sie die Pfade zu den Protokolldateien in eine durch Kommas getrennte Liste ein, oder verwenden Sie Platzhalterzeichen, um Dateipfadmuster zu erstellen.

`Get-WinEvent` unterstützt Dateien mit `.evt` den `.evtx` -,-und- `.etl` Dateinamen Erweiterungen. Sie können Ereignisse aus verschiedenen Dateien und Dateitypen in demselben Befehl einschließen.

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ProviderName

Gibt die Ereignisprotokoll Anbieter, von denen dieses Cmdlet Ereignisse abruft, als Zeichen folgen Array an. Geben Sie die Anbieternamen in eine durch Kommas getrennte Liste ein, oder verwenden Sie Platzhalterzeichen, um Anbieternamensmuster zu erstellen.

Ein Ereignisprotokollanbieter ist ein Programm oder Dienst, der Ereignisse in das Ereignisprotokoll schreibt. Dabei handelt es sich nicht um einen PowerShell-Anbieter.

```yaml
Type: System.String[]
Parameter Sets: GetProviderSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. String, System.Xml.XmlDocument, System. Collections. Hashtable

Sie können einen **logName** (String), eine **filterxml** -Abfrage oder eine **filterhashtable** -Abfrage an Pipeline in Pipeline `Get-WinEvent` .

## AUSGABEN

### System. Diagnostics. Eventing. Reader. EventLogConfiguration, System. Diagnostics. Eventing. Reader. EventLogRecord, System. Diagnostics. Eventing. Reader. ProviderMetadata

Mit dem Parameter " **listlog** " `Get-WinEvent` gibt **System. Diagnostics. Eventing. Reader. EventLogConfiguration** -Objekte zurück.

Mit dem Parameter " **List Provider** " `Get-WinEvent` gibt **System. Diagnostics. Eventing. Reader. ProviderMetadata** -Objekte zurück.

Mit allen anderen Parametern `Get-WinEvent` gibt **System. Diagnostics. Eventing. Reader. EventLogRecord** -Objekte zurück.

## HINWEISE

`Get-WinEvent` ist so konzipiert, dass das `Get-EventLog` Cmdlet auf Computern ersetzt wird, auf denen Windows Vista und spätere Versionen von Windows ausgeführt werden. `Get-EventLog` Ruft Ereignisse nur in klassischen Ereignisprotokollen ab. `Get-EventLog` wird aus Gründen der Abwärtskompatibilität beibehalten.

Die `Get-WinEvent` -und- `Get-EventLog` Cmdlets werden in Windows Pre-Installation Environment (Windows PE) nicht unterstützt.

## VERWANDTE LINKS

[about_Automatic_Variables](../Microsoft.PowerShell.Core/about/about_automatic_variables.md)

[about_Foreach](../Microsoft.PowerShell.Core/about/about_Foreach.md)

[about_Hash_Tables](../Microsoft.PowerShell.Core/about/about_hash_tables.md)

[Erstellen von Get-WinEvent-Abfragen mit FilterHashtable](/powershell/scripting/samples/Creating-Get-WinEvent-queries-with-FilterHashtable)

[Format-Table](../Microsoft.PowerShell.Utility/Format-Table.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Sort-Object](../Microsoft.PowerShell.Utility/Sort-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
