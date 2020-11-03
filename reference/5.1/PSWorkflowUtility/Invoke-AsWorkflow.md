---
external help file: Microsoft.PowerShell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSWorkflowUtility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflowutility/invoke-asworkflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-AsWorkflow
ms.openlocfilehash: b96bce9fe4d574fe2b7e9c7c0f1e05ee0508adce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213356"
---
# Invoke-AsWorkflow

## ZUSAMMENFASSUNG
Führt einen Befehl oder Ausdruck als Windows PowerShell-Workflow aus.

## SYNTAX

### Befehl (Standard)

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### Ausdruck

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## DESCRIPTION

Der `Invoke-AsWorkflow` Workflow führt einen beliebigen Befehl oder Ausdruck als Inline Skript in einem Workflow aus.
Diese Workflows nutzen die standardmäßige Workflowsemantik, verfügen über alle allgemeinen Workflowparameter und bieten sämtliche Vorteile von Workflows, einschließlich der Möglichkeit, einen Workflow zu beenden, fortzusetzen und wiederherzustellen.

Workflows sind für Befehle mit langer Ausführungsdauer konzipiert, die wichtige Daten sammeln, können aber zur Ausführung jedes Befehls verwendet werden.
Weitere Informationen finden Sie unter [about_Workflows](../PSWorkflow/About/about_Workflows.md).

Sie können diesem Befehl auch allgemeine Workflowparameter hinzufügen.
Weitere Informationen zu allgemeinen Workflow Parametern finden Sie unter [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)

Dieser Workflow wird in Windows PowerShell 3.0 eingeführt.

## BEISPIELE

### Beispiel 1: Ausführen eines Cmdlets als Workflow

```powershell
Invoke-AsWorkflow -PSComputerName (Get-Content Servers.txt) -CommandName Get-ExecutionPolicy
```

```output
PSComputerName                     PSSourceJobInstanceId                   Value
--------------                     ---------------------                   -----
Server01                           77b1cdf8-8226-4662-9067-cd2fa5c3b711    AllSigned
Server02                           a33542d7-3cdd-4339-ab99-0e7cd8e59462    Unrestricted
Server03                           279bac28-066a-4646-9497-8fcdcfe9757e    AllSigned
localhost                          0d858009-2cc4-47a4-a2e0-da17dc2883d0    RemoteSigned
```

Mit diesem Befehl wird das `Get-ExecutionPolicy` Cmdlet als Workflow auf Hunderten von Computern ausgeführt.

Der Befehl verwendet den **CommandName** -Parameter, um das im Workflow ausgeführte Cmdlet anzugeben.
Er verwendet den allgemeinen Workflowparameter **PSComputerName** zur Angabe der Computer, auf denen der Befehl ausgeführt wird.
Der Wert des **pscomputername** -Parameters ist ein `Get-Content` Befehl, mit dem eine Liste der Computernamen aus der Servers.txt Datei abgerufen wird.
Der Parameterwert wird in Klammern eingeschlossen, um Windows PowerShell anzuweisen, den `Get-Command` Befehl vor der Verwendung des-Werts auszuführen.

Wie bei allen Remotebefehlen müssen Sie Windows PowerShell mit der Option „Als Administrator ausführen“ starten, wenn der Befehl auf dem lokalen Computer ausgeführt wird (wenn der Wert des PSComputerName-Parameters den lokalen Computer enthält).

### Beispiel 2: Ausführen eines Cmdlets mit Parametern

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

Der erste Befehl verwendet das `Import-Csv` Cmdlet, um ein Objekt aus dem Inhalt in der Servers.csv-Datei zu erstellen. Der Befehl verwendet den- `Header` Parameter, um eine `ServerName` Eigenschaft für die Spalte zu erstellen, die die Namen der Zielcomputer enthält, die auch als "Remote Knoten" bezeichnet werden. Der Befehl speichert das Ergebnis in der `$s` Variablen.

