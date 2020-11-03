---
description: Beschreibt, wie Funktionen, die das-Attribut angeben, `CmdletBinding` die für kompilierte Cmdlets verfügbaren Methoden und Eigenschaften verwenden können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_methods?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Methods
ms.openlocfilehash: 862c57d326049096ada28353b74485f8519f46da
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224055"
---
# <a name="about-functions-advanced-methods"></a>Informationen zu erweiterten Funktionen von Functions

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt, wie Funktionen, die das-Attribut angeben, `CmdletBinding` die für kompilierte Cmdlets verfügbaren Methoden und Eigenschaften verwenden können.

## <a name="long-description"></a>Lange Beschreibung

Funktionen, die das-Attribut angeben, `CmdletBinding` können über die Variable auf eine Reihe von Methoden und Eigenschaften zugreifen `$PSCmdlet` . Diese Methoden umfassen die folgenden Methoden:

- Eingabe Verarbeitungsmethoden, die von den kompilierten Cmdlets verwendet werden, um Ihre Arbeit zu erledigen.
- Die `ShouldProcess` -und- `ShouldContinue` Methoden, die verwendet werden, um Benutzer Feedback zu erhalten, bevor eine Aktion ausgeführt wird.
- Die `ThrowTerminatingError` Methode zum Erstellen von Fehler Datensätzen.
- Mehrere `Write` Methoden, die unterschiedliche Arten der Ausgabe zurückgeben.

Alle Methoden und Eigenschaften der **PSCmdlet** -Klasse sind für erweiterte Funktionen verfügbar. Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).

Weitere Informationen zum- `CmdletBinding` Attribut finden Sie unter [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).
Informationen zur **cmdletbindingattribute** -Klasse finden Sie unter [System. Management. Automation. Cmdlet. cmdletbindingattribute](/dotnet/api/system.management.automation.cmdletbindingattribute).

### <a name="input-processing-methods"></a>Eingabe Verarbeitungsmethoden

Die in diesem Abschnitt beschriebenen Methoden werden als Eingabe Verarbeitungsmethoden bezeichnet. Für-Funktionen werden diese drei Methoden durch die `Begin` -, `Process` -und- `End` Blöcke der-Funktion dargestellt. Sie müssen diese Blöcke nicht in ihren Funktionen verwenden.

> [!NOTE]
> Diese Blöcke sind auch für Funktionen verfügbar, die das- `CmdletBinding` Attribut nicht verwenden.

#### <a name="begin"></a>Starten

Dieser Block wird verwendet, um eine optionale einmalige Vorverarbeitung für die Funktion bereitzustellen.
Die PowerShell-Laufzeit verwendet den Code in diesem Block einmal für jede Instanz der Funktion in der Pipeline.

#### <a name="process"></a>Prozess

Dieser Block wird verwendet, um die Verarbeitung von Datensätzen im Datensatz für die Funktion bereitzustellen. Sie können einen- `Process` Block verwenden, ohne die anderen Blöcke zu definieren. Die Anzahl von `Process` Block Ausführungen hängt davon ab, wie Sie die Funktion verwenden und welche Eingaben die Funktion empfängt.

Die automatische Variable `$_` oder `$PSItem` enthält das aktuelle Objekt in der Pipeline für die Verwendung im- `Process` Block. Die `$input` Automatische Variable enthält einen Enumerator, der nur für Funktionen und Skriptblöcke verfügbar ist.
Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).

- Wenn Sie die Funktion am Anfang oder außerhalb einer Pipeline aufrufen, wird der `Process` Block einmal ausgeführt.
- Innerhalb einer Pipeline wird der- `Process` Block einmal für jedes Eingabe Objekt ausgeführt, das die-Funktion erreicht.
- Wenn die Pipeline Eingabe, die die Funktion erreicht, leer ist, wird der- `Process` Block **nicht** ausgeführt.
  - Die `Begin` -und- `End` Blöcke werden weiterhin ausgeführt.

