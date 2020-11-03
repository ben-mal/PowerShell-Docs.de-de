---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213423"
---
# New-JobTrigger

## ZUSAMMENFASSUNG
Erstellt einen Auftragstrigger für einen geplanten Auftrag.

## SYNTAX

### Once (Standard)

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### Täglich

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### Wöchentlich

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### AtStartup

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### AtLogon

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## DESCRIPTION
Das **New-Job-** Cmdlet erstellt einen Auftrags Fehler, der einen geplanten Auftrag nach einem einmaligen oder wiederkehrenden Zeitplan oder bei Auftreten eines Ereignisses startet.

Sie können das **ScheduledJobTrigger** -Objekt, das **New-JobTrigger** zurückgibt, verwenden, um einen Auftragstrigger für einen neuen oder vorhandenen geplanten Auftrag festzulegen.
Sie können mit dem Cmdlet "Get-JobTrigger" auch einen Auftrags--Auslösers erstellen, um den Auftrags Erstellungs Vorgang eines vorhandenen geplanten Auftrags zu erhalten, oder indem Sie einen Hash Tabellenwert zur Darstellung eines Auftrags Auslösers verwenden.

Überprüfen Sie beim Erstellen eines Auftrags Auslösers die Standardwerte der Optionen, die vom New-ScheduledJobOption-Cmdlet angegeben werden.
Diese Optionen, die die gleichen gültigen und standardmäßigen Werte wie die entsprechenden Optionen im **Task Scheduler** aufweisen, wirken sich auf die zeitliche Planung und Steuerung geplanter Aufträge aus.

