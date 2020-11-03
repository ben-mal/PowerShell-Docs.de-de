---
description: Beschreibt die Checkpoint-Workflow-Aktivität, die einen Prüfpunkt in einem Workflow annimmt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_checkpoint-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Workflow about_Checkpoint
ms.openlocfilehash: 223deb07ff6ed387cf04736116ea0ce3f998bb59
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221911"
---
# <a name="about-checkpoint-workflow"></a>Informationen zu Checkpoint-Workflow

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt die Checkpoint-Workflow-Aktivität, die einen Prüfpunkt in einem Workflow annimmt.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Die Checkpoint-Workflow-Aktivität nimmt einen Prüfpunkt an, der den Zustand und die Daten im Workflow speichert. Wenn der Workflow angehalten oder unterbrochen wird, kann er vom letzten Prüfpunkt aus fortgesetzt werden, anstatt neu gestartet werden zu müssen.

Die Checkpoint-Workflow Aktivität ist nur in einem Workflow gültig.

### <a name="syntax"></a>SYNTAX

```
Workflow <Verb-Noun>
{
    Checkpoint-Workflow
}
```

Die Checkpoint-Workflow-Aktivität akzeptiert keine Parameter, einschließlich der allgemeinen Parameter und allgemeinen Workflow Parameter.

Sie können den Checkpoint-Activity Prüfpunkt an einer beliebigen Stelle in einem Workflow nach der cmdletbinding-oder Param-Anweisung platzieren. Beim Platzieren von Prüfpunkten sollten Sie jedoch die Leistungseinbußen beim Sammeln der Daten und beim Schreiben der Daten auf den Datenträger auf dem Computer, auf dem der Workflow ausgeführt wird, überprüfen.

Sie können davon ausgehen, dass der Zeitaufwand für die erneute Ausführung eines unterbrochenen Workflowabschnitts höher ist als der Zeitaufwand für das Schreiben von Prüfpunktstatus und -daten auf den Datenträger.

Sie sollten Prüfpunkte nach kritischen Schritten übernehmen, damit der Workflow fortgesetzt werden kann, anstatt neu gestartet zu werden. Nehmen Sie z. b. einen Prüfpunkt auf, der nicht idempotent ist.

### <a name="about-checkpoints"></a>Informationen zu Prüfpunkten

Ein Prüfpunkt ist eine Momentaufnahme des aktuellen Zustands des Workflows, einschließlich der aktuellen Werte von Variablen, und beliebiger, bis zu diesem Punkt generierter Ausgaben, die auf dem Datenträger gespeichert wird.

Wenn ein Workflow absichtlich oder versehentlich unterbrochen wird, verwendet der Windows PowerShell-Workflow automatisch die Daten im neuesten Prüfpunkt, um den Workflow wiederherzustellen und fortzusetzen.

Wenn Sie den Workflow als Auftrag ausführen, z. b. mit dem allgemeinen Workflow Parameter AsJob, werden die Workflow Prüfpunkte so lange beibehalten, bis Sie den Auftrag löschen, z. b. mithilfe des Remove-Job-Cmdlets.
Andernfalls werden Workflow Prüfpunkte gelöscht, wenn der Workflow abgeschlossen ist.

### <a name="other-checkpointing-techniques"></a>andere Prüf Punkt Techniken

Zusätzlich zur Checkpoint-Workflow Aktivität unterstützt der Windows PowerShell-Workflow auch andere Prüf Punkt Techniken, einschließlich der folgenden:

- Allgemeiner Workflowparameter "PSPersist"
- Allgemeiner Aktivitätsparameter "PSPersist"
- Pspersistpreference-Variable (in einem Workflow)

Weitere Informationen zum Hinzufügen eines Prüf Punkts zu einem Workflow finden Sie unter "Vorgehensweise beim Hinzufügen von Prüfpunkten zu einem Workflow".

## <a name="examples"></a>BEISPIELE

Der folgende Workflow schließt einen aufzurufenden Checkpoint-Workflow Aktivität ein, nachdem eine Funktion mit langer Laufzeit und ein Skript, das Daten gemeinsam nutzen, fertiggestellt wurden.

```powershell
Workflow Test-Workflow
{
    $a = Invoke-LongRunningFunction
    InlineScript { \\Server\Share\Get-DataPacks.ps1 $Using:a}
    Checkpoint-Workflow

    Invoke-LongRunningFunction
    {
        ...
    }
}
```

## <a name="see-also"></a>SIEHE AUCH

[Schreiben Sie einen Windows PowerShell-Workflow](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
