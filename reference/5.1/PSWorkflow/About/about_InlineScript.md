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
# <a name="about-inlinescript"></a><span data-ttu-id="8dbc2-104">Informationen zu InlineScript</span><span class="sxs-lookup"><span data-stu-id="8dbc2-104">About InlineScript</span></span>

## <a name="short-description"></a><span data-ttu-id="8dbc2-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dbc2-105">Short description</span></span>

<span data-ttu-id="8dbc2-106">Beschreibt die- `InlineScript` Aktivität, mit der PowerShell-Befehle in einem Workflow ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-106">Describes the `InlineScript` activity, that runs PowerShell commands in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="8dbc2-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dbc2-107">Long description</span></span>

<span data-ttu-id="8dbc2-108">Die `InlineScript` -Aktivität führt Befehle im Workflow einer freigegebenen PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-108">The `InlineScript` activity runs commands in a shared PowerShell session's workflow.</span></span> <span data-ttu-id="8dbc2-109">`InlineScript` ist nur in Workflows gültig.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-109">`InlineScript` is only valid in workflows.</span></span>

## <a name="syntax"></a><span data-ttu-id="8dbc2-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="8dbc2-110">Syntax</span></span>

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a><span data-ttu-id="8dbc2-111">Detaillierte Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dbc2-111">Detailed description</span></span>

<span data-ttu-id="8dbc2-112">Die- `InlineScript` Aktivität führt Befehle in einer freigegebenen PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-112">The `InlineScript` activity runs commands in a shared PowerShell session.</span></span> <span data-ttu-id="8dbc2-113">Sie können Sie in einen Workflow einschließen, um Befehle auszuführen, die Daten und Befehle gemeinsam verwenden, die in einem Workflow nicht anderweitig gültig sind.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-113">You can include it in a workflow to run commands that share data and commands that aren't otherwise valid in a workflow.</span></span>

<span data-ttu-id="8dbc2-114">Der `InlineScript` Skriptblock kann alle gültigen PowerShell-Befehle und-Ausdrücke enthalten.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-114">The `InlineScript` script block can include all valid PowerShell commands and expressions.</span></span> <span data-ttu-id="8dbc2-115">Da die Befehle und Ausdrücke in einem `InlineScript` Skriptblock in derselben Sitzung ausgeführt werden, werden alle Zustände und Daten gemeinsam genutzt, einschließlich der importierten Module und der Werte von Variablen.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-115">Because the commands and expressions in an `InlineScript` script block run in the same session, they share all state and data, including imported modules and the values of variables.</span></span>

<span data-ttu-id="8dbc2-116">Sie können eine `InlineScript` Aktivität an beliebiger Stelle in einem Workflow oder einem geschachtelten Workflow platzieren, einschließlich innerhalb einer Schleife oder einer Steuerelement Anweisung oder eines parallelen oder Sequenz Skript Blocks.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-116">You can place an `InlineScript` activity anywhere in a workflow or nested workflow, including inside a loop or control statement or a Parallel or Sequence script block.</span></span>

<span data-ttu-id="8dbc2-117">Die `InlineScript` Aktivität verfügt über die allgemeinen Aktivitäts Parameter, einschließlich **pspersist**.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-117">The `InlineScript` activity has the activity common parameters, including **PSPersist**.</span></span> <span data-ttu-id="8dbc2-118">Die Befehle und Ausdrücke in einem `InlineScript` Skriptblock verfügen jedoch nicht über die Workflow Funktionen, wie z. b. Prüfpunkte, Persistenz und allgemeine Workflow-oder Aktivitäts Parameter.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-118">However, the commands and expressions in an `InlineScript` script block don't have the workflow features such as checkpointing, or persistence, and workflow or activity common parameters.</span></span> <span data-ttu-id="8dbc2-119">Weitere Informationen finden Sie unter [about_ActivityCommonParameters](about_ActivityCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="8dbc2-119">For more information, see [about_ActivityCommonParameters](about_ActivityCommonParameters.md).</span></span>

## <a name="inlinescript-variables"></a><span data-ttu-id="8dbc2-120">InlineScript-Variablen</span><span class="sxs-lookup"><span data-stu-id="8dbc2-120">InlineScript Variables</span></span>

<span data-ttu-id="8dbc2-121">Standardmäßig sind die Variablen, die in einem Workflow definiert sind, für die Befehle im `InlineScript` Skriptblock nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-121">By default, the variables that are defined in a workflow aren't visible to the commands in the `InlineScript` script block.</span></span> <span data-ttu-id="8dbc2-122">Um Workflow Variablen für sichtbar zu machen `InlineScript` , verwenden Sie den bereichsmodifizierer `$Using` .</span><span class="sxs-lookup"><span data-stu-id="8dbc2-122">To make workflow variables visible to the `InlineScript`, use the `$Using` scope modifier.</span></span> <span data-ttu-id="8dbc2-123">Der bereichsmodifizierer `$Using` ist nur einmal für jede Variable in der erforderlich `InlineScript` .</span><span class="sxs-lookup"><span data-stu-id="8dbc2-123">The `$Using` scope modifier is required only once for each variable in the `InlineScript`.</span></span>

