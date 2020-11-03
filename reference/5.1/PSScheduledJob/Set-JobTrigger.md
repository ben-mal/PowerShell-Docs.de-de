---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213399"
---
# Set-JobTrigger

## ZUSAMMENFASSUNG
Ändert den Auftragstrigger eines geplanten Auftrags.

## SYNTAX

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
Das **Set-JobTrigger** -Cmdlet ändert die Eigenschaften der Auftragstrigger geplanter Aufträge.
Mit dem Cmdlet können Sie ändern, wann oder wie häufig Aufträge gestartet werden, oder von zeitbasierten Zeitplänen zu Zeitplänen wechseln, die durch einen Anmelde- oder Startvorgang ausgelöst werden.

Ein Auftrags-Trigger definiert einen wiederkehrenden Zeitplan oder Bedingungen für das Starten eines geplanten Auftrags.
Obwohl Auftragstrigger nicht auf dem Datenträger gespeichert werden, können Sie die Auftragstrigger geplanter Aufträge ändern, die auf dem Datenträger gespeichert werden.

Zum Ändern eines Auftrags Auslösers eines geplanten Auftrags beginnen Sie mit dem Cmdlet "Get-JobTrigger", um den Auftrags-und einen geplanten Auftrag zu erhalten.
Reichen Sie dann den Trigger an **Set-ScheduledJobOption** weiter, oder speichern Sie den Trigger in einer Variablen, und verwenden Sie den *InputObject* -Parameter des **Set-JobTrigger** -Cmdlets, um den Trigger zu identifizieren.
Verwenden Sie die übrigen Parameter von **Set-JobTrigger** , um den Auftragstrigger zu ändern.

Wenn Sie den Typ eines Auftrags Auslösers ändern (z. b. das Ändern eines Auftrags Auslösers von einem täglichen oder wöchentlichen) in einen *atlogon* -Vorgang, werden die ursprünglichen Auslösereigenschaften gelöscht.
Wenn Sie jedoch die Werte des Triggers, aber nicht dessen Typ ändern, also z. B. die Tage in einem Weekly-Trigger, werden nur die Eigenschaften geändert, die Sie angeben.
Alle anderen Eigenschaften des ursprünglichen Auftragstriggers werden beibehalten.

**Set-jobausgelöst** ist eine Sammlung von Auftrags Planungs-Cmdlets im psscheduledjob-Modul, das in Windows PowerShell enthalten ist.

Weitere Informationen zu geplanten Aufträgen finden Sie unter den Info-Themen im PSScheduledJob-Modul.
Importieren Sie das psscheduledjob-Modul, und geben Sie dann Folgendes ein: `Get-Help about_Scheduled*`  oder about_Scheduled_Jobs.

Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Ändern der Tage eines Auftrags Auslösers

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

Dieses Beispiel zeigt, wie die Tage in einem Weekly-Auftragstrigger geändert werden.

Der erste Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags-und den geplanten Auftrag "DeployPackage" zu erhalten.
Die Ausgabe zeigt, dass der Trigger den Auftrag mittwochs und samstags um Mitternacht startet.

Dieser Befehl ist nicht erforderlich. Er soll lediglich die Auswirkung der Triggeränderung veranschaulichen.

### Beispiel 2: Ändern des Auftrags auslösertyps

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

In diesem Beispiel wird veranschaulicht, wie der Typ des Auftragstriggers geändert wird, der einen Auftrag startet.
Durch die Befehle in diesem Beispiel wird ein AtStartup-Auftragstrigger durch einen Weekly-Trigger ersetzt.

Der erste Befehl verwendet das Cmdlet "Get-JobTrigger", um den Auftrags--Befehl des geplanten Inventur Auftrags zu erhalten.
Die Ausgabe zeigt, dass der Auftrag über zwei Trigger für einen täglichen Trigger und einen *atstartup* -Trigger verfügt.

Dieser Befehl ist nicht erforderlich. Er soll lediglich die Auswirkung der Triggeränderung veranschaulichen.

### Beispiel 3: Ändern des Benutzers für einen Remote Auftrags--Auslösers

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

Mit diesem Befehl wird der Benutzer in allen *atlogon* -Auftrags Triggern geplanter Aufträge auf dem Server01-Computer geändert.

Der Befehl verwendet das Cmdlet "Invoke-Command", um einen Befehl auf dem Server01-Computer auszuführen.

Der Remote Befehl beginnt mit einem Get-ScheduledJob Befehl, mit dem alle geplanten Aufträge auf dem Computer abgerufen werden.
Die geplanten Aufträge werden an das Get-JobTrigger-Cmdlet weitergeleitet, das die Auftrags Trigger der geplanten Aufträge abruft.
Jeder Auftragstrigger enthält eine JobDefinition-Eigenschaft, die den geplanten Auftrag umfasst, damit die Zuordnung des Triggers zum geplanten Auftrag selbst bei einer Änderung erhalten bleibt.