> [!IMPORTANT]
> Wenn ein Funktionsparameter so festgelegt ist, dass er Pipeline Eingaben annimmt, und ein- `Process` Block nicht definiert ist, schlägt die Daten Satz Weise Verarbeitung fehl. In diesem Fall wird die Funktion nur einmal ausgeführt, unabhängig von der Eingabe.

#### <a name="end"></a>Ende

Dieser Block wird verwendet, um eine optionale einmalige Nachbearbeitung für die Funktion bereitzustellen.

Das folgende Beispiel zeigt die Gliederung einer Funktion, die einen `Begin` -Block für die einmalige Vorverarbeitung, einen `Process` -Block für die Verarbeitung mehrerer Datensätze und einen-Block für die `End` einmalige Nachbearbeitung enthält.

```powershell
Function Test-ScriptCmdlet
{
[CmdletBinding(SupportsShouldProcess=$True)]
    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

> [!NOTE]
> Die Verwendung eines- `Begin` oder- `End` Blocks erfordert, dass Sie alle drei Blöcke definieren. Wenn alle drei Blöcke verwendet werden, muss sich der gesamte PowerShell-Code in einem der-Blöcke befinden.

### <a name="confirmation-methods"></a>Bestätigungs Methoden

#### <a name="shouldprocess"></a>ShouldProcess

Diese Methode wird aufgerufen, um eine Bestätigung vom Benutzer anzufordern, bevor die Funktion eine Aktion ausführt, durch die das System geändert wird. Die Funktion kann basierend auf dem booleschen Wert fortgesetzt werden, der von der-Methode zurückgegeben wird. Diese Methode kann nur innerhalb des- `Process{}` Blocks der-Funktion aufgerufen werden. Das- `CmdletBinding` Attribut muss auch deklarieren, dass die-Funktion unterstützt `ShouldProcess` (wie im vorherigen Beispiel gezeigt).

Weitere Informationen zu dieser Methode finden Sie unter " [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/system.management.automation.cmdlet.shouldprocess)".

Weitere Informationen zum Anfordern der Bestätigung finden Sie unter [Anfordern einer Bestätigung](/powershell/scripting/developer/cmdlet/requesting-confirmation).

#### <a name="shouldcontinue"></a>ShouldContinue

Diese Methode wird aufgerufen, um eine zweite Bestätigungsmeldung anzufordern. Sie sollte aufgerufen werden, wenn die- `ShouldProcess` Methode zurückgibt `$true` . Weitere Informationen zu dieser Methode finden Sie unter " [System. Management. Automation. Cmdlet. daudcontinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue)".

### <a name="error-methods"></a>Fehler Methoden

Funktionen können zwei verschiedene Methoden aufzurufen, wenn Fehler auftreten. Wenn ein Fehler ohne Abbruch auftritt, sollte die Funktion die-Methode aufzurufen `WriteError` , die im `Write` Abschnitt Methoden beschrieben wird. Wenn ein Abbruch Fehler auftritt und die Funktion nicht fortgesetzt werden kann, sollte die-Methode aufgerufen werden `ThrowTerminatingError` . Sie können auch die `Throw` -Anweisung verwenden, um Fehler zu beenden, und das [Write-error-](xref:Microsoft.PowerShell.Utility.Write-Error) Cmdlet für Fehler ohne Abbruch.

Weitere Informationen finden Sie unter [System. Management. Automation. Cmdlet. ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror).

### <a name="write-methods"></a>Write-Methoden

Eine Funktion kann die folgenden Methoden aufzurufen, um unterschiedliche Ausgabetypen zurückzugeben.
Beachten Sie, dass nicht die gesamte Ausgabe an den nächsten Befehl in der Pipeline weitergeleitet wird. Sie können auch die verschiedenen `Write` Cmdlets verwenden, z `Write-Error` . b..

#### <a name="writecommanddetail"></a>"Write-commanddetail"

Weitere Informationen zur- `WriteCommandDetails` Methode finden Sie unter [System. Management. Automation. Cmdlet. Beschreib tecommanddetail](/dotnet/api/system.management.automation.cmdlet.writecommanddetail).

#### <a name="writedebug"></a>Beschreib Debuggen

Zum Bereitstellen von Informationen, die für die Problembehandlung einer Funktion verwendet werden können, muss die Funktion die- `WriteDebug` Methode aufruft. Die- `WriteDebug` Methode zeigt Debugmeldungen für den Benutzer an. Weitere Informationen finden Sie unter [System. Management. Automation. Cmdlet. Write-Debug](/dotnet/api/system.management.automation.cmdlet.writedebug).

#### <a name="writeerror"></a>WriteError

Functions sollte diese Methode aufgerufen werden, wenn Fehler ohne Abbruch auftreten und die Funktion zum Fortsetzen der Verarbeitung von Datensätzen entworfen wurde. Weitere Informationen finden Sie unter [System. Management. Automation. Cmdlet. Write-error](/dotnet/api/system.management.automation.cmdlet.writeerror).

> [!NOTE]
> Wenn ein Abbruch Fehler auftritt, sollte die Funktion die [ThrowTerminatingError](/dotnet/api/system.management.automation.cmdlet.throwterminatingerror) -Methode aufzurufen.

#### <a name="writeobject"></a>WriteObject

Die- `WriteObject` Methode ermöglicht es der-Funktion, ein Objekt an den nächsten Befehl in der Pipeline zu senden. In den meisten Fällen `WriteObject` ist die Methode, die verwendet werden soll, wenn die Funktion Daten zurückgibt. Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write Object](/dotnet/api/system.management.automation.cmdlet.writeobject).

#### <a name="writeprogress"></a>"Write Progress"

Für Funktionen mit Aktionen, deren Ausführung viel Zeit in Anspruch nimmt, ermöglicht diese Methode der-Funktion, die-Methode aufzurufen, `WriteProgress` damit Fortschrittsinformationen angezeigt werden. Beispielsweise können Sie den abgeschlossenen Prozentsatz anzeigen.
Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write Progress](/dotnet/api/system.management.automation.cmdlet.writeprogress).

#### <a name="writeverbose"></a>WriteVerbose

Um ausführliche Informationen zur Funktionsweise der Funktion bereitzustellen, müssen Sie die-Funktion aufrufen, `WriteVerbose` um dem Benutzer ausführliche Meldungen anzuzeigen. Standardmäßig werden ausführliche Meldungen nicht angezeigt. Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write-Verbose](/dotnet/api/system.management.automation.cmdlet.writeverbose).

#### <a name="writewarning"></a>WriteWarning

Um Informationen zu Bedingungen bereitzustellen, die möglicherweise zu unerwarteten Ergebnissen führen, rufen Sie die-Funktion auf, um dem Benutzer Warnmeldungen anzuzeigen. Standardmäßig werden Warnmeldungen angezeigt. Weitere Informationen finden Sie unter [System. Management. Automation. PSCmdlet. Write Warning](/dotnet/api/system.management.automation.cmdlet.writewarning).

> [!NOTE]
> Sie können auch Warnmeldungen anzeigen, indem Sie die `$WarningPreference` -Variable oder die `Verbose` `Debug` Befehlszeilenoptionen und verwenden. Weitere Informationen zur- `$WarningPreference` Variablen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).

### <a name="other-methods-and-properties"></a>Andere Methoden und Eigenschaften

Informationen zu den anderen Methoden und Eigenschaften, auf die über die Variable zugegriffen werden kann `$PSCmdlet` , finden Sie unter [System. Management. Automation. PSCmdlet](/dotnet/api/system.management.automation.pscmdlet).

Beispielsweise können Sie mit der [parametersetname](/dotnet/api/system.management.automation.pscmdlet.parametersetname) -Eigenschaft den verwendeten Parametersatz anzeigen. Mithilfe von Parametersätzen können Sie eine Funktion erstellen, die basierend auf den Parametern, die beim Ausführen der Funktion angegeben werden, verschiedene Aufgaben ausführt.

## <a name="see-also"></a>Weitere Informationen:

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)

[about_Preference_Variables](about_Preference_Variables.md)

