---
description: Beschreibt das `ForEach -Parallel` Sprachkonstrukt in Windows PowerShell Workflow.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_foreach-parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Parallel about_Foreach
ms.openlocfilehash: 1012b45396b65d424dacac067c2af8d3b6823f92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221908"
---
# <a name="about-foreach-parallel"></a>Informationen zu Foreach-Parallel

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt das `ForEach -Parallel` Sprachkonstrukt in Windows PowerShell Workflow.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Der **parallele** Parameter des `ForEach` Schlüssel Worts führt die Befehle in einem `ForEach` Skriptblock einmal für jedes Element in einer bestimmten Auflistung aus.

Die Elemente in der Auflistung, z. b. ein Datenträger in einer Sammlung von Datenträgern, werden parallel verarbeitet. Die Befehle im Skriptblock werden sequenziell für jedes Element in der Sammlung ausgeführt.

`ForEach -Parallel` ist nur in einem Windows PowerShell-Workflow gültig.

### <a name="syntax"></a>SYNTAX

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a>DETAILLIERTE BESCHREIBUNG

Wie die foreach-Anweisung in Windows PowerShell muss die Variable, die die Auflistung enthält, `$<collection>` vor der-Anweisung definiert werden `ForEach -Parallel` , aber die Variable, die das aktuelle Element darstellt, `$<item>` wird in der- `ForEach -Parallel` Anweisung definiert.

Das `ForEach -Parallel` -Konstrukt unterscheidet sich vom `ForEach` -Schlüsselwort und dem **parallel** -Parameter. Mit dem- `ForEach` Schlüsselwort werden die Elemente in der-Auflistung nacheinander verarbeitet. Der **parallele** Parameter führt Befehle parallel in einem Skriptblock aus. Sie können einen parallelen Skriptblock in einen `ForEach -Parallel` Skriptblock einschließen.

Die Zielcomputer in einem Workflow, z. b. die durch den allgemeinen Workflow Parameter **pscomputername** angegebenen, werden immer parallel verarbeitet.
Sie müssen `ForEach -Parallel` für diesen Zweck nicht das Schlüsselwort angeben.

### <a name="examples"></a>BEISPIELE

Der folgende Workflow enthält eine-Anweisung, die die Datenträger verarbeitet, die von der-Aktivität abgerufen werden `ForEach -Parallel` `Get-Disk` . Die Befehle im `ForEach -Parallel` Skriptblock werden nacheinander ausgeführt, auf den Datenträgern werden Sie jedoch parallel ausgeführt. Die Datenträger werden möglicherweise gleichzeitig und in beliebiger Reihenfolge verarbeitet.

```powershell
workflow Test-Workflow
{
    $Disks = Get-Disk

    # The disks are processed in parallel.
    ForEach -Parallel ($Disk in $Disks)
    {
        # The commands run sequentially on each disk.
        $DiskPath = $Disk.Path
        $Disk | Initialize-Disk
        Set-Disk -Path $DiskPath
    }
}

workflow Test-Workflow
{
    #Run commands in parallel.
    Parallel
    {
        Get-Process
        Get-Service
    }

   $Disks = Get-Disk

   # The disks are processed in parallel.
   ForEach -Parallel ($Disk in $Disks)
   {
       # The commands run in parallel on each disk.
       Parallel
       {
           Initialize-Disk
           InlineScript {.\Get-DiskInventory}
       }
   }
}
```

## <a name="see-also"></a>SIEHE AUCH

[Writing a Script Workflow](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)
