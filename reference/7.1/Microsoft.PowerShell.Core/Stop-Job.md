---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job
ms.openlocfilehash: 5d8fdd3b798caab4661b1b26641c4e534cbd99a5
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390557"
---
# Stop-Job

## ZUSAMMENFASSUNG
Beendet einen PowerShell-Hintergrund Auftrag.

## SYNTAX

### Sessionidparameterset (Standard)

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Jobparameterset

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Nameparameterset

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Instanceidparameterset

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Stateparameterset

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Filterparameterset

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Stop-Job` Cmdlet werden PowerShell-Hintergrund Aufträge, die gerade ausgeführt werden, beendet. Mit diesem Cmdlet können Sie alle Aufträge oder ausgewählte Aufträge basierend auf dem Namen, der ID, der Instanz-ID oder dem Status oder durch Übergabe eines Auftrags Objekts an Abbrechen `Stop-Job` .

Sie können verwenden, `Stop-Job` um Hintergrund Aufträge zu verhindern, wie z. b. solche, die mit dem `Start-Job` Cmdlet oder dem **AsJob** -Parameter eines beliebigen Cmdlets gestartet wurden. Wenn Sie einen Hintergrund Auftrag beenden, schließt PowerShell alle Aufgaben ab, die in der Auftrags Warteschlange ausstehend sind, und beendet dann den Auftrag. Keine neuen Vorgänge werden in die Warteschlange hinzugefügt, nachdem dieser Befehl gesendet wird.

Mit diesem Cmdlet werden die Hintergrundaufträge nicht gelöscht. Verwenden Sie das Cmdlet, um einen Auftrag zu löschen `Remove-Job` .

Ab Windows PowerShell 3,0 werden von `Stop-Job` auch benutzerdefinierte Auftrags Typen, z. b. Workflow Aufträge und Instanzen von geplanten Aufträgen, von angehalten. Damit `Stop-Job` ein Auftrag mit einem benutzerdefinierten Auftragstyp beendet werden kann, müssen Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung importieren, bevor Sie einen `Stop-Job` Befehl ausführen, indem Sie entweder das `Import-Module` Cmdlet verwenden oder ein Cmdlet im Modul verwenden oder ein Cmdlet verwenden. Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.

## BEISPIELE

### Beispiel 1: Abbrechen eines Auftrags auf einem Remote Computer mit Invoke-Command

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

Dieses Beispiel zeigt, wie das `Stop-Job` Cmdlet verwendet wird, um einen Auftrag anzuhalten, der auf einem Remote Computer ausgeführt wird.

Da der Auftrag mithilfe des `Invoke-Command` Cmdlets gestartet wurde, um einen `Start-Job` Befehl Remote auszuführen, wird das Auftrags Objekt auf dem Remote Computer gespeichert. Sie müssen einen anderen `Invoke-Command` Befehl verwenden, um einen `Stop-Job` Befehl Remote auszuführen. Weitere Informationen zu Remotehintergrundaufträgen finden Sie unter „about_Remote_Jobs“.

Mit dem ersten Befehl wird eine PowerShell-Sitzung ( **PSSession** ) auf dem Server01-Computer erstellt, und anschließend wird das Sitzungs Objekt in der `$s` Variablen gespeichert. Der Befehl verwendet die Anmeldeinformationen eines Domänenadministrators.

Der zweite Befehl verwendet das `Invoke-Command` Cmdlet, um einen `Start-Job` Befehl in der Sitzung auszuführen. Der Befehl im Auftrag ruft alle Ereignisse im Systemereignisprotokoll ab. Das resultierende Auftrags Objekt wird in der `$j` Variablen gespeichert.

Mit dem dritten Befehl wird der Auftrag beendet. Er verwendet das `Invoke-Command` Cmdlet, um einen `Stop-Job` Befehl in der **PSSession** auf Server01 auszuführen. Da die Auftrags Objekte in `$j` , einer Variablen auf dem lokalen Computer, gespeichert werden, verwendet der Befehl den using-bereichsmodifizierer, um `$j` als lokale Variable zu identifizieren.
Weitere Informationen zum using-bereichsmodifizierer finden Sie unter [about_Remote_Variables](about/about_Remote_Variables.md).

Wenn der Befehl abgeschlossen ist, wird der Auftrag beendet und die **PSSession** in `$s` steht zur Verwendung zur Verfügung.

### Beispiel 2: Abbrechen eines Hintergrund Auftrags

```powershell
Stop-Job -Name "Job1"
```

Dieser Befehl beendet den Hintergrundauftrag Job1.

### Beispiel 3: mehrere Hintergrund Aufträge werden beendet.

```powershell
Stop-Job -Id 1, 3, 4
```

Mit diesem Befehl werden drei Aufträge beendet.
Sie werden anhand der ID identifiziert.

### Beispiel 4: alle Hintergrund Aufträge werden beendet

```powershell
Get-Job | Stop-Job
```

Mit diesem Befehl werden alle Hintergrundaufträge im in der aktuellen Sitzung beendet.

### Beispiel 5: Abbrechen aller blockierten Hintergrund Aufträge

```powershell
Stop-Job -State Blocked
```

Dieser Befehl beendet alle Aufträge, die blockiert sind.

### Beispiel 6: Beenden eines Auftrags mit einer Instanz-ID

```powershell
Get-Job | Format-Table ID, Name, Command, @{Label="State";Expression={$_.JobStateInfo.State}},
InstanceID -Auto
```

```Output
Id Name Command                 State  InstanceId
-- ---- -------                 -----  ----------
1 Job1 start-service schedule Running 05abb67a-2932-4bd5-b331-c0254b8d9146
3 Job3 start-service schedule Running c03cbd45-19f3-4558-ba94-ebe41b68ad03
5 Job5 get-service s*         Blocked e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