Die Auftrags Trigger werden an das Where-Object-Cmdlet weitergeleitet, das Auftrags Trigger mit der User-Eigenschaft abruft.
Die ausgewählten Auftragstrigger werden an das **Set-JobTrigger** -Cmdlet weitergereicht, das den Benutzer in Domain01\Admin02 ändert.

### Beispiel 4: Ändern eines der vielen Auftrags Trigger

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

Durch die Befehle in diesem Beispiel wird das Wiederholungsintervall des *Once* -Auftragstriggers des geplanten Auftrags SecurityCheck von stündlich in alle 90 Minuten geändert.
Der geplante Securitycheck-Auftrag hat drei Auftrags Trigger, sodass die Befehle den *triggerid* -Parameter des Get-JobTrigger Cmdlets verwenden, um den Auftrags Trigger zu identifizieren, der geändert wird.

Der erste Befehl verwendet das **Get-JobTrigger** -Cmdlet zum Abrufen aller Auftragstrigger des geplanten Auftrags SecurityCheck.
An der Ausgabe, in der die IDs der Auftragstrigger angezeigt werden, ist erkennbar, dass der *Once* -Auftragstrigger über die ID 3 verfügt.

## PARAMETERS

### -At
Startet den Auftrag zum angegebenen Datum und zur angegebenen Uhrzeit.
Geben Sie ein **DateTime** -Objekt ein, z. b. ein Objekt, das vom Get-Date-Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in eine Uhrzeit konvertiert werden kann, z. b. "19. April 2012 15:00", "12/31/2013 9:00 pm" oder "3AM".

Wenn Sie kein Element des **DateTime** -Objekts angeben, z. b. Sekunden, wird dieses Element des Auftrags Auslösers nicht geändert.
Wenn der ursprüngliche Auftrags--ausgelöst kein **DateTime** -Objekt enthielt und Sie ein Element weglassen, wird der Auftrags--Vorgang mit dem entsprechenden Element aus dem aktuellen Datum und der aktuellen Uhrzeit erstellt.

Bei Verwendung des *Once* -Parameters legen Sie den Wert des *At* -Parameters auf ein bestimmtes Datum und eine bestimmte Uhrzeit fest.
Da das Standarddatum in einem **DateTime** -Objekt das aktuelle Datum ist, erhalten Sie einen Auftragstrigger für einen Zeitpunkt in der Vergangenheit, wenn Sie einen Zeitpunkt vor der aktuellen Zeit ohne explizites Datum festlegen.

**DateTime** -Objekte und Zeichen folgen, die in **DateTime** -Objekte konvertiert werden, werden automatisch so angepasst, dass Sie mit den Datums-und Uhrzeit Formaten kompatibel sind, die für den lokalen Computer in der Systemsteuerung in Region und Sprache ausgewählt wurden.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Atstartup
Startet den geplanten Auftrag beim Start von Windows.

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

### -Täglich
Gibt einen täglichen Wiederholungszeitplan für Aufträge an.
Verwenden Sie die anderen Parameter im *Daily* -Parametersatz, um die Details zum Zeitplan anzugeben.

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

### -Daysinterval
Gibt die Anzahl der Tage zwischen den Ausführungen in einem täglichen Zeitplan an.
Durch den Wert 3 wird der geplante Auftrag beispielsweise an Tag 1, 4, 7 usw. gestartet.
Der Standardwert ist 1.

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

### -DaysOfWeek
Gibt die Wochentage an, an denen ein wöchentlicher geplanter Auftrag ausgeführt wird.
Geben Sie Tagnamen ein, z. b. Montag, Donnerstag, ganze Zahlen 0-6, wobei 0 Sonntag darstellt, oder ein Sternchen (), das \* jeden Tag repräsentiert.
Dieser Parameter ist im Weekly-Parametersatz erforderlich.

Namen von Tagen werden im Auftragstrigger in ihre ganzzahligen Werte konvertiert.
Wenn Sie den Namen eines Tags in einem Befehl in Anführungszeichen einschließen, verwenden Sie für jeden Namen separate Anführungszeichen, z. B. „Montag“, „Dienstag“.
Wenn Sie mehrere Namen von Wochentagen in ein Paar von Anführungszeichen einschließen, werden die entsprechenden ganzzahligen Werte addiert.
„Montag, Dienstag“ (1, 2) ergibt z. B. den Wert „Mittwoch“ (3).

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Gibt die Auftragstrigger an.
Geben Sie eine Variable ein, die **ScheduledJob-** Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, der **ScheduledJob-** Objekte abruft, z. b. einen Get-JobTrigger Befehl
Sie können ein **ScheduledJob-** Objekt auch über die Pipeline an **Set-Job-** Token übergeben.

Wenn Sie mehrere Auftragstrigger angeben, nimmt **Set-JobTrigger** die gleichen Änderungen an allen Auftragstriggern vor.

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Einmal
Gibt einen nicht wiederkehrenden (einmaligen) Zeitplan an.

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

