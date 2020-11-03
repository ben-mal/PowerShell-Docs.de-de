---
description: Bietet eine kurze Einführung in das PowerShell-Workflow-Feature.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen über_Workflows
ms.openlocfilehash: fbd8ee62b1e9c6969d489c5024c33f5cca883dc6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221847"
---
# <a name="about-workflows"></a>Informationen zu Workflows

## <a name="short-description"></a>Kurze Beschreibung

Bietet eine kurze Einführung in das PowerShell-Workflow-Feature.

## <a name="long-description"></a>Lange Beschreibung

Der PowerShell-Workflow bietet die Vorteile der [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) in PowerShell und ermöglicht das Schreiben und Ausführen von Workflows.

PowerShell-Workflow wurde in PowerShell 3,0 eingeführt, und das Modul ist bis PowerShell 5,1 verfügbar. Weitere Informationen zum PowerShell-Workflow finden Sie im Workflow [Handbuch](/previous-versions/powershell/scripting/components/workflows-guide) und unter [Schreiben eines Windows PowerShell-Workflows](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).

## <a name="about-workflows"></a>Informationen zu Workflows

Workflows sind Befehle, die aus einer geordneten Sequenz verwandter Aktivitäten bestehen. In der Regel werden Sie über einen längeren Zeitraum ausgeführt, sodass Sie Daten von Hunderten von Computern erfassen und ändern können (häufig in heterogenen Umgebungen).

