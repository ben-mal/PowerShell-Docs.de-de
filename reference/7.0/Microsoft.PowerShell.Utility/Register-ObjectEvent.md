---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/register-objectevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ObjectEvent
ms.openlocfilehash: a6ed76164dbc2773393211ad8474becb499986a3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210300"
---
# Register-ObjectEvent

## ZUSAMMENFASSUNG
Abonniert die Ereignisse, die von einem Microsoft .NET Framework-Objekt generiert werden.

## SYNTAX

```
Register-ObjectEvent [-InputObject] <PSObject> [-EventName] <String> [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

Das- `Register-ObjectEvent` Cmdlet abonniert Ereignisse, die von .NET-Objekten auf dem lokalen Computer oder auf einem Remote Computer generiert werden.

Wenn das abonnierte Ereignis ausgelöst wird, wird es der Ereigniswarteschlange der Sitzung hinzugefügt. Verwenden Sie das-Cmdlet, um Ereignisse in der Ereignis Warteschlange zu erhalten `Get-Event` .

Sie können die Parameter von verwenden `Register-ObjectEvent` , um Eigenschaftswerte der Ereignisse anzugeben, mit deren Hilfe Sie das Ereignis in der Warteschlange identifizieren können. Sie können auch den **Action** -Parameter verwenden, um Aktionen anzugeben, die ausgeführt werden, wenn ein abonnierte Ereignis ausgelöst wird, und den **Forward** -Parameter zum Senden von Remote Ereignissen an die Ereignis Warteschlange in der lokalen Sitzung

Wenn Sie ein Ereignis abonnieren, wird der Sitzung ein Ereignisabonnent hinzugefügt. Rufen Sie die Ereignisabonnenten in der Sitzung mithilfe des Cmdlets `Get-EventSubscriber` ab. Brechen Sie das Abonnement mit dem Cmdlet `Unregister-Event` ab, wodurch die Ereignisabonnenten aus der Sitzung gelöscht werden.

## BEISPIELE

### Beispiel 1: Abonnieren von Ereignissen, wenn ein neuer Prozess gestartet wird

In diesem Beispiel werden Ereignisse abonniert, die beim Starten neuer Prozesse generiert werden.

Der Befehl verwendet das **ManagementEventWatcher** -Objekt, um **eventeingetroffen** -Ereignisse zu erhalten. Ein Query-Objekt gibt an, dass die Ereignisse instanzerstellungsereignisse für die **Win32_Process** -Klasse sind.

```powershell
$queryParameters = '__InstanceCreationEvent', (New-Object TimeSpan 0,0,1),
    "TargetInstance isa 'Win32_Process'"
$Query = New-Object System.Management.WqlEventQuery -ArgumentList $queryParameters
$ProcessWatcher = New-Object System.Management.ManagementEventWatcher $Query
Register-ObjectEvent -InputObject $ProcessWatcher -EventName "EventArrived"
```

### Beispiel 2: Geben Sie eine Aktion an, die auf ein Ereignis antwortet.

Wenn Sie eine Aktion angeben, werden ausgelöste Ereignisse nicht der Ereigniswarteschlange hinzugefügt. Die Aktion reagiert stattdessen auf das Ereignis. In diesem Beispiel wird ein neues **processcreated** -Ereignis ausgelöst, wenn ein instanzerstellungs-Ereignis ausgelöst wird, das angibt, dass ein neuer Prozess gestartet wird.

```powershell
$queryParameters = '__InstanceCreationEvent', (New-Object TimeSpan 0,0,1),
    "TargetInstance isa 'Win32_Process'"
$Query = New-Object System.Management.WqlEventQuery -ArgumentList $queryParameters
$ProcessWatcher = New-Object System.Management.ManagementEventWatcher $query
$newEventArgs = @{
    SourceIdentifier = 'PowerShell.ProcessCreated'
    Sender = $Sender
    EventArguments = $EventArgs.NewEvent.TargetInstance
}
$Action = { New-Event @newEventArgs }
Register-ObjectEvent -InputObject $ProcessWatcher -EventName "EventArrived" -Action $Action
```

```Output
Id   Name               PSJobTypeName   State       HasMoreData   Location   Command
--   ----               -------------   -----       -----------   --------   -------
 5   3db2d67a-efff-...                 NotStarted   False                    New-Event @newEventArgs
