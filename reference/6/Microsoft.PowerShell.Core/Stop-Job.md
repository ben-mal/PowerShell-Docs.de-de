---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job
ms.openlocfilehash: 5b023efa2c1545da574f447b8542bfbfe9b5d861
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217156"
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

Das Cmdlet " **Stopp-Job** " beendet PowerShell-Hintergrund Aufträge, die gerade ausgeführt werden.
Mit diesem Cmdlet können Sie alle Aufträge oder ausgewählte Aufträge auf der Grundlage ihres Namens, der ID, der Instanz-ID oder des Zustands abbrechen oder indem Sie ein Auftrags Objekt an " **beendet-Job** " übergeben.

Sie können " **stopjob** " verwenden, um Hintergrund Aufträge zu verhindern, z. b. solche, die mit dem Cmdlet "Start-Job" oder dem *AsJob* -Parameter eines beliebigen Cmdlets gestartet wurden.
Wenn Sie einen Hintergrund Auftrag beenden, schließt PowerShell alle Aufgaben ab, die in der Auftrags Warteschlange ausstehend sind, und beendet dann den Auftrag.
Keine neuen Vorgänge werden in die Warteschlange hinzugefügt, nachdem dieser Befehl gesendet wird.

Mit diesem Cmdlet werden die Hintergrundaufträge nicht gelöscht.
Zum Löschen eines Auftrags verwenden Sie das Cmdlet "Remove-Job".

Ab Windows PowerShell 3,0 stoppt " **Stopp-Job** " auch benutzerdefinierte Auftrags Typen, z. b. Workflow Aufträge und Instanzen von geplanten Aufträgen.
Um " **beendet-Job** " zum Abbrechen eines Auftrags mit einem benutzerdefinierten Auftragstyp zu aktivieren, müssen Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung importieren, bevor Sie einen Befehl zum **Abbrechen eines Auftrags** ausführen, indem Sie entweder das Cmdlet "Import-Module" verwenden oder ein Cmdlet im Modul verwenden.
Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.

## BEISPIELE

### Beispiel 1: Abbrechen eines Auftrags auf einem Remote Computer mit Invoke-Command

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

Dieses Beispiel zeigt, wie Sie das **Stop-Job** -Cmdlet verwenden, um einen Auftrag zu beenden, der auf einem Remotecomputer ausgeführt wird.

Da der Auftrag mithilfe des Invoke-Command-Cmdlets gestartet wurde, um einen **Start-Job-** Befehl Remote auszuführen, wird das Auftrags Objekt auf dem Remote Computer gespeichert.
Sie müssen einen anderen Befehl zum **aufrufen** eines Auftrags verwenden, um einen Befehl zum **Abbrechen** von Aufträgen Remote auszuführen.
Weitere Informationen zu Remotehintergrundaufträgen finden Sie unter „about_Remote_Jobs“.

Der erste Befehl erstellt eine PowerShell-Sitzung ( **PSSession** ) auf dem Server01-Computer und speichert dann das Sitzungs Objekt in der $s Variable.
Der Befehl verwendet die Anmeldeinformationen eines Domänenadministrators.

Der zweite Befehl verwendet das **Invoke-Command** -Cmdlet zum Ausführen eines **Start-Job** -Befehls in der Sitzung.
Der Befehl im Auftrag ruft alle Ereignisse im Systemereignisprotokoll ab.
Das resultierende Auftragsobjekt wird in der $j-Variablen gespeichert.

Mit dem dritten Befehl wird der Auftrag beendet.
Er verwendet das Cmdlet " **Aufruf-Command** ", um einen Befehl zum **Abbrechen eines Auftrags** in der **PSSession** auf Server01 auszuführen.
Da die Auftragsobjekte in $j, einer Variablen auf dem lokalen Computer, gespeichert werden, verwendet der Befehl den „Using“-Bereichsbezeichner, um $j als lokale Variable zu identifizieren.
Weitere Informationen zum using-bereichsmodifizierer finden Sie unter [about_Remote_Variables](about/about_Remote_Variables.md).

Wenn der Befehl abgeschlossen ist, wird der Auftrag beendet und die **PSSession** in $s zur Verwendung verfügbar.

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