```powershell
Stop-Job -InstanceId e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

Diese Befehle veranschaulichen die Beendigung eines Auftrags basierend auf der Instanz-ID.

Der erste Befehl verwendet das `Get-Job` Cmdlet, um die Aufträge in der aktuellen Sitzung zu erhalten. Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Aufträge an einen `Format-Table` Befehl zu senden, der eine Tabelle mit den angegebenen Eigenschaften jedes Auftrags anzeigt. Die Tabelle enthält die Instanz-ID für jeden Auftrag. Er verwendet eine berechnete Eigenschaft, um den Auftragsstatus anzuzeigen.

Der zweite Befehl verwendet einen `Stop-Job` Befehl, der über den **InstanceId-** Parameter verfügt, um einen ausgewählten Auftrag zu unterbinden.

### Beispiel 7: Abbrechen eines Auftrags auf einem Remote Computer

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

Dieses Beispiel zeigt, wie das `Stop-Job` Cmdlet verwendet wird, um einen Auftrag anzuhalten, der auf einem Remote Computer ausgeführt wird.

Da der Auftrag mithilfe des **AsJob** -Parameters des `Invoke-Command` Cmdlets gestartet wurde, befindet sich das Auftrags Objekt auf dem lokalen Computer, obwohl der Auftrag auf dem Remote Computer ausgeführt wird. Daher können Sie einen lokalen Befehl verwenden, `Stop-Job` um den Auftrag zu unterbinden.

Der erste Befehl verwendet das `Invoke-Command` Cmdlet, um einen Hintergrund Auftrag auf dem Server01-Computer zu starten. Der Befehl verwendet den **AsJob** -Parameter, um den Remotebefehl als Hintergrundauftrag auszuführen.

Dieser Befehl gibt ein Auftrags Objekt zurück, bei dem es sich um das gleiche Auftrags Objekt handelt, das vom `Start-Job` Cmdlet zurückgegeben wird.
Der Befehl speichert das Auftrags Objekt in der `$j` Variablen.

Der zweite Befehl verwendet einen Pipeline Operator, um den Auftrag in der `$j` Variablen an zu senden `Stop-Job` . Der Befehl verwendet den **passthru** -Parameter, um `Stop-Job` ein Auftrags Objekt zurückzugeben. Die Auftrags Objekt Anzeige bestätigt, dass der Status des Auftrags beendet wurde.

Weitere Informationen zu Remotehintergrundaufträgen finden Sie unter „about_Remote_Jobs“.

## PARAMETERS

### -Filter

Gibt eine Hash Tabelle mit Bedingungen an. Dieses Cmdlet beendet Aufträge, die alle Bedingungen erfüllen.
Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.

Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen. Sie funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des `Start-Job` Cmdlets. Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### -Id

Gibt die IDs von Aufträgen an, die von diesem Cmdlet beendet werden. Der Standardwert ist alle Aufträge in der aktuellen Sitzung.

Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert. Es ist leichter zu merken und einzugeben als die Instanz-ID, Sie ist jedoch nur in der aktuellen Sitzung eindeutig. Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben. Um die ID eines Auftrags zu ermitteln, geben Sie ein `Get-Job` .

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Gibt die Instanz-IDs von Aufträgen an, die von diesem Cmdlet angehalten werden. Standardmäßig werden alle Aufträge fortgesetzt.

Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert. Um die Instanz-ID eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Auftrag

Gibt die Aufträge an, die von diesem Cmdlet beendet werden. Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden. Sie können auch einen Pipeline Operator verwenden, um Aufträge an das `Stop-Job` Cmdlet zu übermitteln. Standardmäßig `Stop-Job` Löscht alle Aufträge, die in der aktuellen Sitzung gestartet wurden.

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

Gibt die anzeigen Amen von Aufträgen an, die von diesem Cmdlet beendet werden. Geben Sie die Auftragsnamen in eine kommagetrennte Liste ein, oder verwenden Sie Platzhalterzeichen (*), um ein Auftragsnamensmuster einzugeben. Standardmäßig werden `Stop-Job` alle Aufträge, die in der aktuellen Sitzung erstellt wurden, beendet.

Da der Anzeige Name nicht unbedingt eindeutig ist, verwenden Sie die Parameter " **WhatIf** " und " **Confirm** ", wenn Sie Aufträge nach Namen beenden.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -PassThru

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten. Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

### -State

Gibt einen Auftragsstatus an. Dieses Cmdlet beendet nur Aufträge im angegebenen Zustand. Zulässige Werte für diesen Parameter:

- NotStarted
- Wird ausgeführt
- Abgeschlossen
- Fehler
- Beendet
- Blockiert
- Ausgesetzt
- Getrennt
- Wird angehalten
- Wird beendet

Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](/dotnet/api/system.management.automation.jobstate).

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.

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

### -WhatIf

Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.
Das Cmdlet wird nicht ausgeführt.

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

### System. Management. Automation. remotingjob

Sie können ein Auftrags Objekt an dieses Cmdlet weiterreichen.

## AUSGABEN

### None, System. Management. Automation. psremotingjob

Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den **passthru** -Parameter angeben. Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

## HINWEISE

## VERWANDTE LINKS

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Wait-Job](Wait-Job.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)

[about_Remote_Variables](About/about_Remote_Variables.md)

[about_Jobs](About/about_Jobs.md)

[about_Scopes](About/about_scopes.md)