### -PassThru
Gibt die Auftragstrigger zurück, die sich geändert haben.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### -Randomdelay
Ermöglicht eine zufällige Verzögerung, die zur geplanten Startzeit beginnt, und legt den Wert für die maximale Verzögerung fest.
Die Länge der Verzögerung wird nach dem Pseudozufallsprinzip für jeden Start festgelegt und variiert von keiner Verzögerung bis zu der durch den Wert dieses Parameters angegebenen Dauer.
Beim Standardwert 0 (null, 00:00:00), wird die zufällige Verzögerung deaktiviert.

Geben Sie ein TimeSpan-Objekt ein, z. b. ein vom New-TimeSpan-Cmdlet zurück gegebenes Objekt, oder geben Sie einen Wert im \<hours\> \<minutes\> Format:: ein \<seconds\> , der automatisch in ein TimeSpan-Objekt konvertiert wird.

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
Parameter Sets: (All)
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
Wenn der Wert von **RepetitionInterval** z. B. 5 Minuten und der Wert von *RepetitionDuration* 2 Stunden beträgt, wird der Auftrag während zwei Stunden alle fünf Minuten ausgelöst.

Geben Sie ein TimeSpan-Objekt ein, z. b. ein Objekt, das vom New-TimeSpan Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein TimeSpan-Objekt konvertiert werden kann, 1:05:30 z. b.

Fügen Sie zum Ausführen eines Auftrags für unbestimmte Zeit stattdessen den *RepeatIndefinitely* -Parameter hinzu.

Um einen Auftrag vor Ablauf der Wiederholungsdauer des Auftragstriggers zu beenden, legen Sie den **RepetitionDuration** -Wert auf 0 (null) fest.

Um die Wiederholungsdauer oder das Wiederholungsintervall eines *Once* -Auftragstriggers zu ändern, muss der Befehl sowohl den **RepetitionInterval** -Parameter als auch den **RepetitionDuration** -Parameter enthalten.
Um die Wiederholungsdauer oder die Wiederholungsintervalle anderer Typen von Auftragstriggern zu ändern, muss der Befehl die Parameter *Once* , *At* , *RepetitionInterval* und *RepetitionDuration* enthalten.

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

### -Repetitioninterval
Wiederholt den Auftrag im angegebenen Zeitintervall.
Wenn der Wert dieses Parameters 2 Stunden beträgt, wird der Auftrag z. B. alle zwei Stunden ausgelöst.
Beim Standardwert 0 wird der Auftrag nicht wiederholt.

Geben Sie ein TimeSpan-Objekt ein, z. b. ein Objekt, das vom New-TimeSpan Cmdlet zurückgegeben wird, oder eine Zeichenfolge, die in ein TimeSpan-Objekt konvertiert werden kann, 1:05:30 z. b.

Um die Wiederholungsdauer oder das Wiederholungsintervall eines **Once** -Auftragstriggers zu ändern, muss der Befehl sowohl den **RepetitionInterval** -Parameter als auch den **RepetitionDuration** -Parameter enthalten.
Um die Wiederholungsdauer oder die Wiederholungsintervalle anderer Typen von Auftragstriggern zu ändern, muss der Befehl die Parameter **Once** , **At** , **RepetitionInterval** und **RepetitionDuration** enthalten.

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

### -User
Gibt die Benutzer an, die einen *AtLogon* -Start eines geplanten Auftrags auslösen.
Geben Sie den Namen eines Benutzers im \<UserName\> \<Domain\Username\> Format oder ein, oder geben Sie ein Sternchen ( \* ) ein, um alle Benutzer darzustellen.
Der Standardwert entspricht allen Benutzern.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wöchentlich
Gibt einen wöchentlichen Wiederholungszeitplan für Aufträge an.
Verwenden Sie die anderen Parameter im *wöchentlichen* Parametersatz, um die Details zum Zeitplan anzugeben.

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

### -Weeksinterval
Gibt die Anzahl der Wochen zwischen den Ausführungen in einem wöchentlichen Auftragszeitplan an.
Durch den Wert 3 wird der geplante Auftrag beispielsweise in Woche 1, 4, 7 usw. gestartet.
Der Standardwert ist 1.

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

### CommonParameters
Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Microsoft. PowerShell. ScheduledJob. ScheduledJob-Auslösers
Sie können mehrere Auftrags Trigger an **Set-jobtrigger** weiterreichen.

## AUSGABEN

### None oder Microsoft. PowerShell. ScheduledJob. scheduledjobauslöst
Bei Verwendung des *Passthru* -Parameters gibt **Set-JobTrigger** die geänderten Auftragstrigger zurück.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

* Auftragstrigger verfügen über eine JobDefintion-Eigenschaft, durch die sie dem geplanten Auftrag zugeordnet werden. Wenn Sie den Auftragstrigger eines geplanten Auftrags ändern, wird der Auftrag geändert. Sie müssen keinen Set-ScheduledJob Befehl verwenden, um den geänderten-Befehl auf den geplanten Auftrag anzuwenden.

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