Workflows können in XAML, der in Windows Workflow Foundation verwendeten Sprache oder in der PowerShell-Sprache geschrieben werden. Workflows werden in der Regel in Module verpackt und enthalten Hilfe Themen. Weitere Informationen finden Sie unter [Übersicht über XAML (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).

Workflows sind in einer IT-Umgebung von entscheidender Bedeutung, da Sie Neustarts überstehen und automatisch nach häufigen Fehlern wieder hergestellt werden können. Sie können Verbindungen mit Sitzungen und Computern, auf denen Workflows ausgeführt werden, trennen und wiederherstellen, ohne die Workflow Verarbeitung zu unterbrechen und Workflows ohne Datenverlust transparent anzuhalten und fortzusetzen. Jede Aktivität in einem Workflow kann protokolliert und auf Verweise überprüft werden.
Workflows können als Aufträge ausgeführt werden und können mit dem Feature "geplante Aufträge" von PowerShell geplant werden.

Der Zustand und die Daten in einem Workflow werden am Anfang und am Ende des Workflows sowie an den von Ihnen angegebenen Punkten gespeichert. Workflow-Persistenzpunkte funktionieren wie Daten Bank Momentaufnahmen oder Programm Prüfpunkte, um den Workflow vor den Auswirkungen von Unterbrechungen und Fehlern zu schützen. Wenn der Workflow nach einem Fehler nicht wieder hergestellt werden kann, können Sie die beibehaltenen Daten verwenden und vom letzten Persistenzpunkt fortsetzen, anstatt einen umfangreichen Workflow von Anfang an erneut auszuführen.

## <a name="workflow-requirements-and-configuration"></a>Workflow Anforderungen und-Konfiguration

Eine PowerShell-Workflow Konfiguration besteht aus den folgenden Elementen:

- Ein Client Computer, auf dem der Workflow ausgeführt wird.
- Eine Workflow Sitzung, **PSSession** , auf dem Client Computer oder auf einem Remote Computer.
- Verwaltete Knoten, die Zielcomputer, die von den Workflow Aktivitäten betroffen sind.

Die Workflow Sitzung ist nicht erforderlich, wird jedoch empfohlen. **Pssessions** können die robusten Features für Wiederherstellung und getrennte Sitzungen von PowerShell nutzen, um getrennte Workflow Sitzungen wiederherzustellen. Weitere Informationen finden Sie unter [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)

Da der Client Computer und der Computer, auf dem die Workflow Sitzung ausgeführt wird, verwaltete Knoten sein können, können Sie einen Workflow auf einem einzelnen Computer ausführen, der alle Rollen erfüllt.

Auf dem Client Computer und dem Computer, auf dem die Workflow Sitzung ausgeführt wird, muss PowerShell 3,0 ausgeführt werden. Alle berechtigten Systeme werden unterstützt, einschließlich der Server Core-Installationsoptionen von Windows Server-Betriebssystemen.

Zum Ausführen von Workflows, die Cmdlets enthalten, müssen die verwalteten Knoten Windows PowerShell 2,0 oder höher aufweisen. Für verwaltete Knoten ist PowerShell nur erforderlich, wenn der Workflow Cmdlets enthält. Sie können Workflows ausführen, die Windows-Verwaltungsinstrumentation-Befehle (WMI) und Common Information Model (CIM) auf Computern enthalten, die nicht über PowerShell verfügen.

## <a name="how-to-get-workflows"></a>Vorgehensweise beim erhalten von Workflows

Workflows werden in der Regel in Module verpackt. Um das Modul zu importieren, das einen Workflow enthält, verwenden Sie einen beliebigen Befehl im Modul, oder verwenden Sie das `Import-Module` Cmdlet.
Module werden automatisch bei der ersten Verwendung eines beliebigen Befehls im Modul importiert.

Verwenden Sie den `Get-Command` **CommandType** -Parameter des Cmdlets, um die Workflows in Modulen zu ermitteln, die auf Ihrem Computer installiert sind.

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a>Ausführen von Workflows

Verwenden Sie das folgende Verfahren, um einen Workflow auszuführen.

1. Wenn der verwaltete Knoten der lokale Computer ist, ist dieser Schritt nicht erforderlich.
   Starten Sie andernfalls auf dem Client Computer PowerShell mit der Option **als Administrator ausführen** .

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. Aktivieren Sie PowerShell-Remoting auf dem Computer, auf dem die Workflow Sitzung ausgeführt wird, sowie auf verwalteten Knoten, die von Workflows mit Cmdlets betroffen sind.

   Sie müssen diesen Schritt nur einmal auf jedem beteiligten Computer ausführen.

   Dieser Schritt ist nur erforderlich, wenn Sie Workflows ausführen, die Cmdlets enthalten. Sie müssen Remoting nicht auf dem Client Computer aktivieren, es sei denn, die Workflows-Sitzung wird auf dem Client Computer oder auf verwalteten Knoten ausgeführt, auf denen PowerShell 3,0 ausgeführt wird.

   Verwenden Sie das-Cmdlet, um Remoting zu aktivieren `Enable-PSRemoting` .

   ```powershell
   Enable-PSRemoting -Force
   ```

   Sie können das Remoting mithilfe der Einstellung **Skriptausführung** Gruppenrichtlinie aktivieren aktivieren. Weitere Informationen finden Sie unter [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) und [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).

1. Verwenden `New-PSWorkflowSession` Sie die `New-PSSession` Cmdlets oder, um die Workflow Sitzung zu erstellen.

   Mit dem- `New-PSWorkflowSession` Cmdlet wird eine Sitzung gestartet, die die integrierte **Microsoft. PowerShell. Workflow** -Sitzungs Konfiguration auf dem Zielcomputer verwendet. Diese Sitzungs Konfiguration umfasst Skripts, Typ-und Formatierungs Dateien sowie Optionen, die für Workflows entworfen wurden.

   Sie können auch das- `New-PSSession` Cmdlet verwenden. Verwenden Sie den **ConfigurationName** -Parameter, um die **Microsoft. PowerShell. Workflow** -Sitzungs Konfiguration anzugeben. Dieser Befehl entspricht der Verwendung des- `New-PSWorkflowSession` Cmdlets.

   Eine Alternative ist die Verwendung des- `New-PSSession` Cmdlets. Verwenden Sie den **ConfigurationName** -Parameter, um die **Microsoft. PowerShell. Workflow** -Sitzungs Konfiguration anzugeben.

   Auf dem lokalen Computer:

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   Auf einem Remote Computer:

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   Wenn Sie Administrator auf dem Workflow Sitzungs Computer sind, können Sie mit dem `New-PSWorkflowExecutionOption` Cmdlet benutzerdefinierte Options Einstellungen für die Workflow Sitzungs Konfiguration erstellen. Verwenden `Set-PSSessionConfiguration` Sie das Cmdlet, um die Sitzungs Konfiguration zu ändern.

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. Führen Sie den Workflow in der Workflow Sitzung aus. Um die Namen der verwalteten Knoten, Zielcomputer anzugeben, verwenden Sie den allgemeinen **pscomputername** -Workflow Parameter.

   In den folgenden Beispielen wird der Workflow mit dem Namen **Test-Workflow** ausgeführt.

   Dabei ist der verwaltete Knoten der Computer, der die Workflow Sitzung hostet:

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   Dabei handelt es sich bei den verwalteten Knoten um Remote Computer.

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   Im folgenden Beispiel wird der **Test-Workflow** auf Hunderten von Computern ausgeführt. Mit dem `Get-Content` -Cmdlet werden die Computernamen aus einer Textdatei abgerufen und in der `$Servers` Variablen auf dem lokalen Computer gespeichert.

   `Invoke-Command` verwendet den `$Using` Scope-Modifizierer, um die `$Servers` Variable in der lokalen Sitzung zu definieren. Weitere Informationen zum bereichsmodifizierer finden Sie unter `$Using` [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a>Verwenden von allgemeinen Workflow Parametern

Die allgemeinen Workflow Parameter sind eine Reihe von Parametern, die von PowerShell automatisch allen Workflows hinzugefügt werden. PowerShell fügt allen Workflows die allgemeinen Cmdlet-Parameter hinzu, auch wenn der Workflow das **cmdletbinding** -Attribut nicht verwendet.

Der folgende Workflow definiert z. b. keine Parameter. Wenn Sie den Workflow ausführen, verfügt er jedoch sowohl über **CommonParameters** als auch über **workflowcommonparameters**.

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

Die allgemeinen Workflow Parameter enthalten mehrere Parameter, die für die Ausführung von Workflows von entscheidender Bedeutung sind. Beispielsweise gibt der allgemeine **pscomputername** -Parameter die verwalteten Knoten an, auf die sich der Workflow auswirkt.

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

Mit dem allgemeinen **pspersist** -Workflow Parameter wird bestimmt, wann Workflow Daten persistent gespeichert werden. Sie ermöglicht es Ihnen, Persistenzpunkte zwischen Aktivitäten zu Workflows hinzuzufügen, die keine Persistenzpunkte definieren.

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

Mit anderen allgemeinen Workflow Parametern können Sie die Merkmale der Remote Verbindung zu den verwalteten Knoten angeben. Ihre Namen und Funktionen ähneln den Parametern von Remoting-Cmdlets, einschließlich `Invoke-Command` .

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

Achten Sie darauf, die remotingparameter, die die Verbindung für die Workflow Sitzung definieren, von den allgemeinen Workflow Parametern des **PS-prefixed** zu unterscheiden, die die Verbindung zu den verwalteten Knoten definieren.

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

Einige allgemeine Workflow Parameter sind für Workflows eindeutig, wie z. b. den **psparametercollection** -Parameter, mit dem Sie verschiedene allgemeine Workflow Parameterwerte für verschiedene Remote Knoten angeben können. Eine Liste und eine Beschreibung der allgemeinen Workflow Parameter finden Sie unter [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).

## <a name="see-also"></a>Weitere Informationen:

[Invoke-AsWorkflow](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Psworkflow](xref:PSWorkflow) -Cmdlets

[Handbuch zu Workflows](/previous-versions/powershell/scripting/components/workflows-guide)

[Schreiben Sie einen Windows PowerShell-Workflow](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
