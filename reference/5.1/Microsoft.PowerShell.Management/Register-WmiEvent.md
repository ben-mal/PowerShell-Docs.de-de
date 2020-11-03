---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/register-wmievent?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-WmiEvent
ms.openlocfilehash: be29ce6376dea7686c0c063cc5528fbc7d840a9d
ms.sourcegitcommit: 41b072f0b6046d619b0e7f758982783fb648a3d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "93219047"
---
# Register-WmiEvent

## ZUSAMMENFASSUNG
Abonniert ein Ereignis der Windows-Verwaltungsinstrumentation (Windows Management Instrumentation, WMI.

## SYNTAX

### Class (Standard)

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Class] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### Abfrage

```
Register-WmiEvent [-Namespace <String>] [-Credential <PSCredential>] [-ComputerName <String>] [-Query] <String>
 [-Timeout <Int64>] [[-SourceIdentifier] <String>] [[-Action] <ScriptBlock>] [-MessageData <PSObject>]
 [-SupportEvent] [-Forward] [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Register-WmiEvent` Cmdlet abonniert Windows-Verwaltungsinstrumentation (WMI)-Ereignisse auf dem lokalen Computer oder auf einem Remote Computer.

Wenn das abonnierte WMI-Ereignis ausgelöst wird, wird es der Ereigniswarteschlange in der lokalen Sitzung hinzugefügt, auch wenn das Ereignis auf einem Remotecomputer eintritt. Verwenden Sie das-Cmdlet, um Ereignisse in der Ereignis Warteschlange zu erhalten `Get-Event` .

Sie können die Parameter von verwenden `Register-WmiEvent` , um Ereignisse auf Remote Computern zu abonnieren und die Eigenschaftswerte der Ereignisse anzugeben, mit deren Hilfe Sie das Ereignis in der Warteschlange identifizieren können. Sie können auch den **Action** -Parameter verwenden, um Aktionen anzugeben, die ausgeführt werden, wenn ein abonnierte Ereignis ausgelöst wird.

Wenn Sie ein Ereignis abonnieren, wird der Sitzung ein Ereignisabonnent hinzugefügt. Rufen Sie die Ereignisabonnenten in der Sitzung mithilfe des Cmdlets `Get-EventSubscriber` ab. Brechen Sie das Abonnement mit dem Cmdlet `Unregister-Event` ab, wodurch die Ereignisabonnenten aus der Sitzung gelöscht werden.

Die neuen Common Information Model (CIM)-Cmdlets, die Windows PowerShell 3,0 eingeführt haben, führen dieselben Aufgaben wie die WMI-Cmdlets aus. Die CIM-Cmdlets entsprechen den WS-Management (WSMAN)-Standards und dem CIM-Standard. Dadurch können die Cmdlets dieselben Verfahren zum Verwalten von Computern verwenden, auf denen das Windows-Betriebssystem ausgeführt wird, und auf denen andere Betriebssysteme ausgeführt werden. Anstatt zu verwenden `Register-WmiEvent` , sollten Sie das Cmdlet [Register-cimindikticmdlet](../cimcmdlets/register-cimindicationevent.md) verwenden.

## BEISPIELE

### Beispiel 1: Abonnieren von Ereignissen, die von einer Klasse generiert wurden

Dieser Befehl abonniert die Ereignisse, die von der **Win32_ProcessStartTrace** -Klasse generiert werden. Diese Klasse löst immer dann ein Ereignis aus, wenn ein Prozess gestartet wird.

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
```

### Beispiel 2: Abonnieren von Erstellungs Ereignissen für einen Prozess

In diesem Befehl werden Win32_process-Instanzerstellungsereignisse mithilfe einer Abfrage abonniert.

```powershell
$wmiParameters = @{
  Query = "select * from __instancecreationevent within 5 where targetinstance isa 'win32_process'"
  SourceIdentifier = "WMIProcess"
  MessageData = "Test 01"
  TimeOut = 500
}
Register-WmiEvent @wmiParameters
```

### Beispiel 3: Verwenden Sie eine Aktion, um auf ein Ereignis zu reagieren.

In diesem Beispiel wird die Verwendung einer Aktion als Antwort auf ein Ereignis veranschaulicht. In diesem Fall `Start-Process` werden alle Befehle in der aktuellen Sitzung in eine XML-Datei geschrieben, wenn ein Prozess gestartet wird.

```powershell
$action = { Get-History | where { $_.commandline -like "*start-process*" } | export-cliXml "commandHistory.clixml" }
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

```Output
Id    Name            State      HasMoreData   Location  Command
--    ----            -----      -----------   --------  -------
1     ProcessStarted  NotStarted False                   get-history | where {...
```

Wenn Sie den **Action** -Parameter verwenden, `Register-WmiEvent` gibt einen Hintergrund Auftrag zurück, der die Ereignis Aktion darstellt. Sie können die **Job** -Cmdlets wie und verwenden `Get-Job` `Receive-Job` , um den Ereignis Auftrag zu verwalten.

Weitere Informationen finden Sie unter %%amp;quot;about_Jobs%%amp;quot;.

### Beispiel 4: Registrieren für Ereignisse auf einem Remote Computer

In diesem Beispiel werden Ereignisse auf dem Remotecomputer %%amp;quot;Server01%%amp;quot; registriert.

