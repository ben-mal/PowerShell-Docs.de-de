---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: 2eeacf8703dbe0f662d0b26d405c605d21c2b84e
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390353"
---
# Wait-Job

## ZUSAMMENFASSUNG
Unterdrückt die Eingabeaufforderung, bis ein oder alle PowerShell-Hintergrund Aufträge, die in der Sitzung ausgeführt werden, abgeschlossen sind.

## SYNTAX

### Sessionidparameterset (Standard)

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### Jobparameterset

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### Nameparameterset

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### Instanceidparameterset

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### Stateparameterset

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### Filterparameterset

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

Das- `Wait-Job` Cmdlet wartet darauf, dass PowerShell-Hintergrund Aufträge abgeschlossen sind, bevor die Eingabeaufforderung angezeigt wird. Sie können warten, bis ein Hintergrundauftrag abgeschlossen ist, oder bis alle Hintergrundaufträge abgeschlossen sind, und Sie können eine maximale Wartezeit für den Auftrag festlegen.

Wenn die Befehle im Auftrag fertig sind, `Wait-Job` zeigt die Eingabeaufforderung an und gibt ein Auftrags Objekt zurück, damit Sie es an einen anderen Befehl übergeben können.

Sie können das `Wait-Job` Cmdlet verwenden, um auf Hintergrund Aufträge zu warten, z. b. solche, die mit dem `Start-Job` Cmdlet oder dem **AsJob** -Parameter des `Invoke-Command` Cmdlets gestartet wurden. Weitere Informationen zu Windows PowerShell-Hintergrundaufträgen finden Sie unter [about_Jobs](./about/about_Jobs.md).

Ab Windows PowerShell 3,0 `Wait-Job` wartet das Cmdlet auch auf benutzerdefinierte Auftrags Typen, z. b. Workflow Aufträge und Instanzen geplanter Aufträge. Damit `Wait-Job` auf Aufträge eines bestimmten Typs gewartet werden kann, müssen Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung importieren, bevor Sie das `Get-Job` Cmdlet entweder mithilfe des-Cmdlets oder mithilfe des-Cmdlets oder mithilfe des-Cmdlets `Import-Module` im Modul ausführen. Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.

## BEISPIELE

### Beispiel 1: warten auf alle Aufträge

```powershell
Get-Job | Wait-Job
```

Dieser Befehl wartet, bis alle Hintergrund Aufträge, die in der Sitzung ausgeführt werden, beendet werden.

### Beispiel 2: warten auf Aufträge, die auf Remote Computern gestartet werden, mithilfe von Start-Job

```powershell
$s = New-PSSession Server01, Server02, Server03
Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
$done.Count
```

```Output
3
```

In diesem Beispiel wird gezeigt, wie das `Wait-Job` Cmdlet mit Aufträgen verwendet wird, die auf Remote Computern mithilfe des `Start-Job` Cmdlets gestartet wurden. `Start-Job`Der- `Wait-Job` Befehl und der-Befehl werden mithilfe des-Cmdlets an den Remote Computer übermittelt `Invoke-Command` .

In diesem Beispiel `Wait-Job` wird verwendet, um zu bestimmen, ob ein `Get-Date` Befehl, der als Hintergrund Auftrag auf drei verschiedenen Computern ausgeführt wird, abgeschlossen ist.

Mit dem ersten Befehl wird eine Windows PowerShell-Sitzung ( **PSSession** ) auf jedem der drei Remote Computer erstellt und in der `$s` Variablen gespeichert.

Der zweite Befehl verwendet `Invoke-Command` , um `Start-Job` in jeder der drei Sitzungen in auszuführen `$s` .
Alle Aufträge werden als date1 bezeichnet.

Der dritte Befehl verwendet `Invoke-Command` , um auszuführen `Wait-Job` . Dieser Befehl wartet, bis die date1-Aufträge auf den einzelnen Computern abgeschlossen sind. Die resultierende Auflistung (Array) der Auftrags Objekte wird in der `$done` Variablen gespeichert.

