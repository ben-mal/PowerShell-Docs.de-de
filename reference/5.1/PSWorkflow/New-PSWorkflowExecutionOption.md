---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowexecutionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowExecutionOption
ms.openlocfilehash: db5d19396f555a41ad14552823c57f3b11c79321
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218287"
---
# New-PSWorkflowExecutionOption

## ZUSAMMENFASSUNG

Erstellt ein Objekt, das Sitzungskonfigurationsoptionen für Workflowsitzungen enthält.

## SYNTAX

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION

Das- `New-PSWorkflowExecutionOption` Cmdlet erstellt ein Objekt, das erweiterte Optionen für Workflow Sitzungs Konfigurationen enthält, d. h. Sitzungs Konfigurationen, die zum Ausführen von Windows PowerShell-Workflow Workflows entworfen wurden.

Sie können das **psworkflowexecutionoption** -Objekt, das `New-PSWorkflowExecutionOption` generiert, als Wert des **sessiontypeoption** -Parameters von Cmdlets verwenden, die eine Sitzungs Konfiguration erstellen oder ändern, wie z `Register-PSSessionConfiguration` . b. die-und- `Set-PSSessionConfiguration` Cmdlets.

Jeder Parameter des `New-PSWorkflowExecutionOption` Cmdlets stellt eine Eigenschaft des Konfigurations Options Objekts der Workflow Sitzung dar, das vom Cmdlet zurückgegeben wird. Wenn Sie einen Parameter weglassen, erstellt das Cmdlet das Objekt mit einem Standardwert für die Eigenschaft.

Das- `New-PSWorkflowExecutionOption` Cmdlet ist Teil der Windows PowerShell-Workflow Funktion.

Sie können diesem Befehl auch allgemeine Workflowparameter hinzufügen. Weitere Informationen zu allgemeinen Workflow Parametern finden Sie unter [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).

Dieses Cmdlet wird in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Erstellen eines Workflow Options-Objekts

```powershell
New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
```

```Output
SessionThrottleLimit                       : 100
PersistencePath                            : C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell\WF\PS
MaxPersistenceStoreSizeGB                  : 10
PersistWithEncryption                      : False
MaxRunningWorkflows                        : 30
AllowedActivity                            : {PSDefaultActivities}
OutOfProcessActivity                       : {InlineScript}
EnableValidation                           : True
MaxDisconnectedSessions                    : 200
MaxConnectedSessions                       : 100
MaxSessionsPerWorkflow                     : 10
MaxSessionsPerRemoteNode                   : 5
MaxActivityProcesses                       : 5
ActivityProcessIdleTimeoutSec              : 60
RemoteNodeSessionIdleTimeoutSec            : 60
WorkflowShutdownTimeoutMSec                : 500
```

Dieser Befehl verwendet das `New-PSWorkflowExecutionOption` Cmdlet, um den **maxsessionsperworkflow** -Wert auf 10 zu erhöhen und den **maxdisconnectedsessions** -Wert auf 200 zu verringern.

Die Ausgabe zeigt das vom Cmdlet zurückgegebene Objekt.

### Beispiel 2: Verwenden eines Workflow Options-Objekts

```powershell
# Create a Workflow Options object and save it in a variable
$wo = New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
# Create the ITWorkflow session configuration
Register-PSSessionConfiguration -Name ITWorkflows -SessionTypeOption $wo -Force
```

```Output
    WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=ITWorkflows}                  ITWorkflows
```