<span data-ttu-id="8dbc2-124">Weitere Informationen zum bereichsmodifizierer finden Sie unter `$Using` [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="8dbc2-124">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

<span data-ttu-id="8dbc2-125">Das folgende Beispiel zeigt, dass der bereichsmodifizierer `$Using` den Wert der `$a` Workflow Variablen der obersten Ebene für die Befehle im `InlineScript` Skriptblock verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-125">The following example shows that the `$Using` scope modifier makes the value of the `$a` top-level workflow variable available to the commands in the `InlineScript` script block.</span></span>

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

## <a name="returning-variables-in-inlinescript"></a><span data-ttu-id="8dbc2-126">Zurückgeben von Variablen in InlineScript</span><span class="sxs-lookup"><span data-stu-id="8dbc2-126">Returning variables in InlineScript</span></span>

<span data-ttu-id="8dbc2-127">`InlineScript` Befehle können den Wert der Variablen ändern, die aus dem Workflow Bereich importiert wurde, aber die Änderungen sind im Workflow Bereich nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-127">`InlineScript` commands can change the value of the variable that was imported from workflow scope, but the changes aren't visible in workflow scope.</span></span> <span data-ttu-id="8dbc2-128">Damit dies dort der Fall ist, geben Sie den geänderten Wert an den Workflowbereich zurück, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-128">To make them visible, return the changed value to the workflow scope, as shown in the following example.</span></span>

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
> <span data-ttu-id="8dbc2-129">Eine-Anweisung mit dem bereichsmodifizierer `$Using` sollte vor jeder Verwendung der Variablen im `InlineScript` Skriptblock angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-129">A statement with the `$Using` scope modifier should appear before any use of the variable in the `InlineScript` script block.</span></span>

## <a name="running-in-process"></a><span data-ttu-id="8dbc2-130">Prozess interne Ausführung</span><span class="sxs-lookup"><span data-stu-id="8dbc2-130">Running in-process</span></span>

<span data-ttu-id="8dbc2-131">Um die Zuverlässigkeit zu verbessern, werden die Befehle im `InlineScript` Skriptblock in einem eigenen Prozess ausgeführt, getrennt vom Prozess, in dem der Workflow ausgeführt wird, und dann die Ausgabe an den Workflow Prozess zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-131">To improve reliability, the commands in the `InlineScript` script block run in their own process, separate from the process in which the workflow runs, and then return their output to the workflow process.</span></span>

<span data-ttu-id="8dbc2-132">Um PowerShell anzuweisen, die `InlineScript` Aktivität im Workflow Prozess auszuführen, entfernen Sie den `InlineScript` Wert aus der **ouesfprocessactivity** -Eigenschaft der Sitzungs Konfiguration, z. b. mithilfe des- `New-PSWorkflowExecutionOption` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-132">To direct PowerShell to run the `InlineScript` activity in the workflow process, remove the `InlineScript` value from the **OutOfProcessActivity** property of the session configuration, such as by using the `New-PSWorkflowExecutionOption` cmdlet.</span></span>

### <a name="example"></a><span data-ttu-id="8dbc2-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8dbc2-133">Example</span></span>

<span data-ttu-id="8dbc2-134">Der `InlineScript` im folgenden Workflow enthält Befehle, die in PowerShell gültig sind, aber in Workflows nicht gültig sind.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-134">The `InlineScript` in the following workflow includes commands that are valid in PowerShell but aren't valid in workflows.</span></span> <span data-ttu-id="8dbc2-135">Beispielsweise das `New-Object` Cmdlet mit dem **ComObject** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="8dbc2-135">For example, the `New-Object` cmdlet with the **ComObject** parameter.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8dbc2-136">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8dbc2-136">See also</span></span>

[<span data-ttu-id="8dbc2-137">Informationen über_ActivityCommonParameters</span><span class="sxs-lookup"><span data-stu-id="8dbc2-137">about_ActivityCommonParameters</span></span>](about_ActivityCommonParameters.md)

[<span data-ttu-id="8dbc2-138">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="8dbc2-138">about_Remote_Variables</span></span>](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[<span data-ttu-id="8dbc2-139">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="8dbc2-139">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="8dbc2-140">[Psworkflow](xref:PSWorkflow) -Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8dbc2-140">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="8dbc2-141">Handbuch zu Workflows</span><span class="sxs-lookup"><span data-stu-id="8dbc2-141">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="8dbc2-142">Schreiben Sie einen Windows PowerShell-Workflow</span><span class="sxs-lookup"><span data-stu-id="8dbc2-142">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