Der vierte Befehl verwendet die **count** -Eigenschaft des Arrays von Auftrags Objekten in der `$done` Variablen, um zu bestimmen, wie viele der Aufträge abgeschlossen sind.

### Beispiel 3: bestimmen, wann der erste Hintergrund Auftrag abgeschlossen ist

```powershell
$s = New-PSSession (Get-Content Machines.txt)
$c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

In diesem Beispiel wird der **any** -Parameter verwendet `Wait-Job` , um zu bestimmen, wann die erste der vielen Hintergrund Aufträge, die in der aktuellen Sitzung ausgeführt werden, abgeschlossen sind. Außerdem wird gezeigt, wie das `Wait-Job` Cmdlet verwendet wird, um zu warten, bis die Remote Aufträge abgeschlossen sind.

Der erste Befehl erstellt eine **PSSession** auf allen Computern, die in der Machines.txt-Datei aufgelistet sind, und speichert die **PSSession** -Objekte in der `$s` Variablen. Der Befehl verwendet das `Get-Content` Cmdlet, um den Inhalt der Datei zu erhalten. Der `Get-Content` Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er vor dem Befehl ausgeführt wird `New-PSSession` .

Mit dem zweiten Befehl `Get-EventLog` wird eine Befehls Zeichenfolge in Anführungszeichen in der `$c` Variablen gespeichert.

Der dritte Befehl verwendet das `Invoke-Command` Cmdlet, um `Start-Job` in jeder der Sitzungen in auszuführen `$s` .
Der `Start-Job` Befehl startet einen Hintergrund Auftrag, der den `Get-EventLog` Befehl in der `$c` Variablen ausführt.

Der Befehl verwendet den **using** -bereichsmodifizierer, um anzugeben, dass die `$c` Variable auf dem lokalen Computer definiert wurde. Der **Using** -Bereichsbezeichner wurde in Windows PowerShell 3.0 eingeführt. Weitere Informationen zum using-bereichsmodifizierer finden **Sie** unter [about_Remote_Variables](./about/about_Remote_Variables.md).

Der vierte Befehl verwendet `Invoke-Command` , um einen `Wait-Job` Befehl in den Sitzungen auszuführen. Er verwendet den **any** -Parameter, um zu warten, bis der erste Auftrag auf den Remote Computern abgeschlossen ist.

### Beispiel 4: Festlegen einer Wartezeit für Aufträge auf Remote Computern

```powershell
$s = New-PSSession Server01, Server02, Server03
$jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
$done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

In diesem Beispiel wird gezeigt, wie der **Timeout** -Parameter von verwendet wird `Wait-Job` , um eine maximale Wartezeit für die Aufträge festzulegen, die auf Remote Computern ausgeführt werden.

Der erste Befehl erstellt eine **PSSession** auf jedem der drei Remote Computer (Server01, Server02 und Server03) und speichert die **PSSession** -Objekte in der `$s` Variablen.

Der zweite Befehl verwendet `Invoke-Command` , um `Start-Job` in jedem der **PSSession** -Objekte in auszuführen `$s` . Die resultierenden Auftrags Objekte werden in der `$jobs` Variablen gespeichert.

Der dritte Befehl verwendet `Invoke-Command` , um `Wait-Job` in jeder der Sitzungen in auszuführen `$s` . Der `Wait-Job` Befehl bestimmt, ob alle Befehle innerhalb von 30 Sekunden abgeschlossen wurden. Er verwendet den **Timeout** -Parameter mit einem Wert von 30, um die maximale Wartezeit festzulegen, und speichert dann die Ergebnisse des Befehls in der `$done` Variablen.

In diesem Fall wurde nur der Befehl auf dem Computer Server02 nach 30 Sekunden abgeschlossen. `Wait-Job` beendet den warte Vorgang, zeigt die Eingabeaufforderung an und gibt das Objekt zurück, das den abgeschlossenen Auftrag darstellt.

Die- `$done` Variable enthält ein Auftrags Objekt, das den Auftrag darstellt, der auf Server02 ausgeführt wird.

### Beispiel 5: warten, bis einer von mehreren Aufträgen abgeschlossen ist

```powershell
Wait-Job -id 1,2,5 -Any
```

