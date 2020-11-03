---
description: Beschreibt das `Sequence` Schlüsselwort, das ausgewählte Aktivitäten sequenziell ausführt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_sequence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über_Sequence
ms.openlocfilehash: a9dd4fb24274fe4e1478ca69c734b43a2f196792
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221884"
---
# <a name="about-sequence"></a>Informationen zur Sequenz

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt das `Sequence` Schlüsselwort, das ausgewählte Aktivitäten sequenziell ausführt.

## <a name="long-description"></a>Lange Beschreibung

Das `Sequence` Schlüsselwort führt ausgewählte Workflow Aktivitäten sequenziell aus. Workflow Aktivitäten werden in der Reihenfolge ausgeführt, in der Sie angezeigt werden und nicht gleichzeitig ausgeführt werden. Das `Sequence` Schlüsselwort ist nur in einem PowerShell-Workflow gültig.

Das `Sequence` Schlüsselwort wird in einem `Parallel` Skriptblock verwendet, um ausgewählte Befehle sequenziell auszuführen.

Da Workflow Aktivitäten standardmäßig sequenziell ausgeführt werden, `Sequence` ist das Schlüsselwort nur in einem `Parallel` Skriptblock wirksam. Wenn das `Sequence` Schlüsselwort nicht in einem `Parallel` Skriptblock enthalten ist, ist es gültig, aber nicht wirksam.

`Sequence`Mit dem Script-Block können Sie weitere Befehle parallel ausführen, indem Sie abhängige Befehle sequenziell ausführen können.

## <a name="syntax"></a>Syntax

### <a name="workflow-using-sequence"></a>Workflow mit Sequenz

```
workflow <Verb-Noun>
{
    Sequence
    {
        [<Activity>]
        [<Activity>]
        # ...
    }
}
```

### <a name="workflow-using-parallel-and-sequence"></a>Workflow mit parallel und Sequence

```
workflow <Verb-Noun>
{
    Parallel
    {
        [<Activity>]
        Sequence
        {
            [<Activity>]
            [<Activity>]
            # ...
        }
    }
}
```

## <a name="detailed-description"></a>Detaillierte Beschreibung

Die Befehle in einem `Parallel`-Skriptblock können gleichzeitig ausgeführt werden. Die Reihenfolge, in der sie ausgeführt werden, ist nicht festgelegt. Diese Funktion verbessert die Leistung eines Skript Workflows.

Sie können einen `Sequence` Skriptblock verwenden, um ausgewählte Aktivitäten sequenziell auszuführen, auch wenn die Aktivitäten in einem `Parallel` Skriptblock angezeigt werden.

Die Aktivitäten in einem `Sequence` Skriptblock werden nacheinander in der Reihenfolge ausgeführt, in der Sie aufgelistet sind. Eine Aktivität in einem `Sequence` Skriptblock wird erst gestartet, nachdem die vorherige Aktivität abgeschlossen wurde.

Wenn der Skriptblock jedoch `Sequence` in einem `Parallel` Skriptblock angezeigt wird, wird die Reihenfolge, in der der `Sequence` Skriptblock ausgeführt wird, nicht ermittelt. Sie kann vor, nach oder gleichzeitig mit anderen Aktivitäten im `Parallel` Skriptblock ausgeführt werden.

Der folgende Workflow enthält z. b `Parallel` . einen Skriptblock, der Aktivitäten ausführt, die Prozesse und Dienste auf dem Computer erhalten. Der `Parallel` Skriptblock enthält einen `Sequence` Skriptblock, der Informationen aus einer Datei abruft und die Informationen als Eingabe für ein Skript verwendet.

Die `Get-Process` `Get-Service` -,-und-hotfixbezogenen Befehle sind voneinander unabhängig. Die Befehle können gleichzeitig oder in beliebiger Reihenfolge ausgeführt werden. Der Befehl, mit dem die Hotfixinformationen abgerufen werden, muss jedoch vor dem Befehl ausgeführt werden, der ihn verwendet.

```powershell
workflow Test-Workflow
{
    Parallel
    {
    Get-Process
    Get-Service

    Sequence
    {
        $Hotfix = Get-Content 'D:\HotFixes\Required.txt'
        Foreach ($h in $Hotfix) {'D:\Scripts\Verify-Hotfix' -Hotfix $h}
        }
    }
}
```

## <a name="see-also"></a>Weitere Informationen:

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach parallel](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)

[Erstellen eines Workflows mit einem Windows PowerShell-Skript](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
