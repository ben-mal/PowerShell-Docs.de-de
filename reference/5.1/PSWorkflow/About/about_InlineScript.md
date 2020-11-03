---
description: Beschreibt die- `InlineScript` Aktivität, mit der PowerShell-Befehle in einem Workflow ausgeführt werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_inlinescript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über_InlineScript
ms.openlocfilehash: 2eaeb02c6441865551b586e27a39c4000826752b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221903"
---
# <a name="about-inlinescript"></a>Informationen zu InlineScript

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt die- `InlineScript` Aktivität, mit der PowerShell-Befehle in einem Workflow ausgeführt werden.

## <a name="long-description"></a>Lange Beschreibung

Die `InlineScript` -Aktivität führt Befehle im Workflow einer freigegebenen PowerShell-Sitzung aus. `InlineScript` ist nur in Workflows gültig.

## <a name="syntax"></a>Syntax

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a>Detaillierte Beschreibung

Die- `InlineScript` Aktivität führt Befehle in einer freigegebenen PowerShell-Sitzung aus. Sie können Sie in einen Workflow einschließen, um Befehle auszuführen, die Daten und Befehle gemeinsam verwenden, die in einem Workflow nicht anderweitig gültig sind.

Der `InlineScript` Skriptblock kann alle gültigen PowerShell-Befehle und-Ausdrücke enthalten. Da die Befehle und Ausdrücke in einem `InlineScript` Skriptblock in derselben Sitzung ausgeführt werden, werden alle Zustände und Daten gemeinsam genutzt, einschließlich der importierten Module und der Werte von Variablen.

Sie können eine `InlineScript` Aktivität an beliebiger Stelle in einem Workflow oder einem geschachtelten Workflow platzieren, einschließlich innerhalb einer Schleife oder einer Steuerelement Anweisung oder eines parallelen oder Sequenz Skript Blocks.

Die `InlineScript` Aktivität verfügt über die allgemeinen Aktivitäts Parameter, einschließlich **pspersist**. Die Befehle und Ausdrücke in einem `InlineScript` Skriptblock verfügen jedoch nicht über die Workflow Funktionen, wie z. b. Prüfpunkte, Persistenz und allgemeine Workflow-oder Aktivitäts Parameter. Weitere Informationen finden Sie unter [about_ActivityCommonParameters](about_ActivityCommonParameters.md).

## <a name="inlinescript-variables"></a>InlineScript-Variablen

Standardmäßig sind die Variablen, die in einem Workflow definiert sind, für die Befehle im `InlineScript` Skriptblock nicht sichtbar. Um Workflow Variablen für sichtbar zu machen `InlineScript` , verwenden Sie den bereichsmodifizierer `$Using` . Der bereichsmodifizierer `$Using` ist nur einmal für jede Variable in der erforderlich `InlineScript` .

Weitere Informationen zum bereichsmodifizierer finden Sie unter `$Using` [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).

Das folgende Beispiel zeigt, dass der bereichsmodifizierer `$Using` den Wert der `$a` Workflow Variablen der obersten Ebene für die Befehle im `InlineScript` Skriptblock verfügbar macht.

```powershell
workflow Test-Workflow {
  $a = 3

  ## Without $Using, the $a workflow variable isn't visible
  ## in inline script.
  InlineScript {"Inline A0 = $a"}

  ## $Using imports the variable and its current value.
  InlineScript {"Inline A1 = $Using:a"}
}

Test-Workflow
```

```output
Inline A0 =
Inline A1 = 3
```

## <a name="returning-variables-in-inlinescript"></a>Zurückgeben von Variablen in InlineScript

`InlineScript` Befehle können den Wert der Variablen ändern, die aus dem Workflow Bereich importiert wurde, aber die Änderungen sind im Workflow Bereich nicht sichtbar. Damit dies dort der Fall ist, geben Sie den geänderten Wert an den Workflowbereich zurück, wie im folgenden Beispiel dargestellt.

```powershell
workflow Test-Workflow {
  $a = 3

  ##  Changes to the InlineScript variable value don't
  ##  change the workflow variable.
  InlineScript {
    $a = $Using:a+1;
    "Inline A = $a"
  }
  "Workflow A = $a"

  ##  To change the variable in workflow scope, return the
  ##  new value.
  $a = InlineScript {$b = $Using:a+1; $b}
  "Workflow New A = $a"
}

Test-Workflow
```

```output
Inline A = 4
Workflow A = 3
Workflow New A = 4
```

> [!NOTE]
> Eine-Anweisung mit dem bereichsmodifizierer `$Using` sollte vor jeder Verwendung der Variablen im `InlineScript` Skriptblock angezeigt werden.

## <a name="running-in-process"></a>Prozess interne Ausführung

Um die Zuverlässigkeit zu verbessern, werden die Befehle im `InlineScript` Skriptblock in einem eigenen Prozess ausgeführt, getrennt vom Prozess, in dem der Workflow ausgeführt wird, und dann die Ausgabe an den Workflow Prozess zurückgeben.

Um PowerShell anzuweisen, die `InlineScript` Aktivität im Workflow Prozess auszuführen, entfernen Sie den `InlineScript` Wert aus der **ouesfprocessactivity** -Eigenschaft der Sitzungs Konfiguration, z. b. mithilfe des- `New-PSWorkflowExecutionOption` Cmdlets.

### <a name="example"></a>Beispiel

Der `InlineScript` im folgenden Workflow enthält Befehle, die in PowerShell gültig sind, aber in Workflows nicht gültig sind. Beispielsweise das `New-Object` Cmdlet mit dem **ComObject** -Parameter.

```powershell
workflow Test-Workflow
{
  $ie = InlineScript {
    $ie = New-Object -ComObject InternetExplorer.Application -Property @{navigate2="www.microsoft.com"}

    $ie.Visible = $true
  }

  $ie
}

Test-Workflow
```

## <a name="see-also"></a>Weitere Informationen:

[Informationen über_ActivityCommonParameters](about_ActivityCommonParameters.md)

[about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

[Psworkflow](xref:PSWorkflow) -Cmdlets

[Handbuch zu Workflows](/previous-versions/powershell/scripting/components/workflows-guide)

[Schreiben Sie einen Windows PowerShell-Workflow](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
