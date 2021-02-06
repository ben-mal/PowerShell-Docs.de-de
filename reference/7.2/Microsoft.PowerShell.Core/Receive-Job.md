---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-job?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-Job
ms.openlocfilehash: 3a11bdb27f3fe16b7b66e82821a3ffe8fa5f6cfa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599637"
---
# Receive-Job

## ZUSAMMENFASSUNG
Ruft die Ergebnisse der PowerShell-Hintergrund Aufträge in der aktuellen Sitzung ab.

## SYNTAX

### Speicherort (Standard)

```
Receive-Job [-Job] <Job[]> [[-Location] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### Computername

```
Receive-Job [-Job] <Job[]> [[-ComputerName] <String[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### Sitzung

```
Receive-Job [-Job] <Job[]> [[-Session] <PSSession[]>] [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob]
 [-WriteEvents] [-WriteJobInResults] [<CommonParameters>]
```

### Nameparameterset

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Name] <String[]> [<CommonParameters>]
```

### Instanceidparameterset

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-InstanceId] <Guid[]> [<CommonParameters>]
```

### Sessionidparameterset

```
Receive-Job [-Keep] [-NoRecurse] [-Force] [-Wait] [-AutoRemoveJob] [-WriteEvents] [-WriteJobInResults]
 [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse von PowerShell-Hintergrund Aufträgen abgerufen, z. b. solche, die mit dem `Start-Job` Cmdlet oder dem **AsJob** -Parameter eines beliebigen Cmdlets gestartet wurden.
Sie können die Ergebnisse aller Aufträge abrufen oder Aufträge nach Name, ID, Instanz-ID, Computername, Speicherort oder Sitzung oder durch Senden eines Auftragsobjekts identifizieren.

Wenn Sie einen PowerShell-Hintergrund Auftrag starten, wird der Auftrag gestartet, aber die Ergebnisse werden nicht sofort angezeigt. Stattdessen gibt der Befehl ein Objekt zurück, das den Hintergrundauftrag darstellt.
Das Auftragsobjekt enthält nützliche Informationen zum Auftrag, jedoch nicht die Ergebnisse.
Mit dieser Methode können Sie die Arbeit in der Sitzung fortsetzen, während der Auftrag ausgeführt wird.
Weitere Informationen zu Hintergrund Aufträgen in PowerShell finden Sie unter [about_Jobs](./About/about_Jobs.md).

Mit dem- `Receive-Job` Cmdlet werden die Ergebnisse abgerufen, die von dem Zeitpunkt generiert wurden, an dem der `Receive-Job` Befehl übermittelt wird.
Wenn die Ergebnisse noch nicht erfüllt sind, können Sie zusätzliche Befehle ausführen, `Receive-Job` um die verbleibenden Ergebnisse zu erhalten.

Standardmäßig werden die Auftragsergebnisse aus dem System gelöscht, nachdem Sie sie erhalten haben, Sie können jedoch den **Keep**-Parameter verwenden, um die Ergebnisse zu speichern, damit Sie sie erneut empfangen können.
Um die Auftrags Ergebnisse zu löschen, führen Sie den `Receive-Job` Befehl ohne den **Keep** -Parameter erneut aus, schließen Sie die Sitzung, oder verwenden `Remove-Job` Sie das Cmdlet, um den Auftrag aus der Sitzung zu löschen.

Ab Windows PowerShell 3,0 ruft `Receive-Job` auch die Ergebnisse von benutzerdefinierten Auftrags Typen ab, wie z. b. Workflow Aufträge und Instanzen geplanter Aufträge.
Um `Receive-Job` die Ergebnisse eines benutzerdefinierten Auftrags Typs zu erhalten, importieren Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung, bevor ein `Receive-Job` Befehl ausgeführt wird, entweder mithilfe des- `Import-Module` Cmdlets oder mithilfe des-Cmdlets oder mithilfe eines Cmdlets im Modul.
Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.

## BEISPIELE

### Beispiel 1: Ergebnisse für einen bestimmten Auftrag erhalten

```powershell
$job = Start-Job -ScriptBlock {Get-Process}
Receive-Job -Job $job
```

Diese Befehle verwenden den **Job** -Parameter von `Receive-Job` , um die Ergebnisse eines bestimmten Auftrags zu erhalten.

Der erste Befehl startet einen Auftrag mit `Start-Job` und speichert das Auftrags Objekt in der `$job` Variablen.

Der zweite Befehl verwendet das `Receive-Job` Cmdlet, um die Ergebnisse des Auftrags zu erhalten.
Mit dem **Job**-Parameter wird der Auftrag angegeben.

### Beispiel 2: Verwenden des Keep-Parameters

```powershell
$job = Start-Job -ScriptBlock {Get-Service dhcp, fakeservice}
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

```powershell
$job | Receive-Job -Keep
```

```Output
Cannot find any service with service name 'fakeservice'.
    + CategoryInfo          : ObjectNotFound: (fakeservice:String) [Get-Service], ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.GetServiceCommand
    + PSComputerName        : localhost

Status   Name               DisplayName
------   ----               -----------
Running  dhcp               DHCP Client
```

In diesem Beispiel wird ein Auftrag in der `$job` -Variable gespeichert, und der Auftrag wird an das `Receive-Job` Cmdlet weitergeleitet. Der- `-Keep` Parameter wird auch verwendet, um zuzulassen, dass alle aggregierten Datenstrom Daten nach der ersten Ansicht erneut abgerufen werden.

### Beispiel 3: Ergebnisse mehrerer Hintergrund Aufträge erhalten

Wenn Sie den **AsJob** -Parameter von verwenden, `Invoke-Command` um einen Auftrag zu starten, wird das Auftrags Objekt auf dem lokalen Computer erstellt, auch wenn der Auftrag auf den Remote Computern ausgeführt wird.
Folglich verwenden Sie lokale Befehle, um den Auftrag zu verwalten.

Wenn Sie **AsJob** verwenden, gibt PowerShell außerdem ein Auftrags Objekt zurück, das einen untergeordneten Auftrag für jeden gestarteten Auftrag enthält. In diesem Fall enthält das Auftragsobjekt drei untergeordnete Aufträge, einen für jeden Auftrag auf jedem Remotecomputer.

```powershell
# Use the Invoke-Command cmdlet with the -AsJob parameter to start a background job that runs a Get-Service command on three remote computers.
# Store the resulting job object in the $j variable
$j = Invoke-Command -ComputerName Server01, Server02, Server03 -ScriptBlock {Get-Service} -AsJob
# Display the value of the **ChildJobs** property of the job object in $j.
# The display shows that the command created three child jobs, one for the job on each remote computer.
# You could also use the -IncludeChildJobs parameter of the Get-Job cmdlet.
$j.ChildJobs
```

```Output
Id   Name     State      HasMoreData   Location       Command
--   ----     -----      -----------   --------       -------
2    Job2     Completed  True          Server01       Get-Service
3    Job3     Completed  True          Server02       Get-Service
4    Job4     Completed  True          Server03       Get-Service
```

```powershell
# Use the Receive-Job cmdlet to get the results of just the Job3 child job that ran on the Server02 computer.
# Use the *Keep* parameter to allow you to view the aggregated stream data more than once.
Receive-Job -Name Job3 -Keep
```

```Output
Status  Name        DisplayName                        PSComputerName
------  ----------- -----------                        --------------
Running AeLookupSvc Application Experience             Server02
Stopped ALG         Application Layer Gateway Service  Server02
Running Appinfo     Application Information            Server02
Running AppMgmt     Application Management             Server02
```

### Beispiel 4: erhalten der Ergebnisse von Hintergrund Aufträgen auf mehreren Remote Computern

```powershell
# Use the New-PSSession cmdlet to create three user-managed PSSessions on three servers, and save the sessions in the $s variable.
$s = New-PSSession -ComputerName Server01, Server02, Server03
# Use Invoke-Command run a Start-Job command in each of the PSSessions in the $s variable.
# The job outputs the ComputerName of each server.
# Save the job objects in the $j variable.
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$env:COMPUTERNAME}}
# To confirm that these job objects are from the remote machines, run Get-Job to show no local jobs running.
Get-Job
```

```Output

```

```powershell
# Display the three job objects in $j.
# Note that the Localhost location is not the local computer, but instead localhost as it relates to the job on each Server.
$j
```

```Output
Id   Name     State      HasMoreData   Location   Command
--   ----     -----      -----------   --------   -------
1    Job1     Completed  True          Localhost  $env:COMPUTERNAME
2    Job2     Completed  True          Localhost  $env:COMPUTERNAME
3    Job3     Completed  True          Localhost  $env:COMPUTERNAME
```

```powershell
# Use Invoke-Command to run a Receive-Job command in each of the sessions in the $s variable and save the results in the $Results variable.
# The Receive-Job command must be run in each session because the jobs were run locally on each server.
$results = Invoke-Command -Session $s -ScriptBlock {Receive-Job -Job $Using:j}
```

```Output
Server01
Server02
Server03
```

Dieses Beispiel zeigt, wie Sie die Ergebnisse der Hintergrundaufträge abrufen können, die auf drei Computern ausgeführt werden.
Im Gegensatz zum vorherigen Beispiel wurden `Invoke-Command` bei der Verwendung von zum Ausführen des `Start-Job` Befehls tatsächlich drei unabhängige Aufträge auf jedem der drei Computer gestartet. Daher gibt der Befehl drei Auftragsobjekte zurück, die die drei Aufträge darstellen, die lokal auf drei verschiedenen Computern ausgeführt werden.

> [!NOTE]
> Im letzten Befehl, da `$j` eine lokale Variable ist, verwendet der Skriptblock den **using** -bereichsmodifizierer, um die Variable zu identifizieren `$j` . Weitere Informationen zum using-bereichsmodifizierer finden **Sie** unter [about_Remote_Variables](./About/about_Remote_Variables.md).

### Beispiel 5: Zugriff auf untergeordnete Aufträge

Der- `-Keep` Parameter behält den Zustand der aggregierten Streams eines Auftrags bei, sodass er wieder angezeigt werden kann. Ohne diesen Parameter werden alle aggregierten Datenstrom Daten gelöscht, wenn der Auftrag empfangen wird. Weitere Informationen finden Sie unter [about_Job_Details](About/about_Job_Details.md#child-jobs)

> [!NOTE]
> Die aggregierten Streams enthalten die Streams aller untergeordneten Aufträge. Die einzelnen Datenströme können weiterhin über das Auftrags Objekt und die untergeordneten Auftrags Objekte erreicht werden.

```powershell
Start-Job -Name TestJob -ScriptBlock {dir C:\, Z:\}
# Without the Keep parameter, aggregated child job data is displayed once.
# Then destroyed.
Receive-Job -Name TestJob
```

```Output
    Directory: C:\

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-r---        1/24/2019   7:11 AM                Program Files
d-r---        2/13/2019   8:32 AM                Program Files (x86)
d-r---        10/3/2018  11:47 AM                Users
d-----         2/7/2019   1:52 AM                Windows
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

```powershell
# It would seem that the child job data is gone.
Receive-Job -Name TestJob
```

```Output

```

```powershell
# Using the object model, you can still retrieve child job data and streams.
$job = Get-Job -Name TestJob
$job.ChildJobs[0].Error
```

```Output
Cannot find drive. A drive with the name 'Z' does not exist.
    + CategoryInfo          : ObjectNotFound: (Z:String) [Get-ChildItem], DriveNotFoundException
    + FullyQualifiedErrorId : DriveNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
    + PSComputerName        : localhost
```

## PARAMETERS

### -Autoremovejob

Gibt an, dass dieses Cmdlet den Auftrag löscht, nachdem die Auftrags Ergebnisse zurückgegeben wurden.
Wenn für den Auftrag weitere Ergebnisse ausgegeben werden, wird der Auftrag weiterhin gelöscht, aber `Receive-Job` eine Meldung angezeigt.

Dieser Parameter kann nur für benutzerdefinierte Auftragstypen verwendet werden.
Er wurde für Instanzen von Auftragstypen entwickelt, die den Auftrag oder den Typ außerhalb der Sitzung speichern, z. B. Instanzen von geplanten Aufträgen.

Dieser Parameter kann nicht ohne den **Wait** -Parameter verwendet werden.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### -ComputerName

Gibt ein Array von Namen von Computern an.

Mit diesem Parameter wird unter den Auftragsergebnissen ausgewählt, die auf dem lokalen Computer gespeichert sind.
Er ruft keine Daten für Aufträge ab, die auf Remote Computern ausgeführt werden.
Verwenden Sie zum Ausführen von Auftrags Ergebnissen, die auf Remote Computern gespeichert sind, das- `Invoke-Command` Cmdlet, um einen `Receive-Job` Befehl Remote auszuführen.

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 1
Default value: All computers available
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Force

Gibt an, dass dieses Cmdlet weiterhin wartet, wenn sich **Aufträge im angehaltenen oder** **getrennten** Zustand befinden. Standardmäßig gibt der **Wait** -Parameter von `Receive-Job` zurück oder beendet den warte Vorgang, wenn Aufträge einen der folgenden Zustände aufweisen:

- Abgeschlossen
- Fehler
- Beendet
- Ausgesetzt
- Getrennt

Der **Force**-Parameter ist nur gültig, wenn der **Wait**-Parameter ebenfalls im Befehl verwendet wird.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### -Id

Gibt ein Array von IDs an.
Dieses Cmdlet ruft die Ergebnisse von Aufträgen mit den angegebenen IDs ab.

Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.
Es ist leichter zu merken und einzugeben als die Instanz-ID, Sie ist jedoch nur in der aktuellen Sitzung eindeutig. Sie können eine oder mehrere durch Kommas getrennte IDs eingeben.
Um die ID eines Auftrags zu ermitteln, verwenden Sie `Get-Job` .

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

Gibt ein Array von Instanz-IDs an.
Dieses Cmdlet ruft die Ergebnisse von Aufträgen mit den angegebenen Instanz-IDs ab.

Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.
Verwenden Sie das-Cmdlet, um die Instanz-ID eines Auftrags zu ermitteln `Get-Job` .

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All instances
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Auftrag

Gibt den Auftrag an, für den Ergebnisse abgerufen werden.

Geben Sie eine Variable ein, die den Auftrag enthält, oder geben Sie einen Befehl ein, mit dem das Objekt abgerufen wird.
Sie können ein Auftrags Objekt auch an die Pipeline übergeben `Receive-Job` .

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: Location, Session, ComputerName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Keep

Gibt an, dass dieses Cmdlet die aggregierten Datenstrom Daten im System speichert, auch nachdem Sie Sie empfangen haben. Standardmäßig werden aggregierte Datenstrom Daten gelöscht, nachdem Sie mit angezeigt wurden `Receive-Job` .

Wenn Sie die Sitzung schließen oder den Auftrag mit dem `Remove-Job` Cmdlet entfernen, werden auch aggregierte Datenstrom Daten gelöscht.

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

### -Location

Gibt ein Array von Speicherorten an.
Mit diesem Cmdlet werden nur die Ergebnisse der Aufträge an den angegebenen Speicherorten abgerufen.

```yaml
Type: System.String[]
Parameter Sets: Location
Aliases:

Required: False
Position: 1
Default value: All locations
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Gibt ein Array von Anzeigenamen an.
Dieses Cmdlet ruft die Ergebnisse der Aufträge ab, die über die angegebenen Namen verfügen.
Platzhalterzeichen werden unterstützt.

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

### -Norecurse

Gibt an, dass dieses Cmdlet Ergebnisse nur aus dem angegebenen Auftrag abruft.
In der Standardeinstellung werden von `Receive-Job` auch die Ergebnisse aller untergeordneten Aufträge des angegebenen Auftrags abgerufen.

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

### -Sitzung

Gibt ein Array von Sitzungen an.
Dieses Cmdlet ruft die Ergebnisse der Aufträge ab, die in der angegebenen PowerShell-Sitzung (**PSSession**) ausgeführt wurden.
Geben Sie eine Variable ein, die die **PSSession** oder einen Befehl enthält, mit dem die **PSSession** abgerufen wird, z. b. einen- `Get-PSSession` Befehl.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 1
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wait

Gibt an, dass dieses Cmdlet die Eingabeaufforderung unterdrückt, bis alle Auftrags Ergebnisse empfangen wurden.
Standardmäßig werden `Receive-Job` die verfügbaren Ergebnisse sofort zurückgegeben.

Standardmäßig wartet der **Wait**-Parameter, bis der Auftrag sich in einem der folgenden Zustände befindet:

- Abgeschlossen
- Fehler
- Beendet
- Ausgesetzt
- Getrennt

Verwenden Sie den **Force** -Parameter und den **Wait** -Parameter, um den **Wait** -Parameter so zu leiten, dass er weiterhin wartet, wenn der Auftrags Zustand angehalten oder getrennt wird.

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

### -Write Events

Gibt an, dass dieses Cmdlet Änderungen im Auftrags Zustand meldet, während es darauf wartet, dass der Auftrag beendet wird.

Dieser Parameter ist nur gültig, wenn der **Wait**-Parameter im Befehl verwendet wird und der **Keep**-Parameter weggelassen wird.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### -Beschreib Items @ binresults

Gibt an, dass dieses Cmdlet das Auftrags Objekt zurückgibt, gefolgt von den Ergebnissen.

Dieser Parameter ist nur gültig, wenn der **Wait**-Parameter im Befehl verwendet wird und der **Keep**-Parameter weggelassen wird.

Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](./About/about_CommonParameters.md).

## EINGABEN

### System. Management. Automation. Job

Sie können Auftrags Objekte über die Pipeline an dieses Cmdlet übergeben.

## AUSGABEN

### PSObject

Mit diesem Cmdlet werden die Ergebnisse der Befehle im Auftrag zurückgegeben.

## HINWEISE

## VERWANDTE LINKS

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)