```powershell
Register-WmiEvent -Class 'Win32_ProcessStartTrace' -SourceIdentifier "Start" -Computername Server01
Get-Event -SourceIdentifier "Start"
```

WMI gibt die Ereignisse an den lokalen Computer zurück und speichert sie in der Ereigniswarteschlange in der aktuellen Sitzung. Um die Ereignisse abzurufen, führen Sie einen lokalen `Get-Event` Befehl aus.

## PARAMETERS

### -Action

Gibt Befehle an, die die Ereignisse behandeln. Die Befehle im **Action** -Parameter werden ausgeführt, wenn ein Ereignis ausgelöst wird, anstatt das Ereignis an die Ereignis Warteschlange zu senden. Schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen.

Der Wert der **Aktion** kann die `$Event` `$EventSubscriber` automatischen Variablen,,, `$Sender` und enthalten `$EventArgs` `$Args` , die dem **Aktions** Skriptblock Informationen zum Ereignis bereitstellen. Weitere Informationen finden Sie unter %%amp;quot;about_Automatic_Variables%%amp;quot;.

Wenn Sie eine Aktion angeben, `Register-WmiEvent` gibt ein Ereignis Auftrags Objekt zurück, das diese Aktion darstellt. Sie können die-Cmdlets verwenden, die das **Auftrags** Substantiv (die **Job** -Cmdlets) enthalten, um den Ereignis Auftrag zu verwalten.

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

### -Klasse

Gibt das Ereignis an, das Sie abonnieren. Geben Sie die WMI-Klasse ein, die die Ereignisse generiert. Ein **Class** -oder **Query** -Parameter ist in jedem Befehl erforderlich.

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt den Namen des Computers an, auf dem der Befehl ausgeführt wird. Die Standardeinstellung ist der lokale Computer.

Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen des Computers ein. Geben Sie den Computernamen, einen Punkt () oder einen localhost ein, um den lokalen Computer anzugeben `.` .

Dieser Parameter beruht nicht auf Windows PowerShell-Remoting. Sie können den **ComputerName** -Parameter auch dann verwenden, wenn der Computer nicht für das Ausführen von Remotebefehlen konfiguriert ist.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Gibt ein Benutzerkonto an, das über die Berechtigung zum Ausführen dieser Aktion verfügt. Der Standardwert ist der aktuelle Benutzer.

Geben Sie einen Benutzernamen ein, z. b. USER01 oder Domain01\User01, oder geben Sie ein **PSCredential** -Objekt ein, z. b. ein vom `Get-Credential` Cmdlet generiertes Objekt. Wenn Sie einen Benutzernamen eingeben, werden Sie von diesem Cmdlet zur Eingabe eines Kennworts aufgefordert.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vorwärts

Gibt an, dass dieses Cmdlet Ereignisse für dieses Abonnement an die Sitzung auf dem lokalen Computer sendet.
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

Gibt die maximale Anzahl von Auslösers an.

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

Gibt alle weiteren Daten an, die diesem Ereignisabonnement zugeordnet werden sollen. Der Wert dieses Parameters wird in der **messageData** -Eigenschaft aller diesem Abonnement zugeordneten Ereignisse angezeigt.

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

### -Namespace

Gibt den Namespace der WMI-Klasse an.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

Gibt eine Abfrage in WMI-Abfragesprache (WQL) an, die die WMI-Ereignisklasse identifiziert, z `select * from __InstanceDeletionEvent` . b.:.

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Gibt einen Namen an, den Sie für das Abonnement auswählen. Der von Ihnen ausgewählte Name muss in der aktuellen Sitzung eindeutig sein. Der Standardwert ist die von Windows PowerShell zugewiesene GUID.

Der Wert dieses Parameters wird im Wert der **SourceIdentifier** -Eigenschaft des Abonnentenobjekts und aller diesem Abonnement zugeordneten Ereignisobjekte angezeigt.

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

Gibt an, dass dieses Cmdlet das Ereignis Abonnement verbirgt. Verwenden Sie diesen Parameter, wenn das aktuelle Abonnement Teil eines komplexeren Ereignisregistrierungsmechanismus ist und nicht unabhängig erfasst werden soll.

Um ein Abonnement anzuzeigen oder abzubrechen, das mit dem **supportevent** -Parameter erstellt wurde, geben Sie den **Force** -Parameter der `Get-EventSubscriber` -und- `Unregister-Event` Cmdlets an.

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

### -Timeout

Gibt an, wie lange Windows PowerShell auf den Abschluss dieses Befehls wartet.

Der Standardwert %%amp;quot;0%%amp;quot; (null) bedeutet, dass kein Timeout vorliegt und Windows PowerShell unbegrenzt wartet.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases: TimeoutMSec

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

Objekte können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Keine

Dieses Cmdlet generiert keine Ausgabe.

## HINWEISE

Wenn Sie dieses Cmdlet in Windows Vista oder einer neueren Version des Windows-Betriebssystems verwenden möchten, starten Sie Windows PowerShell mit der Option als Administrator ausführen.

Ereignisse, Ereignisabonnements und die Ereigniswarteschlange sind nur in der aktuellen Sitzung vorhanden. Wenn Sie die aktuelle Sitzung schließen, wird die Ereigniswarteschlange verworfen, und das Ereignisabonnement wird abgebrochen.

## VERWANDTE LINKS
