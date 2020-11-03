---
description: Beschreibt die- `Suspend-Workflow` Aktivität, die den Workflow anhält, in dem die-Aktivität angezeigt wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_suspend-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Workflow about_Suspend
ms.openlocfilehash: cbe5386ae5aa4bd863079fde240ddf2ce5384727
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221863"
---
# <a name="about-suspend-workflow"></a>Informationen zu Suspend-Workflow

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt die- `Suspend-Workflow` Aktivität, die den Workflow anhält, in dem die-Aktivität angezeigt wird.

## <a name="long-description"></a>Lange Beschreibung

Die- `Suspend-Workflow` Aktivität beendet die Workflow Verarbeitung vorübergehend innerhalb des Workflows. Vor dem Anhalten nimmt der Windows PowerShell-Workflow einen Prüfpunkt an, sodass der Zustand und die Daten des Workflows beibehalten werden und der Workflow vom Unterbrechungs Punkt fortgesetzt werden kann.

Zum Fortsetzen des Workflows verwendet der Benutzer, der den Workflow durchführt, das- `Resume-Job` Cmdlet. Ein Workflow kann nicht innerhalb des Workflows fortgesetzt werden.

## <a name="syntax"></a>Syntax

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a>Detaillierte Beschreibung

`Suspend-Workflow`Beendet den Workflow vorübergehend und gibt ein Auftrags Objekt zurück, das den Workflow Auftrag darstellt. Ein Auftrags Objekt wird auch dann zurückgegeben, wenn Sie den Workflow nicht als Auftrag ausgeführt haben. Beispielsweise mit dem allgemeinen Workflow Parameter **AsJob** . Der Auftrags **Status ist "** angehalten".

Sie können die Job-Cmdlets verwenden, um den angehaltenen Workflow Auftrag zu verwalten. Verwenden Sie das-Cmdlet, um den Workflow Auftrag fortzusetzen `Resume-Job` .

Wenn Sie den Workflow Auftrag fortsetzen, wird der Workflow mit dem Befehl fortgesetzt, der der `Suspend-Workflow` Aktivität folgt.

Der folgende Workflow schließt z. b. die- `Suspend-Workflow` Aktivität ein.
Wenn Sie den Workflow ausführen, führt er die- `Get-Date` Aktivität aus, speichert die Ausgabe in der `$a` Variablen, hält den Workflow an und gibt ein Auftrags Objekt zurück, das den angehaltenen Workflow darstellt. Der Auftragstyp ist " **psworkflowjob** ".

Sie können die Job-Cmdlets, z `Get-Job` . b., verwenden, um den Workflow Auftrag zu verwalten.

```powershell
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

Test-Suspend
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Suspended  True         localhost Test-Suspend
```

## <a name="resuming-a-workflow-job"></a>Fortsetzen eines Workflow Auftrags

Verwenden Sie das-Cmdlet, um den Workflow Auftrag fortzusetzen `Resume-Job` . Das Cmdlet `Resume-Job` gibt das Workflowauftragsobjekt sofort zurück, obgleich es möglicherweise noch nicht fortgesetzt wurde. Um zu warten, bis der Auftrag fortgesetzt wird, verwenden Sie den **Wait** -Parameter, oder verwenden Sie das `Get-Job` Cmdlet, um das aktuelle Auftrags Objekt zu erhalten.

```powershell
Resume-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State    HasMoreData  Location  Command
--  ----  -------------  -----    -----------  --------  -------
8   Job8  PSWorkflowJob  Running  True         localhost Test-Suspend
```

```powershell
Get-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Completed  True         localhost Test-Suspend
```

## <a name="getting-the-output-of-a-workflow-job"></a>Erhalten der Ausgabe eines Workflow Auftrags

Verwenden Sie das-Cmdlet, um die Ausgabe eines Workflow Auftrags zu erhalten `Receive-Job` . Die Ausgabe zeigt, dass der Workflow mit dem Befehl fortgesetzt wird, der mit dem `Suspend-Workflow` Cmdlet gefolgt ist. Der Wert der `$a` Variablen, die vor der Unterbrechung aufgefüllt wurde, ist für den Workflow verfügbar, wenn er fortgesetzt wird.

```powershell
Get-Job -Name Job8 | Receive-Job
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 19
Milliseconds      : 823
Ticks             : 198230041
TotalDays         : 0.000229432917824074
TotalHours        : 0.00550639002777778
TotalMinutes      : 0.330383401666667
TotalSeconds      : 19.8230041
TotalMilliseconds : 19823.0041
PSComputerName    : localhost
```

## <a name="see-also"></a>Weitere Informationen:

[about_Workflows](about_Workflows.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

[Psworkflow](xref:PSWorkflow) -Cmdlets

[Handbuch zu Workflows](/previous-versions/powershell/scripting/components/workflows-guide)

[Schreiben Sie einen Windows PowerShell-Workflow](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