**New-jobausgelöst** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*` oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: einmal Zeitplan

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

Dieser Befehl verwendet das **New-JobTrigger** -Cmdlet, um einen Auftragstrigger zu erstellen, der einen geplanten Auftrag nur einmal startet.
Der Wert des *At* -Parameters ist eine Zeichenfolge, die von Windows PowerShell in ein **DateTime** -Objekt konvertiert wird.
Der *At* -Parameterwert umfasst ein explizites Datum und nicht nur eine Uhrzeit.
Würde das Datum weggelassen, würde der Trigger mit dem aktuellen Datum und der Uhrzeit 3:00 Uhr erstellt, was wahrscheinlich einem Zeitpunkt in der Vergangenheit entspricht.

### Beispiel 2: Täglicher Zeitplan

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

Dieser Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag alle 3 Tage um 4:15 Uhr startet.

Da der Wert des *At* -Parameters kein Datum enthält, wird das aktuelle Datum im **DateTime** -Objekt als Datumswert verwendet.
Liegen das Datum und die Uhrzeit in der Vergangenheit, wird der geplante Auftrag bei der nächsten Ausführung gestartet, die 3 Tage nach dem *At* -Parameterwert liegt.

### Beispiel 3: wöchentlicher Zeitplan

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

Dieser Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag alle 4 Wochen am Montag, Mittwoch und Freitag um 23:00 Uhr startet.

Sie können auch den *DaysOfWeek* -Parameterwert in Ganzzahlen eingeben, z `-DaysOfWeek 1, 5` . b..

### Beispiel 4: Anmelde Zeitplan

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

Dieser Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag startet, sobald sich der Domänenadministrator beim Computer anmeldet.

### Beispiel 5: Verwenden einer zufälligen Verzögerung

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

Dieser Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag jeden Tag um 1:00 Uhr morgens startet.
Der Befehl verwendet den *RandomDelay* -Parameter, um die maximale Verzögerung auf 20 Minuten festzulegen.
Folglich wird der Auftrag täglich zwischen 1:00 Uhr und 1:20 Uhr ausgeführt, während das Intervall nach dem Pseudozufallsprinzip variiert.

Sie können eine zufällige Verzögerung für das Sampling, den Lastenausgleich und andere Verwaltungsaufgaben verwenden.
Wenn Sie den Verzögerungswert festlegen, überprüfen Sie die effektiven Werte und die Standardwerte des New-ScheduledJobOption-Cmdlets, und koordinieren Sie die Verzögerung mit den Options Einstellungen.

### Beispiel 6: Erstellen eines Auftrags Auslösers für einen neuen geplanten Auftrag

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

Diese Befehle verwenden einen Auftragstrigger zum Erstellen eines neuen geplanten Auftrags.

### Beispiel 7: Hinzufügen eines Auftrags Auslösers zu einem geplanten Auftrag

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

In diesem Beispiel wird veranschaulicht, wie einem vorhandenen geplanten Auftrag ein Auftragstrigger hinzugefügt wird.
Sie können einem geplanten Auftrag mehrere Auftragstrigger hinzufügen.

Der Befehl verwendet das Cmdlet "Add-JobTrigger", um den Auftrags-und den geplanten Auftrag "synchronizeapps" hinzuzufügen.
Der Wert des *Trigger* -Parameters ist ein **New-JobTrigger** -Befehl, der den Auftrag täglich um 3:10 Uhr ausführt.

Nach Abschluss des Befehls ist SynchronizeApps ein geplanter Auftrag, der zu den durch den Auftragstrigger angegebenen Zeiten ausgeführt wird.

### Beispiel 8: Erstellen eines Wiederholungs Auftrags Auslösers

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

Mit diesem Befehl wird ein Auftrags-Triggerwert erstellt, der einen Auftrag für 48 Stunden ab dem 12. September 2013 um 1:00 Uhr, alle 60 Minuten, ausführt.

### Beispiel 9: Abbrechen eines Wiederholungs Auftrags Auslösers

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

Mit diesem Befehl wird die Beendigung des Auftrags SecurityCheck erzwungen, dessen Ausführung bis zum Ablauf seines Auftragstriggers alle 60 Minuten ausgelöst wird.

Um zu verhindern, dass der Auftrag wiederholt wird, verwendet der Befehl die Get-JobTrigger, um den Auftrags Set-JobTrigger-und die Wiederholungs Dauer des Auftrags Auslösers in NULL (0) zu ändern.

### Beispiel 10: Erstellen eines stündlichen Auftrags Auslösers

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

Der folgende Befehl erstellt einen Auftragstrigger, der einen geplanten Auftrag für eine unbestimmte Dauer alle 12 Stunden einmal ausführt.
Der Zeitplan beginnt am nächsten Tag (21.09.2012) um Mitternacht (00:00 Uhr).

## PARAMETERS

### -At
Startet den Auftrag zum angegebenen Datum und zur angegebenen Uhrzeit.
Geben Sie ein **DateTime** -Objekt ein, z. b. ein Objekt, das vom Get-Date Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein Datum und eine Uhrzeit konvertiert werden kann, z. b. "19. April 2012 15:00", "12/31" oder "3AM".
Wenn Sie kein Datumselement, z. B. das Jahr, angeben, entspricht das Datum im Trigger dem jeweiligen Element aus dem aktuellen Datum.

Bei Verwendung des *Once* -Parameters legen Sie den Wert des *At* -Parameters auf ein Datum und eine Uhrzeit in der Zukunft fest.
Da das Standarddatum in einem **DateTime** -Objekt das aktuelle Datum ist, wird der Auftragstrigger für einen Zeitpunkt in der Vergangenheit erstellt, wenn Sie einen Zeitpunkt vor der aktuellen Zeit ohne explizites Datum angeben.

**DateTime** -Objekte und Zeichen folgen, die in **DateTime** -Objekte konvertiert werden, werden automatisch so angepasst, dass Sie mit den Datums-und Uhrzeit Formaten kompatibel sind, die für den lokalen Computer in der Systemsteuerung in Region und Sprache ausgewählt wurden.

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Atlogon
Startet den geplanten Auftrag, wenn sich die angegebenen Benutzer beim Computer anmelden.
Verwenden Sie zum Angeben eines Benutzers den *User* -Parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Atstartup
Startet den geplanten Auftrag beim Start von Windows.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Täglich
Gibt einen täglichen Wiederholungszeitplan für Aufträge an.
Verwenden Sie die anderen Parameter im *Daily* -Parametersatz, um die Details zum Zeitplan anzugeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Daysinterval
Gibt die Anzahl der Tage zwischen den Ausführungen in einem täglichen Zeitplan an.
Durch den Wert 3 wird der geplante Auftrag beispielsweise an Tag 1, 4, 7 usw. gestartet.
Der Standardwert ist 1.

```yaml
Type: System.Int32
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
Gibt die Wochentage an, an denen ein wöchentlicher geplanter Auftrag ausgeführt wird.
Geben Sie die Namen der Tage ein, z. B. „Montag“, oder ganze Zahlen von 0–6, wobei 0 Sonntag darstellt.
Dieser Parameter ist im Weekly-Parametersatz erforderlich.

Namen von Tagen werden im Auftragstrigger in ihre ganzzahligen Werte konvertiert.
Wenn Sie den Namen eines Tags in einem Befehl in Anführungszeichen einschließen, verwenden Sie für jeden Namen separate Anführungszeichen, z. B. „Montag“, „Dienstag“.
Wenn Sie mehrere Namen von Wochentagen in ein Paar von Anführungszeichen einschließen, werden die entsprechenden ganzzahligen Werte addiert.
„Montag, Dienstag“ (1, 2) ergibt z. B. den Wert „Mittwoch“ (3).

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Einmal
Gibt einen nicht wiederkehrenden (einmaligen) Zeitplan oder benutzerdefinierten Wiederholungszeitplan an.
Um einen Wiederholungszeitplan zu erstellen, verwenden Sie den *Once* -Parameter mit dem *RepetitionDuration* -Parameter und *RepetitionInterval* -Parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Randomdelay
Ermöglicht eine zufällige Verzögerung, die zur geplanten Startzeit beginnt, und legt den Wert für die maximale Verzögerung fest.
Die Länge der Verzögerung wird nach dem Pseudozufallsprinzip für jeden Start festgelegt und variiert von keiner Verzögerung bis zu der durch den Wert dieses Parameters angegebenen Dauer.
Beim Standardwert 0 (null, 00:00:00), wird die zufällige Verzögerung deaktiviert.

