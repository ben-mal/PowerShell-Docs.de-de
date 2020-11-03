---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 02/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/register-engineevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-EngineEvent
ms.openlocfilehash: 26a8ef5bfb9fd520fabc836ca1e5da40558e0e8a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210303"
---
# Register-EngineEvent

## ZUSAMMENFASSUNG
Abonniert Ereignisse, die von der PowerShell-Engine und vom `New-Event` Cmdlet generiert werden.

## SYNTAX

```
Register-EngineEvent [-SourceIdentifier] <String> [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

Das `Register-EngineEvent` -Cmdlet abonniert Ereignisse, die von der PowerShell-Engine und dem `New-Event` Cmdlet generiert werden. Verwenden Sie den **SourceIdentifier** -Parameter, um das Ereignis anzugeben.

Mit diesem Cmdlet können **Sie das Ereignis** und die vom `New-Event` Cmdlet generierten Ereignisse abonnieren. Diese Ereignisse werden der Ereigniswarteschlange in der Sitzung ohne Abonnement automatisch hinzugefügt. Ein Abonnement ermöglicht es Ihnen jedoch, Ereignisse weiterzuleiten, eine Aktion für die Reaktion auf Ereignisse anzugeben und das Abonnement zu stornieren.

Wenn das abonnierte Ereignis ausgelöst wird, wird es der Ereigniswarteschlange der Sitzung hinzugefügt. Verwenden Sie das-Cmdlet, um Ereignisse in der Ereignis Warteschlange zu erhalten `Get-Event` .

Wenn Sie ein-Ereignis abonnieren, wird der Sitzung ein Ereignis Abonnent hinzugefügt. Rufen Sie die Ereignisabonnenten in der Sitzung mithilfe des Cmdlets `Get-EventSubscriber` ab. Brechen Sie das Abonnement mit dem Cmdlet `Unregister-Event` ab, wodurch die Ereignisabonnenten aus der Sitzung gelöscht werden.

## BEISPIELE

### Beispiel 1: Registrieren eines PowerShell-Engine-Ereignisses auf Remote Computern

Dieses Beispiel registriert sich für ein PowerShell-Engine-Ereignis auf zwei Remote Computern.

```powershell
$S = New-PSSession -ComputerName "Server01, Server02"
Invoke-Command -Session $S { Register-EngineEvent -SourceIdentifier ([System.Management.Automation.PsEngineEvent]::Exiting) -Forward }
```

`New-PSSession` erstellt eine vom Benutzer verwaltete Sitzung (PSSession) auf jedem Remote Computer. Das `Invoke-Command` Cmdlet führt den `Register-EngineEvent` Befehl in den Remote Sitzungen aus.
`Register-EngineEvent` verwendet den **SourceIdentifier** -Parameter, um das Ereignis zu identifizieren. Der **Forward** -Parameter teilt der Engine mit, die Ereignisse von der Remote Sitzung an die lokale Sitzung weiterzuleiten.

### Beispiel 2: nehmen Sie eine angegebene Aktion vor, wenn das beendeereignis auftritt.

In diesem Beispiel wird gezeigt, wie ausgeführt wird `Register-EngineEvent` , um eine bestimmte Aktion auszuführen, wenn das **PowerShell. Exit** -Ereignis auftritt.

```powershell
Register-EngineEvent -SourceIdentifier PowerShell.Exiting -SupportEvent -Action {
    Get-History | Export-Clixml $Home\history.clixml
}
```

Der **supportevent** -Parameter wird hinzugefügt, um das Ereignis Abonnement auszublenden. Wenn PowerShell beendet wird, wird in diesem Fall der Befehlsverlauf aus der Beendigungen enden Sitzung in eine XML-Datei im Verzeichnis des Benutzers exportiert `$Home` .

### Beispiel 3: Erstellen und Abonnieren eines benutzerdefinierten Ereignisses

In diesem Beispiel wird ein Abonnement für Ereignisse aus der Quelle " **myeventsource** " erstellt. Dies ist eine beliebige Quelle, die wir zum Überwachen des Fortschritts eines Auftrags verwenden werden. `Register-EngineEvent` wird verwendet, um das Abonnement zu erstellen. Der Skriptblock für den **Action** -Parameter protokolliert die Ereignisdaten in einer Textdatei.

```powershell
Register-EngineEvent -SourceIdentifier MyEventSource -Action {
    "Event: {0}" -f $event.messagedata | Out-File c:\temp\MyEvents.txt -Append
}

Start-Job -Name TestJob -ScriptBlock {
    While ($True) {
        Register-EngineEvent -SourceIdentifier MyEventSource -Forward
        Start-Sleep -seconds 2
        "Doing some work..."
        New-Event -SourceIdentifier MyEventSource -Message ("{0} -  Work done..." -f (Get-Date))
    }
}
Start-Sleep -seconds 4
Get-EventSubscriber
Get-Job
```

```Output
SubscriptionId   : 12
SourceObject     :
EventName        :
SourceIdentifier : MyEventSource
Action           : System.Management.Automation.PSEventJob
HandlerDelegate  :
SupportEvent     : False
ForwardEvent     : False

Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
18     MyEventSource                   Running       True                                 …
19     TestJob         BackgroundJob   Running       True            localhost            …
```

`Register-EngineEvent` die Auftrags-ID 18 wurde erstellt. `Start-Job` die Auftrags-ID 19 wurde erstellt. Im Beispiel #4 entfernen wir das Ereignis Abonnement und die Aufträge und überprüfen dann die Protokolldatei.

### Beispiel 4: Aufheben der Registrierung von Ereignissen und Bereinigen von Aufträgen

Dies ist eine Fortsetzung von Beispiel 3. In diesem Beispiel warten wir 10 Sekunden, bis mehrere Ereignisse eintreten. Dann heben Sie die Registrierung für das Ereignis Abonnement auf.

```powershell
PS> Start-Sleep -seconds 10
PS> Get-EventSubscriber | Unregister-Event
PS> Get-Job

Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
18     MyEventSource                   Stopped       False                                …
19     TestJob         BackgroundJob   Running       True            localhost            …

