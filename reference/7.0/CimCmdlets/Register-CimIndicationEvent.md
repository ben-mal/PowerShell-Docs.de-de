---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/register-cimindicationevent?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-CimIndicationEvent
ms.openlocfilehash: 802af0d2a130a0ddc01d9a94cadf7f503eb7d697
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210063"
---
# Register-CimIndicationEvent

## ZUSAMMENFASSUNG
Abonniert die Angabe von Hinweisen mithilfe eines Filter Ausdrucks oder eines Abfrage Ausdrucks.

## SYNTAX

### Classnamecomputerset (Standard)

```
Register-CimIndicationEvent [-Namespace <String>] [-ClassName] <String>
 [-OperationTimeoutSec <UInt32>] [-ComputerName <String>] [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### Classnamesessionset

```
Register-CimIndicationEvent [-Namespace <String>] [-ClassName] <String>
 [-OperationTimeoutSec <UInt32>] -CimSession <CimSession> [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### Queryexpressionsessionset

```
Register-CimIndicationEvent [-Namespace <String>] [-Query] <String> [-QueryDialect <String>]
 [-OperationTimeoutSec <UInt32>] -CimSession <CimSession> [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

### Queryexpressioncomputerset

```
Register-CimIndicationEvent [-Namespace <String>] [-Query] <String> [-QueryDialect <String>]
 [-OperationTimeoutSec <UInt32>] [-ComputerName <String>] [[-SourceIdentifier] <String>]
 [[-Action] <ScriptBlock>] [-MessageData <PSObject>] [-SupportEvent] [-Forward]
 [-MaxTriggerCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION

Das- `Register-CimIndicationEvent` Cmdlet abonniert Anzeichen für die Verwendung eines Hinweis Klassen namens oder eines Abfrage Ausdrucks. Verwenden Sie den **SourceIdentifier** -Parameter, um einen Namen für das Abonnement anzugeben.

Dieses Cmdlet gibt ein **eventabonnement** -Objekt zurück. Mit diesem Objekt können Sie das Abonnement kündigen.

## BEISPIELE

### Beispiel 1: Registrieren der von einer Klasse generierten Ereignisse

In diesem Beispiel werden die von der-Klasse mit dem Namen **Win32_ProcessStartTrace** generierten Ereignisse abonniert. Diese Klasse löst immer dann ein Ereignis aus, wenn ein Prozess gestartet wird.

```powershell
Register-CimIndicationEvent -ClassName 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted"
Get-Event -SourceIdentifier "ProcessStarted"
```

Mit dem- `Get-Event` Cmdlet werden die Ereignisse mit dem Abonnement " **processstarted** " abgerufen. Weitere Informationen finden Sie unter [Get-Event](../Microsoft.PowerShell.Utility/Get-Event.md).

> [!NOTE]
> In diesem Beispiel müssen Sie PowerShell als Administrator ausführen.

### Beispiel 2: Registrieren der Ereignisse mithilfe einer Abfrage

In diesem Beispiel wird eine Abfrage verwendet, um ein Ereignis zu abonnieren, das generiert wird, wenn eine Änderung in der Instanz einer Klasse mit dem Namen " **Win32_LocalTime** " vorliegt.

```powershell
$query = "SELECT * FROM CIM_InstModification WHERE TargetInstance ISA 'Win32_LocalTime'"
Register-CimIndicationEvent -Query $query -SourceIdentifier "Timer"
```

### Beispiel 3: Ausführen eines Skripts beim Eintreffen des Ereignisses

In diesem Beispiel wird gezeigt, wie eine Aktion als Reaktion auf ein Ereignis verwendet wird. Die-Variable `$action` enthält den Skriptblock für **Action** , der die-Variable verwendet, `$event` um auf das von CIM empfangene Ereignis zuzugreifen.

```powershell
$action = {
  $name = $event.SourceEventArgs.NewEvent.ProcessName
  $id = $event.SourceEventArgs.NewEvent.ProcessId
  Write-Host -Object "New Process Started : Name = $name
 ID = $id"
}
Register-CimIndicationEvent -ClassName 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -Action $action
```

Weitere Informationen finden Sie unter [Win32_ProcessStartTrace](/previous-versions/windows/desktop/krnlprov/win32-processstarttrace).

### Beispiel 4: Registrieren der Ereignisse auf einem Remote Computer

In diesem Beispiel werden Ereignisse auf einem Remote Computer mit dem Namen **Server01** abonniert. Vom CIM-Server empfangene Ereignisse werden in der aktuellen PowerShell-Sitzung in der Ereignis Warteschlange gespeichert und dann eine lokale `Get-Event` zum Abrufen der Ereignisse ausgeführt.

```powershell
Register-CimIndicationEvent -ClassName 'Win32_ProcessStartTrace' -SourceIdentifier "ProcessStarted" -ComputerName Server01
Get-Event -SourceIdentifier "ProcessStarted"
```

## PARAMETERS

### -Action

Gibt die Befehle an, die die Ereignisse behandeln. Die Befehle, die durch diesen Parameter angegeben werden, werden ausgeführt, wenn ein Ereignis ausgelöst wird, anstatt das Ereignis an die Ereignis Warteschlange zu senden. Schließen Sie die Befehle in geschweiften Klammern ( `{}` ) ein, um einen Skriptblock zu erstellen.

Der mit **Action** angegebene Skriptblock kann die `$Event` `$EventSubscriber` `$Sender` automatischen Variablen,,, und enthalten `$SourceEventArgs` `$SourceArgs` , die dem **Aktions** Skriptblock Informationen zum Ereignis bereitstellen. Weitere Informationen finden Sie unter Informationen [zu automatischen Variablen](../microsoft.powershell.core/about/about_automatic_variables.md).

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Führt den Befehl mit der angegebenen CIM-Sitzung aus. Geben Sie eine Variable ein, die die CIM-Sitzung enthält, oder einen Befehl, mit dem die CIM-Sitzung erstellt oder abgerufen wird, z `New-CimSession` `Get-CimSession` . b. die Cmdlets oder. Weitere Informationen finden Sie unter [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: ClassNameSessionSet, QueryExpressionSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClassName

Gibt die Indikator Klasse an, zu der Sie abonnieren. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Klassen durchsuchen, da PowerShell eine Liste der Klassen vom lokalen WMI-Server abruft, um eine Liste von Klassennamen bereitzustellen.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, ClassNameSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Gibt den Namen des Computers an, auf dem Sie den CIM-Vorgang ausführen möchten. Sie können einen voll qualifizierten Domänen Namen (Fully Qualified Domain Name, FQDN), einen NetBIOS-Namen oder eine IP-Adresse angeben.

Wenn Sie diesen Parameter angeben, erstellt das Cmdlet mithilfe des WSMAN-Protokolls eine temporäre Sitzung mit dem angegebenen Computer. Wenn Sie diesen Parameter nicht angeben, führt das Cmdlet einen Vorgang auf dem lokalen System mithilfe Component Object Model (com) aus.

Wenn mehrere Vorgänge auf dem gleichen Computer ausgeführt werden, stellen Sie eine Verbindung mithilfe einer CIM-Sitzung her, um die Leistung zu verbessern.

```yaml
Type: System.String
Parameter Sets: ClassNameComputerSet, QueryExpressionComputerSet
Aliases: CN, ServerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Vorwärts

Gibt an, dass Ereignisse für das Abonnement an die Sitzung auf dem lokalen Computer weitergeleitet werden. Verwenden Sie diesen Parameter, wenn Sie sich auf einem Remotecomputer oder in einer Remotesitzung für Ereignisse registrieren.

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

-Parameter, um anzugeben, dass die Registrierung des Abonnenten nach dem Auslösen für angegebene Zeiten automatisch aufgehoben werden soll. Wenn der Wert gleich oder kleiner als 0 (null) ist, gibt es keine Beschränkung für die Häufigkeit, mit der das Ereignis ausgelöst werden kann, ohne dass die Registrierung aufgehoben wird.

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

Gibt alle weiteren Daten an, die diesem Ereignis Abonnement zugeordnet werden sollen. Der Wert dieses Parameters wird in der **messageData** -Eigenschaft aller diesem Abonnement zugeordneten Ereignisse angezeigt.

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

Gibt den Namespace für den CIM-Vorgang an. Der Standard Namespace ist **root/cimv2**. Mit der Vervollständigung mit der Tab-Taste können Sie die Liste der Namespaces durchsuchen, da PowerShell eine Liste der Namespaces vom lokalen WMI-Server abruft, um die Liste der Namespaces bereitzustellen.

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

### -Operationtimeoutsec

Gibt die Zeitspanne an, die das Cmdlet auf eine Antwort des Computers wartet. Standardmäßig ist der Wert dieses Parameters 0, was bedeutet, dass das Cmdlet den Standard Timeout Wert für den Server verwendet.

Wenn der Parameter " **operationtimeoutsec** " auf einen Wert festgelegt ist, der kleiner als der Wert für die dauerhafte Verbindungs Wiederholung von drei Minuten ist, können Netzwerkfehler, die den Wert des Parameters " **operationtimeoutsec** " überschreiten, nicht wieder hergestellt werden, da für den Server ein Timeout auftritt, bevor der Client die Verbindung wiederherstellen kann.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

Gibt eine Abfrage an, die auf dem CIM-Server ausgeführt werden soll. Wenn der angegebene Wert doppelte Anführungszeichen `"` , einfache Anführungszeichen `'` oder einen umgekehrten Schrägstrich enthält `\` , müssen Sie diese Zeichen mit Escapezeichen versehen, indem Sie den umgekehrten Schrägstrich vorangestellt werden. Wenn für den angegebenen Wert der WQL Like-Operator verwendet wird, müssen Sie die folgenden Zeichen mit Escapezeichen versehen, indem Sie Sie in eckige Klammern einschließen `[]` : Prozent `%` , unterstrich `_` oder öffnende eckige Klammer `[` .

```yaml
Type: System.String
Parameter Sets: QueryExpressionSessionSet, QueryExpressionComputerSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Querydialekt

Gibt die Abfragesprache an, die für den **Abfrage** Parameter verwendet wird. Die zulässigen Werte für diesen Parameter sind: **WQL** oder **CQL**. Der Standardwert ist **WQL**.

```yaml
Type: System.String
Parameter Sets: QueryExpressionSessionSet, QueryExpressionComputerSet
Aliases:

Required: False
Position: Named
Default value: WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceIdentifier

Gibt einen Namen für das Abonnement an. Der von Ihnen angegebene Name muss in der aktuellen Sitzung eindeutig sein. Der Standardwert ist eine GUID, die von PowerShell zugewiesen wird. Dieser Wert wird im Wert der **SourceIdentifier** -Eigenschaft des Abonnenten Objekts und aller diesem Abonnement zugeordneten Ereignis Objekte angezeigt.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Supportevent

Gibt an, dass das Ereignis Abonnement ausgeblendet ist. Verwenden Sie diesen Parameter, wenn das aktuelle Abonnement Teil eines komplexeren Ereignisregistrierungsmechanismus ist und nicht unabhängig erfasst werden soll.

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

Dieses Cmdlet akzeptiert keine Eingabe Objekte.

## AUSGABEN

### System.Object

Dieses Cmdlet gibt ein **eventabonnement** -Objekt aus.

## HINWEISE

## VERWANDTE LINKS

[Get-Event](../microsoft.powershell.utility/get-event.md)

[Remove-Event](../microsoft.powershell.utility/remove-event.md)

[Unregister-Event](../microsoft.powershell.utility/unregister-event.md)

[Write-Host](../microsoft.powershell.utility/write-host.md)

[Get-CimSession](Get-CimSession.md)

[New-CimSession](New-CimSession.md)