Der zweite Befehl verwendet den `Invoke-AsWorkflow` Workflow, um einen `Get-ExecutionPolicy` Befehl auf den Computern in der Servers.csv-Datei auszuführen. Der Befehl verwendet den **CommandName** -Parameter von `Invoke-AsWorkflow`  , um den Befehl anzugeben, der im Workflow ausgeführt werden soll. Er verwendet den- `Parameter` Parameter von `Invoke-AsWorkflow` , um den- `Scope` Parameter des `Get-ExecutionPolicy` Cmdlets mit dem Wert **Process** anzugeben. Der Befehl verwendet außerdem den `PSConnectionRetryCount` allgemeinen Workflow Parameter, um den Befehl auf fünf Versuche auf den einzelnen Computern und den `PSComputerName` allgemeinen Workflow Parameter zu begrenzen, um die Namen der Remote Knoten (Zielcomputer) anzugeben. Der Wert des- `PSComputerName` Parameters ist ein Ausdruck, der die- `ServerName` Eigenschaft jedes Objekts in der Variablen abruft `$s` .

Diese Befehle führen einen `Get-ExecutionPolicy` Befehl als Workflow auf Hunderten von Computern aus.
Der Befehl verwendet den- `Scope` Parameter des `Get-ExecutionPolicy` Cmdlets mit dem Wert **Process** , um die Ausführungs Richtlinie in der aktuellen Sitzung zu erhalten.

### Beispiel 3: Ausführen eines Ausdrucks als Workflow

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

Dieser Befehl verwendet den `Invoke-AsWorkflow` Workflow, um einen ipconfig-Befehl als Workflow Auftrag auf den Computern auszuführen, die in der DomainControllers.txt-Datei aufgelistet sind.

Der Befehl verwendet den- `Expression` Parameter, um den Ausdruck anzugeben, der ausgeführt werden soll.
Er verwendet den `PSComputerName` allgemeinen Workflow Parameter, um die Namen der Remote Knoten (Zielcomputer) anzugeben.

Der Befehl verwendet außerdem die `AsJob` `JobName` allgemeinen Workflow Parameter und, um den Workflow als Hintergrund Auftrag auf jedem Computer mit dem Auftrags Namen "ipconfig" auszuführen.

Der Befehl gibt ein- `ContainerParentJob` Objekt ( `System.Management.Automation.ContainerParentJob` ) zurück, das die Workflow Aufträge auf jedem Computer enthält.

## PARAMETERS

### -CommandName

Führt das angegebene Cmdlet oder die angegebene erweiterte Funktion als Workflow aus.
Geben Sie den Cmdlet-oder Funktionsnamen ein, z `Update-Help` `Set-ExecutionPolicy` . b., oder `Set-NetFirewallRule` .

```yaml
Type: System.String
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ausdruck

Gibt den Ausdruck an, den dieses Cmdlet als Workflow ausführt.
Geben Sie den Ausdruck als Zeichenfolge ein, z `"ipconfig /all"` . b..
Wenn der Ausdruck Leerzeichen oder Sonderzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.

```yaml
Type: System.String
Parameter Sets: Expression
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter

Gibt die Parameter und Parameterwerte des Befehls an, der im-Parameter angegeben ist `CommandName` .
Geben Sie eine Hash Tabelle ein, in der jeder Schlüssel ein Parameter Name und sein Wert der Parameterwert ist, z `@{ExecutionPolicy="AllSigned"}` . b..

Weitere Informationen zu Hash Tabellen finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Wird verwendet, um Pipeline Eingaben zu ermöglichen.

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

### Workflowcommonparameters

Dieses Cmdlet unterstützt auch Workflow spezifische allgemeine Parameter.
Weitere Informationen finden Sie unter [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).

## EINGABEN

### System.Object

Sie können jedes beliebige Objekt an den- `InputObject` Parameter übergeben.

## AUSGABEN

### Keine

Dieser Befehl generiert keine Ausgabe.
Er führt allerdings den Workflow aus, der eine Ausgabe generieren kann.

## HINWEISE

## VERWANDTE LINKS

[New-PSWorkflowExecutionOption](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[New-PSWorkflowSession](../PSWorkflow/New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_Workflow_Common_Parameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)