```powershell
Get-PSSessionConfiguration ITWorkflows | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITWorkflows
MaxConcurrentCommandsPerShell : 1000
allowedactivity               : PSDefaultActivities
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
maxsessionsperworkflow        : 10
lang                          : en-US
sessionconfigurationdata      : <SessionConfigurationData>
                                    <Param Name='PrivateData'>
                                        <PrivateData>
                                            <ParamName='enablevalidation' Value='True'/>
                                            <Param Name='allowedactivity'Value='PSDefaultActivities' />
                                            <Param Name='outofprocessactivity' Value='InlineScript'/>
                                            <Param Name='maxdisconnectedsessions' Value='200' />
                                            <ParamName='maxsessionsperworkflow' Value='10'/>
                                        </PrivateData>
                                    </Param>
                                </SessionConfigurationData>
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 25
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
outofprocessactivity          : InlineScript
SDKVersion                    : 2
Name                          : ITWorkflows
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
enablevalidation              : True
Enabled                       : True
maxdisconnectedsessions       : 200
MaxShellsPerUser              : 25
Permission                    :
```

Mit den ersten beiden Befehlen wird ein neues Sitzungs Konfigurationsobjekt erstellt und registriert.

Der dritte Befehl verwendet das `Get-PSSessionConfiguration` Cmdlet zum Aufrufen der itworkflows-Sitzungs Konfiguration und zum `Format-List` Anzeigen aller Eigenschaften der Sitzungs Konfiguration in einer Liste. Die Ausgabe zeigt die Workflow Optionen in der Sitzungs Konfiguration. Die Sitzungskonfiguration verfügt insbesondere über eine **MaxSessionsPerWorkflow** -Eigenschaft mit dem Wert 10 und eine **MaxDisconnectedSessions** -Eigenschaft mit dem Wert 200.

## PARAMETERS

### -Activityprocessidletimeoutsec

Bestimmt, wie lange jeder Aktivitätshostprozess beibehalten wird, nachdem er in den Leerlauf gewechselt ist. Wenn das Intervall abläuft, wird der Prozess geschlossen.

Geben Sie einen Wert in Sekunden ein. Der Standardwert beträgt ist 60.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zuordnung

Gibt die Aktivitäten an, die in der Sitzung ausgeführt werden dürfen.

Geben Sie mit Namespace qualifizierte Aktivitäts Namen ein, z `Microsoft.Powershell.HyperV.Activities.*` . b..
Platzhalterzeichen werden unterstützt. Der Standardwert **PSDefaultActivities** enthält die integrierten Windows Workflow Foundation-Aktivitäten und die Aktivitäten, die die zentralen Windows PowerShell-Cmdlets darstellen.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: PSDefaultActivities
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enablevalidation

Stellt sicher, dass alle Workflowaktivitäten in der Sitzung in der Liste zulässiger Aktivitäten enthalten sind.

Der Standardwert lautet „True“. Um die Validierung zu deaktivieren, verwenden Sie das folgende Befehls Format: `-EnableValidation:$false` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maxactivityprocesses

Gibt die maximale Anzahl von Prozessen an, die in der Sitzung zur Unterstützung von Workflowaktivitäten erstellt werden kann. Der Standardwert ist 5.

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

### -Maxconnectedsessions

Gibt die maximale Anzahl von Remotesitzungen an, die sich in einem betriebsbereiten Zustand befinden. Dieses Kontingent gilt für Sitzungen, die mit allen Remoteknoten (Zielcomputern) verbunden sind. Der Standardwert ist 100.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maxdisconnectedsessions

Gibt die maximale Anzahl von Remotesitzungen an, die sich in einem getrennten Zustand befinden. Dieses Kontingent gilt für Sitzungen, die mit allen Remoteknoten (Zielcomputern) verbunden sind. Der Standardwert lautet „1000“.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1000
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maxpersistencestoresizegb

Gibt die maximale Größe des Persistenzspeichers, der von in der Sitzung ausgeführten Workflows belegt wird, in GB an. Bei einer Überschreitung der Größe wird der Persistenzspeicher erweitert, um alle persistenten Daten zu speichern. Allerdings wird eine Warnung angezeigt und eine Meldung in das Workflow-Ereignisprotokoll geschrieben. Der Standardwert ist 10.