Der erste Befehl verwendet das Cmdlet "Get-Job", um die Aufträge in der aktuellen Sitzung zu erhalten.
Der Befehl verwendet einen Pipeline Operator (|), um die Aufträge an einen Format-Table Befehl zu senden, der eine Tabelle mit den angegebenen Eigenschaften jedes Auftrags anzeigt.
Die Tabelle enthält die Instanz-ID für jeden Auftrag.
Er verwendet eine berechnete Eigenschaft, um den Auftragsstatus anzuzeigen.

Der zweite Befehl verwendet einen Befehl zum **Abbrechen eines Auftrags** , der über den *InstanceId-* Parameter verfügt, um einen ausgewählten Auftrag zu unterbinden.

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

Dieses Beispiel zeigt, wie Sie das **Stop-Job** -Cmdlet verwenden, um einen Auftrag zu beenden, der auf einem Remotecomputer ausgeführt wird.

Da der Auftrag mithilfe des *AsJob* -Parameters des Cmdlets " **Aufruf-Command** " gestartet wurde, befindet sich das Auftrags Objekt auf dem lokalen Computer, obwohl der Auftrag auf dem Remote Computer ausgeführt wird.
Daher können Sie einen lokalen Befehl zum **Abbrechen eines Auftrags** verwenden, um den Auftrag zu unterbinden.

Der erste Befehl verwendet das **Invoke-Command** -Cmdlet, um einen Hintergrundauftrag auf dem Computer Server01 zu starten.
Der Befehl verwendet den *AsJob* -Parameter, um den Remotebefehl als Hintergrundauftrag auszuführen.

Dieser Befehl gibt ein Auftrags Objekt zurück, bei dem es sich um das gleiche Auftrags Objekt handelt, das vom **Start-Job-** Cmdlet zurückgegeben wird.
Der Befehl speichert das Auftragsobjekt in der $j-Variablen.

Der zweite zweite Befehl verwendet einen Pipelineoperator, um den Auftrag in der $j-Variablen an „Stop-Job“ zu senden.
Der Befehl verwendet den *PassThru* -Parameter, um **Stop-Job** anzuweisen, ein Auftragsobjekt zurückgegeben.
Die Auftrags Objekt Anzeige bestätigt, dass der Status des Auftrags beendet wurde.

Weitere Informationen zu Remotehintergrundaufträgen finden Sie unter „about_Remote_Jobs“.

## PARAMETERS

### -Filter

Gibt eine Hash Tabelle mit Bedingungen an.
Dieses Cmdlet beendet Aufträge, die alle Bedingungen erfüllen.
Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.

Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.
Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .
Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.

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

Gibt die IDs von Aufträgen an, die von diesem Cmdlet beendet werden.
Der Standardwert ist alle Aufträge in der aktuellen Sitzung.

Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.
Es ist leichter zu merken und einzugeben als die Instanz-ID, Sie ist jedoch nur in der aktuellen Sitzung eindeutig.
Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.
Um die ID eines Auftrags zu ermitteln, geben Sie ein `Get-Job` .

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

Gibt die Instanz-IDs von Aufträgen an, die von diesem Cmdlet angehalten werden.
Standardmäßig werden alle Aufträge fortgesetzt.

Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.
Um die Instanz-ID eines Auftrags zu ermitteln, verwenden Sie „Get-Job“.

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

Gibt die Aufträge an, die von diesem Cmdlet beendet werden.
Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden.
Sie können auch einen Pipeline Operator verwenden, um Aufträge an das Cmdlet "Set **-Job** " zu übermitteln.
Standardmäßig löscht " **beendet-Job** " alle Aufträge, die in der aktuellen Sitzung gestartet wurden.

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

Gibt die anzeigen Amen von Aufträgen an, die von diesem Cmdlet beendet werden.
Geben Sie die Auftragsnamen in eine kommagetrennte Liste ein, oder verwenden Sie Platzhalterzeichen (*), um ein Auftragsnamensmuster einzugeben.
Standardmäßig beendet " **Stopp-Job** " alle Aufträge, die in der aktuellen Sitzung erstellt wurden.

Da der Anzeige Name nicht unbedingt eindeutig ist, verwenden Sie die Parameter " *WhatIf* " und " *Confirm* ", wenn Sie Aufträge nach Namen beenden.

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

Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.
Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.

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

Gibt einen Auftragsstatus an.
Dieses Cmdlet beendet nur Aufträge im angegebenen Zustand.
Zulässige Werte für diesen Parameter:

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

Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in der MSDN Library.

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

Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den *passthru* -Parameter angeben.
Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.

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
