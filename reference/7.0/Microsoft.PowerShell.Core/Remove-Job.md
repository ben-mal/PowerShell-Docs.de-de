---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Job
ms.openlocfilehash: 52db5da9057023ce9a687e1d11b0534afaabdad9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212468"
---
# Remove-Job

## ZUSAMMENFASSUNG
Löscht einen PowerShell-Hintergrund Auftrag.

## SYNTAX

### Sessionidparameterset (Standard)

```
Remove-Job [-Force] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Jobparameterset

```
Remove-Job [-Job] <Job[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nameparameterset

```
Remove-Job [-Force] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Instanceidparameterset

```
Remove-Job [-Force] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Filterparameterset

```
Remove-Job [-Force] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateparameterset

```
Remove-Job [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Commandparameterset

```
Remove-Job [-Command <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Das- `Remove-Job` Cmdlet löscht PowerShell-Hintergrund Aufträge, die durch das- `Start-Job` Cmdlet oder durch Cmdlets gestartet wurden `Invoke-Command` , z. b., die den **AsJob** -Parameter unterstützen.

Sie können verwenden `Remove-Job` , um alle Aufträge zu löschen oder ausgewählte Aufträge zu löschen. Die Aufträge werden anhand Ihres **namens** , der **ID** , der **Instanz-ID** , des **Befehls** oder des **Zustands** identifiziert. Oder ein Job-Objekt kann über die Pipeline an gesendet werden `Remove-Job` . Ohne Parameter oder Parameterwerte `Remove-Job` hat keine Auswirkung.

Seit PowerShell 3,0 `Remove-Job` können benutzerdefinierte Auftrags Typen, z. b. geplante Aufträge und Workflow Aufträge, löschen. `Remove-Job`Löscht z. b. den geplanten Auftrag, alle Instanzen des geplanten Auftrags auf dem Datenträger und die Ergebnisse aller ausgelösten Auftrags Instanzen.

Wenn Sie versuchen, einen laufenden Auftrag zu löschen, `Remove-Job` schlägt fehl. Verwenden `Stop-Job` Sie das Cmdlet, um einen laufenden Auftrag zu unterbinden. Sie können auch `Remove-Job` mit dem **Force** -Parameter verwenden, um einen laufenden Auftrag zu löschen.

Aufträge verbleiben im globalen Auftrags Cache, bis Sie den Hintergrund Auftrag löschen oder die PowerShell-Sitzung schließen.

## BEISPIELE

### Beispiel 1: Löschen eines Auftrags mithilfe des Namens

In diesem Beispiel wird eine-Variable und die-Pipeline verwendet, um einen Auftrag anhand des Namens zu löschen.

```powershell
$batch = Get-Job -Name BatchJob
$batch | Remove-Job
```

`Get-Job` verwendet den **Name** -Parameter, um den Auftrag, **Batchjob** , anzugeben. Das Auftrags Objekt wird in der `$batch` Variablen gespeichert. Das-Objekt in `$batch` wird über die Pipeline an gesendet `Remove-Job` .

Eine Alternative besteht darin, den **Job** -Parameter zu verwenden, z `Remove-Job -Job $batch` . b..

### Beispiel 2: Löschen aller Aufträge in einer Sitzung

In diesem Beispiel werden alle Aufträge in der aktuellen PowerShell-Sitzung gelöscht.

```powershell
Get-job | Remove-Job
```

`Get-Job` Ruft alle Aufträge in der aktuellen PowerShell-Sitzung ab. Die Auftrags Objekte werden über die Pipeline an gesendet `Remove-Job` .

### Beispiel 3: Löschen von notstarted-Aufträgen

In diesem Beispiel werden alle Aufträge aus der aktuellen PowerShell-Sitzung gelöscht, die noch nicht gestartet wurden.

```powershell
Remove-Job -State NotStarted
```

`Remove-Job` verwendet den **State** -Parameter, um den Auftragsstatus anzugeben.

### Beispiel 4: Löschen von Aufträgen mit einem anzeigen Amen

In diesem Beispiel werden alle Aufträge aus der aktuellen Sitzung mit anzeigen Amen gelöscht, die auf * Batch * * enden, einschließlich der Aufträge, die ausgeführt werden.

```powershell
Remove-Job -Name *batch -Force
```

`Remove-Job` verwendet den **Name** -Parameter, um ein Auftrags Namensmuster anzugeben. Das Muster enthält das Platzhalter Zeichen ( `*` ), um alle Auftrags Namen zu suchen, die mit **Batch** enden. Der **Force** -Parameter löscht Aufträge, die ausführen.

### Beispiel 5: Löschen eines Auftrags, der von Invoke-Command erstellt wurde

In diesem Beispiel wird ein Auftrag, der auf einem Remote Computer mithilfe von `Invoke-Command` mit dem **AsJob** -Parameter gestartet wurde, entfernt.

Da im Beispiel der **AsJob** -Parameter verwendet wird, wird das Auftrags Objekt auf dem lokalen Computer erstellt.
Der Auftrag wird jedoch auf einem Remote Computer ausgeführt. Folglich verwenden Sie lokale Befehle, um den Auftrag zu verwalten.

```powershell
$job = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-Process} -AsJob
$job | Remove-Job
```

`Invoke-Command` führt einen Auftrag auf dem **Server01** -Computer aus. Der **AsJob** -Parameter führt den **ScriptBlock** als Hintergrund Auftrag aus. Das Auftrags Objekt wird in der `$job` Variablen gespeichert. Das `$job` Variablen Objekt wird über die Pipeline an gesendet `Remove-Job` .

### Beispiel 6: Löschen eines Auftrags, der von Invoke-Command erstellt wurde, und Start-Job

In diesem Beispiel wird gezeigt, wie ein Auftrag auf einem Remote Computer entfernt wird, der mithilfe von zum Ausführen von gestartet wurde `Invoke-Command` `Start-Job` . Das Auftrags Objekt wird auf dem Remote Computer erstellt, und Remote Befehle werden zum Verwalten des Auftrags verwendet. Eine permanente Verbindung ist erforderlich, wenn ein Remote `Start-Job` Befehl ausgeführt wird.

```powershell
$S = New-PSSession -ComputerName Server01
Invoke-Command -Session $S -ScriptBlock {Start-Job -ScriptBlock {Get-Process} -Name MyJob}
Invoke-Command -Session $S -ScriptBlock {Remove-Job -Name MyJob}
```

`New-PSSession` erstellt eine **PSSession** , eine permanente Verbindung, mit dem **Server01** -Computer. Die Verbindung wird in der `$S` Variablen gespeichert.

`Invoke-Command` stellt eine Verbindung mit der in gespeicherten Sitzung her `$S` . Der **ScriptBlock** verwendet `Start-Job` , um einen Remote Auftrag zu starten. Der Auftrag führt einen `Get-Process` Befehl aus und verwendet den **Name** -Parameter, um den anzeigen Amen **MyJob** anzugeben.

`Invoke-Command` verwendet die `$S` Sitzung und führt Sie aus `Remove-Job` . Der **Name** -Parameter gibt an, dass der Auftrag mit dem Namen **MyJob** gelöscht wird.

### Beispiel 7: Löschen eines Auftrags mithilfe der InstanceId

In diesem Beispiel wird ein Auftrag basierend auf seiner **InstanceId** entfernt.

```powershell
$job = Start-Job -ScriptBlock {Get-Process PowerShell}
$job | Format-List -Property *
Remove-Job -InstanceId ad02b942-8007-4407-87f3-d23e71955872
```

```Output
State         : Completed
HasMoreData   : True
StatusMessage :
Location      : localhost
Command       : Get-Process PowerShell
JobStateInfo  : Completed
Finished      : System.Threading.ManualResetEvent
InstanceId    : ad02b942-8007-4407-87f3-d23e71955872
Id            : 3
Name          : Job3
ChildJobs     : {Job4}
PSBeginTime   : 7/26/2019 11:36:56
PSEndTime     : 7/26/2019 11:36:57
PSJobTypeName : BackgroundJob
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
```

`Start-Job` startet einen Hintergrund Auftrag, und das Auftrags Objekt wird in der `$job` Variablen gespeichert.

Das-Objekt in `$job` wird über die Pipeline an gesendet `Format-List` . Der **Property** -Parameter verwendet ein Sternchen ( `*` ), um anzugeben, dass alle Eigenschaften des Objekts in einer Liste angezeigt werden.

`Remove-Job` verwendet den **InstanceId-** Parameter, um den Auftrag anzugeben, der gelöscht werden soll.

## PARAMETERS

### -Command

Löscht Aufträge, die die im Befehl angegebenen Wörter enthalten. Sie können ein Komma getrenntes Array eingeben.

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Fordert Sie zur Bestätigung auf, bevor `Remove-Job` ausgeführt wird.

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

### -Filter

Löscht Aufträge, die alle in der zugeordneten Hash Tabelle festgelegten Bedingungen erfüllen. Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.

Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen. Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, z. b. bei den mit erstellten `Start-Job` .

Dieser Parameter wird in Windows PowerShell 3.0 eingeführt.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force

Löscht einen Auftrag, auch wenn der Status des Auftrags "wird **ausgeführt** " lautet. Wenn der **Force** -Parameter nicht angegeben wird, werden `Remove-Job` keine laufenden Aufträge gelöscht.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, JobParameterSet, NameParameterSet, InstanceIdParameterSet, FilterParameterSet
Aliases: F

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Löscht Hintergrund Aufträge mit der angegebenen **ID** . Sie können ein Komma getrenntes Array eingeben. Die Auftrags- **ID** ist eine eindeutige ganze Zahl, die einen Auftrag innerhalb der aktuellen Sitzung identifiziert.

Um die **ID** eines Auftrags zu ermitteln, verwenden Sie `Get-Job` ohne Parameter.

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Löscht Aufträge mit der angegebenen **InstanceId** . Sie können ein Komma getrenntes Array eingeben. Eine **InstanceId** ist eine eindeutige GUID, die einen Auftrag identifiziert.

Um die **InstanceId** eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Auftrag

Gibt die zu löschenden Aufträge an. Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden. Sie können ein Komma getrenntes Array eingeben.

Sie können Auftrags Objekte über die Pipeline an senden `Remove-Job` .

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Löscht nur Aufträge mit dem angegebenen anzeigen Amen. Platzhalter sind zulässig. Sie können ein Komma getrenntes Array eingeben.

Anzeigen Amen für Aufträge sind nicht garantiert eindeutig, auch innerhalb einer PowerShell-Sitzung. Verwenden Sie die Parameter " **WhatIf** " und " **Confirm** ", wenn Sie Dateien nach Namen löschen.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -State

Löscht nur Aufträge mit dem angegebenen Zustand. Verwenden Sie den **Force** -Parameter, um Aufträge mit dem Status "wird **ausgeführt** " zu löschen.

Akzeptierte Werte:

- "Atbreakpoint"
- Blockiert
- Abgeschlossen
- Getrennt
- Fehlgeschlagen
- NotStarted
- Wird ausgeführt
- Beendet
- Wird beendet
- Ausgesetzt
- Wird angehalten

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: AtBreakpoint, Blocked, Completed, Disconnected, Failed, NotStarted, Running, Stopped, Stopping, Suspended, Suspending

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Zeigt, was geschieht, wenn ausgeführt wird `Remove-Job` . Das Cmdlet wird nicht ausgeführt.

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

### System. Management. Automation. Job

Sie können ein Auftrags Objekt über die Pipeline an senden `Remove-Job` .

## AUSGABEN

### Keine

`Remove-Job` generiert keine Ausgabe.

## HINWEISE

Ein PowerShell-Auftrag erstellt einen neuen Prozess. Wenn der Auftrag abgeschlossen ist, wird der Prozess beendet. Wenn `Remove-Job` ausgeführt wird, wird der Status des Auftrags entfernt.

Wenn ein Auftrag vor dem Abschluss beendet wird und der Prozess nicht beendet wurde, wird der Prozess erzwungen.

## VERWANDTE LINKS

[about_Jobs](./About/about_Jobs.md)

[about_Job_Details](./About/about_Job_Details.md)

[about_Remote_Jobs](./About/about_Remote_Jobs.md)

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)
