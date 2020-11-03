---
external help file: ThreadJob.dll-Help.xml
Locale: en-US
Module Name: ThreadJob
ms.date: 01/28/2020
online version: https://docs.microsoft.com/powershell/module/threadjob/start-threadjob?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ThreadJob
ms.openlocfilehash: 9ac0570a5e26de47438a48817785836348de19cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212612"
---
# Start-ThreadJob

## ZUSAMMENFASSUNG
Erstellt Hintergrund Aufträge, die dem- `Start-Job` Cmdlet ähneln.

## SYNTAX

### ScriptBlock

```
Start-ThreadJob [-ScriptBlock] <ScriptBlock> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### FilePath

```
Start-ThreadJob [-FilePath] <String> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`Start-ThreadJob` erstellt Hintergrund Aufträge, die dem- `Start-Job` Cmdlet ähneln. Der Hauptunterschied besteht darin, dass die erstellten Aufträge in separaten Threads innerhalb des lokalen Prozesses ausgeführt werden. Standardmäßig verwenden die Aufträge das aktuelle Arbeitsverzeichnis des Aufrufers, der den Auftrag gestartet hat.

Das Cmdlet unterstützt auch einen **throttlelimit** -Parameter, um die Anzahl der gleichzeitig laufenden Aufträge zu begrenzen. Wenn mehr Aufträge gestartet werden, werden Sie in die Warteschlange eingereiht und warten, bis die aktuelle Anzahl der Aufträge unter die Drosselungs Grenze fällt.

## BEISPIELE

### Beispiel 1: Erstellen von Hintergrund Aufträgen mit einem ThreadLimit von 2

```powershell
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } } -ThrottleLimit 2
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Get-Job
```

```Output
Id   Name   PSJobTypeName   State        HasMoreData   Location     Command
--   ----   -------------   -----        -----------   --------     -------
1    Job1   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
2    Job2   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
3    Job3   ThreadJob       NotStarted   False         PowerShell   1..100 | % { sleep 1;...
```

### Beispiel 2: Vergleichen der Leistung von Start-Job und Start-ThreadJob

Dieses Beispiel zeigt den Unterschied zwischen `Start-Job` und `Start-ThreadJob` . Die Aufträge führen das `Start-Sleep` Cmdlet für eine Sekunde aus. Da die Aufträge parallel ausgeführt werden, beträgt die Gesamt Ausführungszeit ungefähr 1 Sekunde, zuzüglich der Zeit, die zum Erstellen der Aufträge benötigt wird.

```powershell
# start five background jobs each running 1 second
Measure-Command {1..5 | % {Start-Job {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
Measure-Command {1..5 | % {Start-ThreadJob {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
```

```Output
TotalSeconds
------------
   5.7665849
   1.5735008
```

Nachdem Sie 1 Sekunde zur Ausführungszeit subtrahieren, können Sie sehen, dass die `Start-Job` Erstellung von fünf Aufträgen ungefähr 4,8 Sekunden dauert. `Start-ThreadJob` ist acht Mal schneller und nimmt ungefähr 0,6 Sekunden Zeit in Anspruch, fünf Aufträge zu erstellen. Die Ergebnisse können in Ihrer Umgebung variieren, die relative Verbesserung sollte jedoch identisch sein.

### Beispiel 3: Erstellen von Aufträgen mithilfe von Inputobject

In diesem Beispiel verwendet der Skriptblock die- `$input` Variable, um Eingaben vom **Inputobject** -Parameter zu empfangen. Dies kann auch durch Weiterleiten von Objekten an erfolgen `Start-ThreadJob` .

```powershell
$j = Start-ThreadJob -InputObject (Get-Process pwsh) -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

```powershell
$j = Get-Process pwsh | Start-ThreadJob -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

## PARAMETERS

### -Argumentlist

Gibt ein Array von Argumenten oder Parameterwerten für das Skript an, das durch die Parameter " **FilePath** " oder " **ScriptBlock** " angegeben wird.

**Argumentlist** muss der letzte Parameter in der Befehlszeile sein. Alle Werte, die dem Parameternamen folgen, sind in der Argumentliste interpretiertes Werte.

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Gibt eine Skriptdatei an, die als Hintergrund Auftrag ausgeführt werden soll. Geben Sie den Pfad und den Dateinamen des Skripts ein. Das Skript muss sich auf dem lokalen Computer oder in einem Ordner befinden, auf den der lokale Computer zugreifen kann.

Wenn Sie diesen Parameter verwenden, konvertiert PowerShell den Inhalt der angegebenen Skriptdatei in einen Skriptblock und führt den Skriptblock als Hintergrund Auftrag aus.

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Initializationscript

Gibt Befehle an, die vor dem Starten des Auftrags ausgeführt werden. Schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen.

Verwenden Sie diesen Parameter zum Vorbereiten der Sitzung, in der der Auftrag ausgeführt wird. Beispielsweise können Sie damit Funktionen und Module zur Sitzung hinzufügen.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die Objekte an, die als Eingabe für den Skriptblock verwendet werden. Außerdem werden Pipeline Eingaben ermöglicht. Verwenden `$input` Sie die automatische Variable im Skriptblock, um auf die Eingabe Objekte zuzugreifen.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

Gibt einen Anzeigenamen für den neuen Auftrag an. Sie können den Namen verwenden, um den Auftrag für andere Auftrags-Cmdlets wie z `Stop-Job` . b. das Cmdlet zu identifizieren.

Der standardmäßige Anzeige Name lautet "Job #", wobei "#" eine Ordinalzahl ist, die für jeden Auftrag erhöht wird.

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

### -ScriptBlock

Gibt die im Hintergrundauftrag auszuführenden Befehle an. Schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen. Verwenden `$Input` Sie die automatische Variable, um auf den Wert des **Inputobject** -Parameters zuzugreifen. Dieser Parameter ist erforderlich.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Streaminghost

Dieser Parameter stellt eine Thread sichere Möglichkeit bereit, um zuzulassen, dass `Write-Host` die Ausgabe direkt zum übergebenen **pshost** -Objekt weitergeleitet wird. Ohne diesen Vorgang wird `Write-Host` die Ausgabe an die Datenstrom Sammlung der Auftrags Informationen weitergeleitet und wird erst dann in einer Host Konsole angezeigt, wenn die Ausführung der Aufträge abgeschlossen ist.

```yaml
Type: System.Management.Automation.Host.PSHost
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Dieser Parameter schränkt die Anzahl der Aufträge ein, die gleichzeitig ausgeführt werden. Wenn Aufträge gestartet werden, werden Sie in die Warteschlange eingereiht und warten, bis ein Thread im Thread Pool verfügbar ist, um den Auftrag auszuführen. Der Standard Grenzwert beträgt 5 Threads.

Die Thread Pool Größe ist für die PowerShell-Sitzung Global. Wenn Sie eine **throttlelimit** in einem Aufruf angeben, wird das Limit für nachfolgende Aufrufe in derselben Sitzung festgelegt.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

## AUSGABEN

### Threadjob. threadjob

## HINWEISE

## VERWANDTE LINKS

[Start-Job](../Microsoft.PowerShell.Core/Start-Job.md)

[Stop-Job](../Microsoft.PowerShell.Core/Stop-Job.md)

[Receive-Job](../Microsoft.PowerShell.Core/Receive-Job.md)

