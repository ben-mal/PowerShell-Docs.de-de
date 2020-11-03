---
description: Beschreibt das parallele Schlüsselwort, mit dem die Aktivitäten in einem Workflow parallel ausgeführt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parallel
ms.openlocfilehash: 402e93672bbea4ec9b6bfda8d608f266f6c40a21
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221892"
---
# <a name="about-parallel"></a>Informationen zu parallel

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt das parallele Schlüsselwort, mit dem die Aktivitäten in einem Workflow parallel ausgeführt werden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Das Schlüsselwort "parallel" führt Workflow Aktivitäten parallel aus. Dieses Schlüsselwort ist nur in Windows PowerShell-Workflows gültig.

### <a name="syntax"></a>SYNTAX

```
workflow <Verb-Noun>
{
     Parallel
     {
          [<Activity>]
          [<Activity>]
        ...
     }
 }
```

## <a name="detailed-description"></a>DETAILLIERTE BESCHREIBUNG

Die Befehle in einem Parallel-Skriptblock können gleichzeitig ausgeführt werden. Die Reihenfolge, in der sie ausgeführt werden, ist nicht festgelegt.

Der folgende Workflow enthält beispielsweise einen Parallel-Skriptblock, der Aktivitäten ausführt, die Prozesse und Dienste auf dem Computer abrufen. Da die Befehle Get-Process und Get-Service unabhängig voneinander sind, können Sie gleichzeitig und in beliebiger Reihenfolge ausgeführt werden.

```powershell
workflow Test-Workflow
{
    Parallel
    {
         Get-Process
         Get-Service
    }
}
```

Das parallele Ausführen von Befehlen ist sehr effizient und verkürzt die Zeit, die zum Ausführen eines Workflows benötigt wird.

Verwenden Sie das Sequence-Schlüsselwort, um ausgewählte Befehle in einem parallelen Skriptblock in sequenzieller Reihenfolge auszuführen. Weitere Informationen finden Sie unter about_Sequence.

Um einen parallelen Skriptblock für Elemente in einer Auflistung auszuführen, verwenden Sie die Schlüsselwörter foreach oder foreach-parallel.

## <a name="see-also"></a>SIEHE AUCH

["Schreiben eines Skript Workflows"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach parallel](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[Informationen über_Sequence](about_Sequence.md)

[about_Workflows](about_workflows.md)