```

Die Aktion verwendet die `$Sender` `$EventArgs` automatischen Variablen und, die nur für Ereignis Aktionen aufgefüllt werden.

Der `Register-ObjectEvent` Befehl gibt ein Auftrags Objekt zurück, das die Aktion darstellt, die als Hintergrund Auftrag ausgeführt wird. Sie können die Job-Cmdlets wie und verwenden `Get-Job` `Receive-Job` , um den Hintergrund Auftrag zu verwalten. Weitere Informationen finden Sie unter [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md).

### Beispiel 3: Abonnieren von Objekt Ereignissen auf Remote Computern

Dieses Beispiel zeigt, wie Sie Objektereignisse auf Remotecomputern abonnieren können. In diesem Beispiel wird die- `Enable-ProcessCreationEvent` Funktion verwendet, die in der `ProcessCreationEvent.ps1` Skriptdatei definiert ist. Dieses Skript ist im Beispiel für alle Computer verfügbar.

```powershell
# ProcessCreationEvent.ps1
function  Enable-ProcessCreationEvent {
    $queryParameters = "__InstanceCreationEvent", (New-Object TimeSpan 0,0,1),
        "TargetInstance isa 'Win32_Process'"
    $Query = New-Object System.Management.WqlEventQuery -ArgumentList $queryParameters

    $objectEventArgs = @{
        Input = New-Object System.Management.ManagementEventWatcher $Query
        EventName = 'EventArrived'
        SourceIdentifier = 'WMI.ProcessCreated'
        MessageData = 'Test'
        Forward = $True
    }
    Register-ObjectEvent @objectEventArgs
}