Dieser Befehl identifiziert drei Aufträge anhand ihrer IDs und wartet, bis eine davon abgeschlossen ist.
Die Eingabeaufforderung wird zurückgegeben, wenn der erste Auftrag abgeschlossen ist.

### Beispiel 6: warten auf einen Zeitraum und anschließendes fortsetzen des Auftrags im Hintergrund

```powershell
Wait-Job -Name "DailyLog" -Timeout 120
```

Dieser Befehl wartet 120 Sekunden (zwei Minuten), bis der dailylog-Auftrag abgeschlossen ist. Wenn der Auftrag nicht innerhalb der nächsten zwei Minuten abgeschlossen wird, wird die Eingabeaufforderung trotzdem zurückgegeben, und der Auftrag wird weiterhin im Hintergrund ausgeführt.

### Beispiel 7: warten auf einen Auftrag nach Name

```powershell
Wait-Job -Name "Job3"
```

Dieser Befehl verwendet den Auftrags Namen, um den Auftrag zu identifizieren, für den gewartet werden soll.

### Beispiel 8: warten auf Aufträge auf dem lokalen Computer, die mit Start-Job gestartet wurden

```powershell
$j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
$j | Wait-Job
```

In diesem Beispiel wird gezeigt, wie das `Wait-Job` Cmdlet mit Aufträgen verwendet wird, die auf dem lokalen Computer mithilfe von gestartet werden `Start-Job` .

Diese Befehle starten einen Auftrag, der die Windows PowerShell-Skriptdateien abruft, die in der letzten Woche hinzugefügt oder aktualisiert wurden.

Der erste Befehl verwendet `Start-Job` , um einen Hintergrund Auftrag auf dem lokalen Computer zu starten. Der Auftrag führt einen `Get-ChildItem` Befehl aus, der alle Dateien mit der Dateinamenerweiterung ". ps1" abruft, die in der letzten Woche hinzugefügt oder aktualisiert wurden.

Der dritte Befehl verwendet `Wait-Job` , um zu warten, bis der Auftrag abgeschlossen ist. Wenn der Auftrag abgeschlossen ist, zeigt der Befehl das Auftrags Objekt an, das Informationen über den Auftrag enthält.

### Beispiel 9: warten auf Aufträge, die auf Remote Computern gestartet werden, mithilfe von Invoke-Command

```powershell
$s = New-PSSession Server01, Server02, Server03
$j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
$j | Wait-Job
```

Dieses Beispiel zeigt `Wait-Job` die Verwendung von mit Aufträgen, die auf Remote Computern mithilfe des **AsJob** -Parameters von gestartet wurden `Invoke-Command` . Wenn Sie **AsJob** verwenden, wird der Auftrag auf dem lokalen Computer erstellt, und die Ergebnisse werden automatisch an den lokalen Computer zurückgegeben, obwohl der Auftrag auf den Remote Computern ausgeführt wird.

In diesem Beispiel `Wait-Job` wird verwendet, um zu bestimmen, ob ein `Get-Process` Befehl, der in Sitzungen auf drei Remote Computern ausgeführt wird, abgeschlossen ist.

Der erste Befehl erstellt **PSSession** -Objekte auf drei Computern und speichert Sie in der `$s` Variablen.

Der zweite Befehl verwendet `Invoke-Command` , um `Get-Process` in jeder der drei Sitzungen in auszuführen `$s` .
Der Befehl verwendet den **AsJob** -Parameter, um den Befehl asynchron als Hintergrund Auftrag auszuführen. Der Befehl gibt ein Auftrags Objekt zurück, genau wie die Aufträge, die mithilfe von gestartet `Start-Job` wurden, und das Auftrags Objekt wird in der `$j` Variablen gespeichert.

Der dritte Befehl verwendet einen Pipeline Operator ( `|` ), um das Auftrags Objekt an `$j` das `Wait-Job` Cmdlet zu senden. Ein `Invoke-Command` Befehl ist in diesem Fall nicht erforderlich, da sich der Auftrag auf dem lokalen Computer befindet.