Der Persistenzspeicher enthält Daten für alle Workflowaufträge. Durch die Möglichkeit, Daten zu speichern, können die Aufträge fortgesetzt werden, ohne ihren Zustand zu verlieren.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maxrunningworkflows

Gibt die maximale Anzahl von Workflows an, die gleichzeitig in der Sitzung ausgeführt werden können.
Der Standardwert ist 30.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 30
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maxsessionsperremotenode

Gibt die maximale Anzahl von Sitzungen an, die mit jedem Remoteknoten (Zielcomputer) verbunden sein können. Der Standardwert ist 5.

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

### -Maxsessionsperworkflow

Gibt die maximale Anzahl von Sitzungen an, die zur Unterstützung jedes Workflows erstellt werden können. Der Standardwert ist 5.

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

### -Ouwesaprocessactivity

Bestimmt, für welche (durch den **AllowedActivities** -Parameter angegebenen) Aktivitäten die Out-of-Process-Ausführung zulässig ist. Der Standardwert ist **InlineScript**.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineScript
Accept pipeline input: False
Accept wildcard characters: False
```

### -Persistencepath

Gibt an, wo der Workflowzustand und Workflowdaten auf dem Datenträger gespeichert werden. Durch die Speicherung des Workflowzustands und der Workflowdaten können Workflows angehalten und fortgesetzt und nach Unterbrechungen und Netzwerkfehlern wiederhergestellt werden.

Der Standardwert ist `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Persistwithencryption

Gibt an, dass der Workflow die Daten im Persistenzspeicher verschlüsselt. Sie sollten dieses Feature beim Speichern von Persistenzdaten auf einer Netzwerkfreigabe verwenden.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remotenodesessionidletimeoutsec

Gibt an, wie lange eine mit einem Remoteknoten (Zielcomputer) verbundene Sitzung beibehalten wird, wenn sie sich im Leerlauf befindet.

Geben Sie einen Wert in Sekunden ein. Der Standardwert beträgt ist 60.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sessionthrottlelimit

Gibt an, wie viele Vorgänge erstellt werden, um alle in der Sitzung gestarteten Workflows zu unterstützen. Der Standardwert ist 100.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -Workflowshutdowntimeoutmsec

Gibt an, wie lange die Sitzung beibehalten wird, nachdem das Anhalten aller Workflows in der Sitzung erzwungen wurde. Nach Ablauf des Timeouts wird die Sitzung selbst dann von Windows PowerShell geschlossen, wenn noch nicht alle Workflows angehalten wurden.

Geben Sie einen Wert in Millisekunden ein.
Der Standardwert ist 500.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 500
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### Keine

Eingaben können nicht an dieses Cmdlet weitergereicht werden.

## AUSGABEN

### Microsoft. PowerShell. Commands. psworkflowexecutionoption

## HINWEISE

Wenn der maximale durch eine Option festgelegte Wert überschritten wird, verursacht der Befehl zum Erstellen einer weiteren Instanz in der Sitzung einen Fehler, sofern in der Parameterbeschreibung nichts anderes angegeben ist. Angenommen, der Wert von **MaxConnectedSessions** beträgt 100. In diesem Fall verursacht der Befehl zum Erstellen der Sitzung Nummer 101 für einen Remoteknoten (Zielcomputer) einen Fehler.

Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab. Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.

Insbesondere die Eigenschaften von Sitzungskonfigurationen, die ein **PSWorkflowExecutionOptions** -Objekt enthalten, variieren abhängig von den Workflowoptionswerten. Wenn die Sitzungskonfiguration beispielsweise ein **PSWorkflowExecutionOptions** -Objekt umfasst, durch das für die **SessionThrottleLimit** -Eigenschaft ein vom Standardwert abweichender Wert festgelegt wird, verfügt die Sitzungskonfiguration über eine **SessionThrottleLimit** -Eigenschaft. Andernfalls trifft dies nicht zu.

## VERWANDTE LINKS

[New-PSWorkflowSession](New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)