$S = New-PSSession -ComputerName "Server01, Server02"
Invoke-Command -Session $S -FilePath ProcessCreationEvent.ps1
Invoke-Command -Session $S { Enable-ProcessCreationEvent }
```

Der erste erstellt **pssessions** auf zwei Remote Computern und speichert Sie in der `$S` Variablen. Als nächstes `Invoke-Command` führt das Cmdlet das `ProcessCreationEvent.ps1` Skript in jeder der pssessions in aus `$S` . Diese Aktion erstellt die `Enable-ProcessCreationEvent` Funktion in den Remote Sitzungen.
Zum Schluss führen wir die `Enable-ProcessCreationEvent` Funktion in den Remote Sitzungen aus.

 Die-Funktion enthält einen `Register-ObjectEvent` Befehl, der instanzerstellungsereignisse für das **Win32_Process** Objekt über das **ManagementEventWatcher** -Objekt und dessen **eventincludes** -Ereignis abonniert.

### Beispiel 4: Verwenden des dynamischen Moduls im psiebziger Job-Objekt

Dieses Beispiel zeigt, wie Sie das dynamische Modul im **peventjob** -Objekt verwenden, das erstellt wird, wenn Sie eine **Aktion** in eine Ereignis Registrierung einschließen. Zuerst wird ein Zeit Geber Objekt aktiviert und aktiviert. Anschließend wird das Zeitintervall des Timers auf 500 (Millisekunden) festgelegt. Das- `Register-ObjectEvent` Cmdlet registriert das **verstrichene** Ereignis des Timer-Objekts. Das **psiebziger Job** -Objekt wird in der `$Job` -Variable gespeichert und ist auch in der **Action** -Eigenschaft des Ereignis Abonnenten verfügbar. Weitere Informationen finden Sie unter " [Get-eventsubscriber](Get-EventSubscriber.md)".

Wenn das Zeit Geber Intervall abläuft, wird ein Ereignis ausgelöst, und die Aktion wird ausgeführt. In diesem Fall generiert das `Get-Random` Cmdlet eine Zufallszahl zwischen 0 und 100 und speichert Sie in der `$Random` Variablen.

```powershell
$Timer = New-Object Timers.Timer
$Timer.Interval = 500
$Timer.Enabled = $True
$objectEventArgs = @{
    InputObject = $Timer
    EventName = 'Elapsed'
    SourceIdentifier = 'Timer.Random'
    Action = {$Random = Get-Random -Min 0 -Max 100}
}
$Job = Register-ObjectEvent @objectEventArgs
$Job | Format-List -Property *
& $Job.module {$Random}
& $Job.module {$Random}
```

```Output
State         : Running
Module        : __DynamicModule_53113769-31f2-42dc-830b-8749325e28d6
StatusMessage :
HasMoreData   : True
Location      :
Command       : $Random = Get-Random -Min 0 -Max 100
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : 47b5ec9f-bfe3-4605-860a-4674e5d44ca8
Id            : 7
Name          : Timer.Random
ChildJobs     : {}
PSBeginTime   : 6/27/2019 10:19:06 AM
PSEndTime     :
PSJobTypeName :
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
Information   : {}
60
47
```

Der **psiebziger Job** verfügt über eine **Modul** Eigenschaft, die ein dynamisches Skript Modul enthält, das die Aktion implementiert. Mit dem Aufruf Operator ( `&` ) rufen wir den Befehl im Modul auf, um den Wert der Variablen anzuzeigen `$Random` .

Weitere Informationen zu Modulen finden Sie unter [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).

## PARAMETERS

### -Action

Gibt die Befehle zum Behandeln des Ereignisses an. Beim Auslösen eines Ereignisses werden die Befehle in **Action** ausgeführt, statt das Ereignis an die Ereigniswarteschlange zu senden. Schließen Sie die Befehle in geschweifte Klammern ({}) ein, um einen Skriptblock zu erstellen.

Der Wert des **Action** -Parameters kann die `$Event` `$EventSubscriber` `$Sender` automatischen Variablen,,, `$EventArgs` und enthalten `$Args` . Diese Variablen stellen dem **Aktions** Skriptblock Informationen zum Ereignis bereit. Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

Wenn Sie eine Aktion angeben, `Register-ObjectEvent` gibt ein Ereignis Auftrags Objekt zurück, das diese Aktion darstellt. Sie können die Job-Cmdlets verwenden, um den Ereignisauftrag zu verwalten.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 101
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventName

Gibt das Ereignis an, das Sie abonnieren.

Der Wert dieses Parameters muss dem Namen des Ereignisses sein, das das .NET-Objekt verfügbar macht. Die **ManagementEventWatcher** -Klasse hat z. b. Ereignisse mit dem Namen **eventeingetroffen** und **beendet**. Verwenden Sie das-Cmdlet, um den Ereignis Namen eines Ereignisses zu ermitteln `Get-Member` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vorwärts

Gibt an, dass das Cmdlet Ereignisse für dieses Abonnement an eine Remote Sitzung sendet. Verwenden Sie diesen Parameter, wenn Sie sich auf einem Remotecomputer oder in einer Remotesitzung für Ereignisse registrieren.

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

### -InputObject

Gibt das .NET-Objekt an, das die Ereignisse generiert. Geben Sie eine Variable ein, die das Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem das Objekt abgerufen wird.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maxtriggercount

Gibt an, wie oft ein Ereignis maximal ausgelöst werden kann.

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

### -MessageData

Gibt alle weiteren Daten an, die diesem Ereignisabonnement zugeordnet werden sollen. Der Wert dieses Parameters wird in der MessageData-Eigenschaft aller diesem Abonnement zugeordneten Ereignisse angezeigt.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Gibt einen Namen an, den Sie für das Abonnement auswählen. Der von Ihnen ausgewählte Name muss in der aktuellen Sitzung eindeutig sein. Der Standardwert ist die GUID, die von PowerShell zugewiesen wird.

Der Wert dieses Parameters wird im Wert der **SourceIdentifier** -Eigenschaft des Abonnenten Objekts und aller diesem Abonnement zugeordneten Ereignis Objekte angezeigt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Supportevent

Gibt an, dass das Cmdlet das Ereignis Abonnement verbirgt. Verwenden Sie diesen Parameter, wenn das aktuelle Abonnement Teil eines komplexeren Ereignis Registrierungs Mechanismus ist und nicht unabhängig erkannt werden sollte.

Um ein Abonnement anzuzeigen oder abzubrechen, das mit dem **supportevent** -Parameter erstellt wurde, verwenden Sie den **Force** -Parameter der `Get-EventSubscriber` `Unregister-Event` Cmdlets und.

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

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

Objekte können nicht an übergeben werden `Register-ObjectEvent` .

## AUSGABEN

### None oder System. Management. Automation. psiebziger Job

Wenn Sie den **Action** -Parameter verwenden, wird `Register-ObjectEvent` ein **System. Management. Automation. psiebziger Job** -Objekt zurückgegeben. Andernfalls wird keine Ausgabe generiert.

## HINWEISE

Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden. Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

## VERWANDTE LINKS

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
