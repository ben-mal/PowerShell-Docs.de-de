---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215468"
---
# Get-EventLog

## ZUSAMMENFASSUNG
Ruft die Ereignisse in einem Ereignisprotokoll oder eine Liste der Ereignisprotokolle auf dem lokalen Computer oder auf Remote Computern ab.

## SYNTAX

### Logname (Standard)

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### List

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Get-EventLog` Cmdlet werden Ereignisse und Ereignisprotokolle von lokalen Computern und Remote Computern abgerufen. Standardmäßig ruft `Get-EventLog` Protokolle vom lokalen Computer ab. Um Protokolle von Remote Computern zu erhalten, verwenden Sie den **Computername** -Parameter.

Sie können die `Get-EventLog` Parameter und Eigenschaftswerte verwenden, um nach Ereignissen zu suchen. Mit dem-Cmdlet werden Ereignisse abgerufen, die den angegebenen Eigenschafts Werten entsprechen.

PowerShell-Cmdlets, die das `EventLog` Substantiv enthalten, funktionieren nur für klassische Windows-Ereignisprotokolle wie z. b. Anwendung, System oder Sicherheit. Verwenden Sie, um Protokolle zu erhalten, in denen die Windows-Ereignisprotokoll Technologie in Windows Vista und neueren Windows-Versionen verwendet wird `Get-WinEvent` .

> [!NOTE]
> `Get-EventLog` verwendet eine als veraltet markierte Win32-API. Die Ergebnisse sind möglicherweise nicht korrekt. Verwenden Sie `Get-WinEvent` stattdessen das-Cmdlet.

## BEISPIELE

### Beispiel 1: erhalten von Ereignisprotokollen auf dem lokalen Computer

In diesem Beispiel wird die Liste der Ereignisprotokolle angezeigt, die auf dem lokalen Computer verfügbar sind. Die Namen in der Spalte Log werden mit dem Parameter **logName** verwendet, um anzugeben, welches Protokoll nach Ereignissen durchsucht werden soll.

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

Das `Get-EventLog` Cmdlet verwendet den **List** -Parameter, um die verfügbaren Protokolle anzuzeigen.

### Beispiel 2: erhalten aktueller Einträge aus einem Ereignisprotokoll auf dem lokalen Computer

In diesem Beispiel werden aktuelle Einträge aus dem System Ereignisprotokoll abgerufen.

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Ereignisprotokoll anzugeben. Mit dem **neuesten** Parameter werden die fünf letzten Ereignisse zurückgegeben.

### Beispiel 3: Suchen aller Quellen für eine bestimmte Anzahl von Einträgen in einem Ereignisprotokoll

Dieses Beispiel zeigt, wie Sie alle Quellen suchen können, die in den 1000 letzten Einträgen im System Ereignisprotokoll enthalten sind.

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben. Der **neueste** Parameter wählt die 1000 aktuellsten Ereignisse aus. Die Ereignis Objekte werden in der `$Events` Variablen gespeichert. Die `$Events` Objekte werden über die Pipeline an das `Group-Object` Cmdlet gesendet.
`Group-Object` verwendet den **Property** -Parameter, um die Objekte nach Quelle zu gruppieren, und zählt die Anzahl der-Objekte für jede Quelle. Der **noelement** -Parameter entfernt die Gruppenmitglieder aus der Ausgabe.
Das `Sort-Object` Cmdlet verwendet den **Property** -Parameter, um nach der Anzahl der einzelnen Quellen Namen zu sortieren.
Der **Absteig** Ende Parameter sortiert die Liste nach Anzahl von der höchsten zum niedrigsten.

### Beispiel 4: erhalten von Fehlerereignissen aus einem bestimmten Ereignisprotokoll

In diesem Beispiel werden Fehlerereignisse aus dem System Ereignisprotokoll abgerufen.

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben. Der **entryType** -Parameter filtert die Ereignisse so, dass nur Fehlerereignisse angezeigt werden.

### Beispiel 5: Ereignisse aus einem Ereignisprotokoll mit InstanceId und Quellwert erhalten

In diesem Beispiel werden Ereignisse aus dem System Protokoll für eine bestimmte InstanceId und eine bestimmte Quelle abgerufen.

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben. Der **InstanceId-** Parameter wählt die Ereignisse mit der angegebenen Instanz-ID aus. Der **Source** -Parameter gibt die Ereignis Eigenschaft an.

### Beispiel 6: Ereignisse von mehreren Computern erhalten

Mit diesem Befehl werden die Ereignisse aus dem System Ereignisprotokoll auf drei Computern abgerufen: Server01, Server02 und Server03.

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben. Der **Computername** -Parameter verwendet eine durch Trennzeichen getrennte Zeichenfolge, um die Computer aufzulisten, von denen Sie die Ereignisprotokolle erhalten möchten.

### Beispiel 7: alle Ereignisse, die ein bestimmtes Wort enthalten, werden in der Nachricht angezeigt.

Dieser Befehl ruft alle Ereignisse im System Ereignisprotokoll ab, die ein bestimmtes Wort in der Meldung des Ereignisses enthalten. Es ist möglich, dass der Wert Ihres angegebenen **Nachrichten** Parameters im Inhalt der Nachricht enthalten ist, aber nicht in der PowerShell-Konsole angezeigt wird.

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Ereignisprotokoll anzugeben. Der **Message** -Parameter gibt ein Wort an, nach dem im Meldungs Feld jedes Ereignisses gesucht werden soll.

### Beispiel 8: Anzeigen der Eigenschaftswerte eines Ereignisses

Dieses Beispiel zeigt, wie alle Eigenschaften und Werte eines Ereignisses angezeigt werden.

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Ereignisprotokoll anzugeben. Der **neueste** Parameter wählt das aktuellste Ereignis Objekt aus. Das-Objekt wird in der- `$A` Variable gespeichert. Das Objekt in der `$A` Variablen wird in der Pipeline an das `Select-Object` Cmdlet gesendet.
`Select-Object` verwendet den **Property** -Parameter mit einem Sternchen ( `*` ), um alle Eigenschaften des Objekts auszuwählen.

### Beispiel 9: Ereignisse aus einem Ereignisprotokoll mithilfe einer Quell-und Ereignis-ID

In diesem Beispiel werden Ereignisse für eine angegebene Quelle und Ereignis-ID abgerufen.

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das Anwendungs Ereignisprotokoll anzugeben. Der **Quell** Parameter gibt den Anwendungsnamen an, Outlook. Die Objekte werden über die Pipeline an das `Where-Object` Cmdlet gesendet. Für jedes Objekt in der Pipeline verwendet das `Where-Object` Cmdlet die Variable, `$_.EventID` um die Ereignis-ID-Eigenschaft mit dem angegebenen Wert zu vergleichen. Die Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet. `Select-Object` verwendet den **Property** -Parameter, um die Eigenschaften auszuwählen, die in der PowerShell-Konsole angezeigt werden sollen.

### Beispiel 10: Ereignisse erhalten und nach einer Eigenschaft gruppieren

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben. Der **username** -Parameter enthält den Platzhalter ( `*` ), um einen Teil des Benutzernamens anzugeben. Die Ereignis Objekte werden über die Pipeline an das `Group-Object` Cmdlet gesendet. `Group-Object` verwendet den **Property** -Parameter, um anzugeben, dass die **username** -Eigenschaft zum Gruppieren der Objekte und zum zählen der Anzahl von Objekten für jeden Benutzernamen verwendet wird. Der **noelement** -Parameter entfernt die Gruppenmitglieder aus der Ausgabe. Die Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.
`Select-Object` verwendet den **Property** -Parameter, um die Eigenschaften auszuwählen, die in der PowerShell-Konsole angezeigt werden sollen.

### Beispiel 11: Ereignisse, die während eines bestimmten Datums-und Zeit Bereichs aufgetreten sind

In diesem Beispiel werden Fehlerereignisse aus dem System Ereignisprotokoll für einen bestimmten Datums-und Uhrzeit Bereich abgerufen. Die Parameter " **before** " und " **after** " legen den Datums-und Uhrzeit Bereich fest, werden jedoch aus der Ausgabe ausgeschlossen.

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

Das `Get-Date` Cmdlet verwendet den **Date** -Parameter, um ein Datum und eine Uhrzeit anzugeben. Die **DateTime** -Objekte werden in der `$Begin` -Variable und der- `$End` Variablen gespeichert. Das- `Get-EventLog` Cmdlet verwendet den **logName** -Parameter, um das System Protokoll anzugeben. Der **entryType** -Parameter gibt den Fehler Ereignistyp an. Der Datums-und Uhrzeit Bereich wird durch den **after** -Parameter und `$Begin` die-Variable sowie den **before** -Parameter und die-Variable festgelegt `$End` .

## PARAMETERS

### Nach

Ruft Ereignisse ab, die nach einem angegebenen Datum und einer angegebenen Uhrzeit aufgetreten sind. Das Datum und die Uhrzeit des **after** -Parameters werden aus der Ausgabe ausgeschlossen. Geben Sie ein **DateTime** -Objekt ein, z. b. den vom `Get-Date` Cmdlet zurückgegebenen Wert.

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Asbaseobject

Gibt an, dass dieses Cmdlet ein **System. Diagnostics. EventLogEntry** -Standard Objekt für jedes Ereignis zurückgibt. Ohne diesen Parameter `Get-EventLog` gibt ein erweitertes **psobject** -Objekt mit zusätzlichen Eigenschaften " **Eventlogname** ", " **Source** " und " **InstanceId** " zurück.

Um die Auswirkung dieses Parameters anzuzeigen, übergeben Sie die Ereignisse an das `Get-Member` Cmdlet, und untersuchen Sie den **TypeName** -Wert im Ergebnis.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsString

Gibt an, dass dieses Cmdlet die Ausgabe als Zeichen folgen anstelle von-Objekten zurückgibt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vor

Ruft Ereignisse ab, die vor dem angegebenen Datum und der angegebenen Uhrzeit aufgetreten sind. Der **before** -Parameter "Date" und "Time" werden aus der Ausgabe ausgeschlossen. Geben Sie ein **DateTime** -Objekt ein, z. b. den vom `Get-Date` Cmdlet zurückgegebenen Wert.

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Dieser Parameter gibt den NetBIOS-Namen, die IP-Adresse oder einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN) eines Remote Computers an.

Wenn der **Computername** -Parameter nicht angegeben ist, wird `Get-EventLog` standardmäßig der lokale Computer verwendet. Der-Parameter akzeptiert auch einen Punkt ( `.` ), um den lokalen Computer anzugeben.

Der **Computername** -Parameter beruht nicht auf Windows PowerShell-Remoting. Sie können `Get-EventLog` mit dem **Computername** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remote Befehlen konfiguriert ist.

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

### -EntryType

Gibt den Eintragstyp der Ereignisse, die von diesem Cmdlet abgerufen werden, als Zeichen folgen Array an.

Zulässige Werte für diesen Parameter:

- Fehler
- Information
- FAILUREAUDIT
- ;
- Warnung

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Index

Gibt die Indexwerte an, die aus dem Ereignisprotokoll abgeleitet werden sollen. Der-Parameter akzeptiert eine durch Kommas getrennte Zeichenfolge von Werten.

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

Gibt die Instanz-IDs an, die aus dem Ereignisprotokoll abgeleitet werden sollen. Der-Parameter akzeptiert eine durch Kommas getrennte Zeichenfolge von Werten.

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -List

Zeigt die Liste der Ereignisprotokolle auf dem Computer an.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

Gibt den Namen eines Ereignis Protokolls an. Zum Ermitteln der Protokollnamen verwenden Sie `Get-EventLog -List` . Platzhalterzeichen sind zulässig. Dieser Parameter ist erforderlich.

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Meldung

Gibt eine Zeichenfolge in der Ereignismeldung an. Sie können diesen Parameter verwenden, um nach Nachrichten zu suchen, die bestimmte Wörter oder Ausdrücke enthalten. Platzhalter sind zulässig.

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Latest

Beginnt mit den neuesten Ereignissen und ruft die angegebene Anzahl von Ereignissen ab. Die Anzahl der Ereignisse ist beispielsweise erforderlich `-Newest 100` . Gibt die maximale Anzahl von Ereignissen an, die zurückgegeben werden.

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Gibt als Zeichen folgen Array Quellen an, die in das Protokoll geschrieben wurden, das von diesem Cmdlet abgerufen wird. Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -UserName

Gibt Benutzernamen, die Ereignissen zugeordnet sind, als Zeichen folgen Array an. Geben Sie Namen oder Namensmuster ein, `User01` z `User*` . b `Domain01\User*` ., oder. Platzhalter sind zulässig.

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Eingaben können nicht an übergeben werden `Get-EventLog` .

## AUSGABEN

### System. Diagnostics. EventLogEntry. System. Diagnostics. EventLog. System.String

Wenn der **logName** -Parameter angegeben wird, handelt es sich bei der Ausgabe um eine Sammlung von **System. Diagnostics. EventLogEntry** -Objekten.

Wenn nur der **List** -Parameter angegeben wird, handelt es sich bei der Ausgabe um eine Sammlung von **System. Diagnostics. EventLog** -Objekten.

Wenn sowohl der **List** -Parameter als auch der **AsString** -Parameter angegeben sind, ist die Ausgabe eine Auflistung von **System. String** -Objekten.

## HINWEISE

Die Cmdlets `Get-EventLog` und `Get-WinEvent` werden im Windows Preinstallation Environment (Windows PE) nicht unterstützt.

## VERWANDTE LINKS

[Clear-EventLog](Clear-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Group-Object](../Microsoft.PowerShell.Utility/Group-Object.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