Geben Sie ein TimeSpan-Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet zurück gegebenes Objekt, oder geben Sie einen Wert im \<hours\> \<minutes\> Format:: ein \<seconds\> , der automatisch in ein **TimeSpan** -Objekt konvertiert wird.

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Repeatunbegrenzt
Durch diesen ab Windows PowerShell 4.0 verfügbaren Parameter ist es nicht mehr erforderlich, einen **TimeSpan.MaxValue** -Wert für den *RepetitionDuration* -Parameter anzugeben, um einen geplanten Auftrag für unbestimmte Zeit wiederholt auszuführen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wiederholtionduration
Wiederholt den Auftrag, bis die angegebene Zeit abgelaufen ist.
Die Häufigkeit der Wiederholungen wird durch den Wert des *RepetitionInterval* -Parameters bestimmt.
Wenn der Wert von **RepetitionInterval** z. B. 5 Minuten und der Wert von **RepetitionDuration** 2 Stunden beträgt, wird der Auftrag während zwei Stunden alle fünf Minuten ausgelöst.

Geben Sie ein TimeSpan-Objekt ein, z. b. ein Objekt, das vom New-TimeSpan Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein TimeSpan-Objekt konvertiert werden kann, 1:05:30 z. b.

Fügen Sie zum Ausführen eines Auftrags für unbestimmte Zeit stattdessen den *RepeatIndefinitely* -Parameter hinzu.

Um einen Auftrag vor Ablauf der Wiederholungs Dauer des Auftrags Auslösers anzuhalten, verwenden Sie das Cmdlet "Set-JobTrigger", um den *Wiederholungs Dauer* -Wert auf NULL (0) festzulegen.

Dieser Parameter ist nur gültig, wenn die Parameter *Once* , *At* und *RepetitionInterval* im Befehl verwendet werden.

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Repetitioninterval
Wiederholt den Auftrag im angegebenen Zeitintervall.
Wenn der Wert dieses Parameters 2 Stunden beträgt, wird der Auftrag z. B. alle zwei Stunden ausgelöst.
Beim Standardwert 0 wird der Auftrag nicht wiederholt.

Geben Sie ein TimeSpan-Objekt ein, z. b. ein Objekt, das vom New-TimeSpan Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein TimeSpan-Objekt konvertiert werden kann, 1:05:30 z. b.

Dieser Parameter ist nur gültig, wenn die Parameter *Once* , *At* und *RepetitionDuration* im Befehl verwendet werden.

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
Gibt die Benutzer an, die einen *AtLogon* -Start eines geplanten Auftrags auslösen.
Geben Sie den Namen eines Benutzers im \<UserName\> \<Domain\Username\> Format oder ein, oder geben Sie ein Sternchen ( \* ) ein, um alle Benutzer darzustellen.
Der Standardwert entspricht allen Benutzern.

```yaml
Type: System.String
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wöchentlich
Gibt einen wöchentlichen Wiederholungszeitplan für Aufträge an.
Verwenden Sie die anderen Parameter im Weekly-Parametersatz, um die Details zum Zeitplan anzugeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Weeksinterval
Gibt die Anzahl der Wochen zwischen den Ausführungen in einem wöchentlichen Auftragszeitplan an.
Durch den Wert 3 wird der geplante Auftrag beispielsweise in Woche 1, 4, 7 usw. gestartet.
Der Standardwert ist 1.

```yaml
Type: System.Int32
Parameter Sets: Weekly
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

### Microsoft. PowerShell. ScheduledJob. ScheduledJob-Auslösers

## HINWEISE

* Auftragstrigger werden nicht auf dem Datenträger gespeichert. Geplante Aufträge werden jedoch auf dem Datenträger gespeichert, und Sie können den Get-JobTrigger verwenden, um den Auftrags Auslösung eines beliebigen geplanten Auftrags zu erhalten.
* **New-Job-Auslösers** verhindert nicht, dass Sie einen Auftrags--Auslösers erstellen, der einen geplanten Auftrag nicht ausführen kann, z. b. einen einmaligen-Auslösung für ein Datum in der Vergangenheit.
* Das Register-ScheduledJob-Cmdlet akzeptiert ein ScheduledJob-Objekt, z. b. eines, das von den **New-Job-** oder Get-JobTrigger-Cmdlets zurückgegeben wird, oder eine Hash Tabelle mit auslöserwerten.

  Um eine Hashtabelle zu übermitteln, verwenden Sie die folgenden Schlüssel.

  `@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (oder eine beliebige gültige Zeit Zeichenfolge); `DaysOfWeek="Monday", "Wednesday"` (oder eine beliebige Kombination von Tages Namen); `Interval=2` (oder ein beliebiges gültiges Häufigkeits Intervall); `RandomDelay="30minutes"` (oder eine beliebige gültige TimeSpan-Zeichenfolge); `User="Domain1\User01` (oder ein beliebiger gültiger Benutzer; wird nur mit dem *atlogon* Frequency-Wert verwendet)}

## VERWANDTE LINKS

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