PS> Stop-Job -Id 19
PS> Get-Job | Remove-Job
PS> Get-Content C:\temp\MyEvents.txt
Event: 2/18/2020 2:36:19 PM -  Work done...
Event: 2/18/2020 2:36:21 PM -  Work done...
Event: 2/18/2020 2:36:23 PM -  Work done...
Event: 2/18/2020 2:36:25 PM -  Work done...
Event: 2/18/2020 2:36:27 PM -  Work done...
Event: 2/18/2020 2:36:29 PM -  Work done...
Event: 2/18/2020 2:36:31 PM -  Work done...
```

Mit dem- `Unregister-Event` Cmdlet wird der dem Ereignis Abonnement zugeordnete Auftrag beendet (Auftrags-ID 18). Die Auftrags-ID 19 wird noch ausgeführt, und es werden neue Ereignisse erstellt. Wir verwenden die **Job** -Cmdlets zum Abbrechen des Auftrags und zum Entfernen der nicht benötigten Auftrags Objekte. `Get-Content` zeigt den Inhalt der Protokolldatei an.

## PARAMETERS

### -Action

Gibt Befehle zur Behandlung der Ereignisse an. Beim Auslösen eines Ereignisses werden die Befehle in **Action** ausgeführt, statt das Ereignis an die Ereigniswarteschlange zu senden. Schließen Sie die Befehle in geschweifte Klammern ({}) ein, um einen Skriptblock zu erstellen.

Der Wert des **Action** -Parameters kann die `$Event` `$EventSubscriber` automatischen Variablen,,, und enthalten `$Sender` `$EventArgs` `$Args` , die dem **Aktions** Skriptblock Informationen zum Ereignis bereitstellen. Weitere Informationen finden Sie unter [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

Wenn Sie eine Aktion angeben, `Register-EngineEvent` gibt ein Ereignis Auftrags Objekt zurück, das diese Aktion darstellt. Sie können die Job-Cmdlets verwenden, um den Ereignisauftrag zu verwalten.

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

### -Vorwärts

Gibt an, dass das Cmdlet Ereignisse für dieses Abonnement an die Sitzung auf dem lokalen Computer sendet.
Verwenden Sie diesen Parameter, wenn Sie sich auf einem Remotecomputer oder in einer Remotesitzung für Ereignisse registrieren.

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

### -Maxtriggercount

Gibt an, wie oft die Aktion für das Ereignis Abonnement maximal ausgeführt werden soll.

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

Gibt zusätzliche Daten an, die dem Ereignis zugeordnet sind. Der Wert dieses Parameters wird in der **MessageData** -Eigenschaft des Ereignisobjekts angezeigt.

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

Gibt den Quellbezeichner des Ereignisses an, das Sie abonnieren. Der Quellbezeichner muss in der aktuellen Sitzung eindeutig sein. Dieser Parameter ist erforderlich.

Der Wert dieses Parameters wird im Wert der **SourceIdentifier** -Eigenschaft des Abonnentenobjekts und aller diesem Abonnement zugeordneten Ereignisobjekte angezeigt.

Der Wert ist für die Quelle des Ereignisses spezifisch. Dies kann ein beliebiger Wert sein, den Sie für die Verwendung mit dem `New-Event` Cmdlet erstellt haben. Die PowerShell-Engine unterstützt die **engineevent** -Werte **PowerShell. Exit** und **PowerShell. OnIdle** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 100
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Supportevent

Gibt an, dass das Cmdlet das Ereignis Abonnement verbirgt. Fügen Sie diesen Parameter hinzu, wenn das aktuelle Abonnement Teil eines komplexeren Ereignis Registrierungs Mechanismus ist und nicht unabhängig erkannt werden sollte.

Um ein Abonnement anzuzeigen oder abzubrechen, das mit dem **supportevent** -Parameter erstellt wurde, fügen Sie den **Force** -Parameter den- `Get-EventSubscriber` oder- `Unregister-Event` Cmdlets hinzu.

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

Eingaben können nicht an übergeben werden `Register-EngineEvent` .

## AUSGABEN

### None oder System. Management. Automation. psiebziger Job

Wenn Sie den **Action** -Parameter verwenden, wird `Register-EngineEvent` ein **System. Management. Automation. psiebziger Job** -Objekt zurückgegeben. Andernfalls wird keine Ausgabe generiert.

## HINWEISE

Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden. Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

## VERWANDTE LINKS

[Get-Event](Get-Event.md)

[New-Event](New-Event.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