### Beispiel 10: warten auf einen Auftrag mit einer ID

```powershell
Get-Job
```

```Output
Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where
```

```powershell
Wait-Job -Id 1
```

Dieser Befehl wartet auf den Auftrag mit dem ID-Wert 1.

## PARAMETERS

### -Beliebig

Gibt an, dass dieses Cmdlet die Eingabeaufforderung anzeigt und das Auftrags Objekt zurückgibt, wenn ein Auftrag abgeschlossen ist. Standardmäßig `Wait-Job` wartet, bis alle angegebenen Aufträge vollständig sind, bevor die Eingabeaufforderung angezeigt wird.

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

### -Filter

Gibt eine Hash Tabelle mit Bedingungen an. Dieses Cmdlet wartet auf Aufträge, die alle Bedingungen in der Hash Tabelle erfüllen. Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.

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

### -Force

Gibt an, dass dieses Cmdlet weiterhin auf Aufträge im Zustand "angehalten" oder "getrennt" wartet. In der Standardeinstellung `Wait-Job` gibt zurück oder beendet den warte Vorgang, wenn Aufträge einen der folgenden Zustände aufweisen:

- Abgeschlossen
- Fehler
- Beendet
- Ausgesetzt
- Getrennt

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### -Id

Gibt ein Array von IDs von Aufträgen an, die von diesem Cmdlet gewartet werden.

Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert. Es ist leichter zu merken und einzugeben als die Instanz-ID, Sie ist jedoch nur in der aktuellen Sitzung eindeutig. Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben. Um die ID eines Auftrags zu ermitteln, geben Sie ein `Get-Job` .

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

Gibt ein Array von Instanz-IDs von Aufträgen an, für die dieses Cmdlet wartet. Standardmäßig werden alle Aufträge fortgesetzt.

Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert. Um die Instanz-ID eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .

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

Gibt die Aufträge an, die dieses Cmdlet wartet. Geben Sie eine Variable ein, die Auftragsobjekte bzw. einen Befehl enthält, der die Auftragsobjekte abruft. Sie können auch einen Pipeline Operator verwenden, um Auftrags Objekte an das `Wait-Job` Cmdlet zu senden. Standardmäßig `Wait-Job` wartet auf alle Aufträge, die in der aktuellen Sitzung erstellt wurden.

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

Gibt die anzeigen Amen von Aufträgen an, die von diesem Cmdlet gewartet werden.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State

Gibt einen Auftragsstatus an. Dieses Cmdlet wartet nur auf Aufträge im angegebenen Zustand. Zulässige Werte für diesen Parameter:

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
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Timeout

Gibt die maximale Wartezeit für jeden Hintergrund Auftrag in Sekunden an. Der Standardwert-1 gibt an, dass das Cmdlet wartet, bis der Auftrag abgeschlossen ist. Die zeitliche Steuerung beginnt, wenn Sie den Befehl übermitteln `Wait-Job` , nicht den `Start-Job` Befehl.

Wenn diese Zeit abgelaufen ist, endet der Wartevorgang, und die Befehlseingabeaufforderung wird wieder angezeigt, auch wenn der Auftrag noch läuft. Der Befehl zeigt keine Fehlermeldung an.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. remotingjob

Sie können ein Auftrags Objekt an dieses Cmdlet weiterreichen.

## AUSGABEN

### System. Management. Automation. psremotingjob

Dieses Cmdlet gibt Auftrags Objekte zurück, die die abgeschlossenen Aufträge darstellen. Wenn der Warte Vorgang beendet wird, weil der Wert des **Timeout** -Parameters überschritten wird, gibt keine- `Wait-Job` Objekte zurück.

## HINWEISE

In der Standardeinstellung `Wait-Job` gibt zurück oder beendet den warte Vorgang, wenn Aufträge einen der folgenden Zustände aufweisen:

- Abgeschlossen
- Fehler
- Beendet
- Ausgesetzt
- Getrennt an Direct, `Wait-Job` um weiterhin auf angehaltene und getrennte Aufträge zu warten, verwenden Sie den **Force** -Parameter.

## VERWANDTE LINKS

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)
