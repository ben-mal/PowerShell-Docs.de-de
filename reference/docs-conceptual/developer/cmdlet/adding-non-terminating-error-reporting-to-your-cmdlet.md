---
ms.date: 09/13/2016
ms.topic: reference
title: Hinzufügen von Berichten für Fehler ohne Abbruch zu Cmdlet
description: Hinzufügen von Berichten für Fehler ohne Abbruch zu Cmdlet
ms.openlocfilehash: 883ff2d522266495e409fb0d45f29713baa6f047
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648661"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a><span data-ttu-id="a052b-103">Hinzufügen von Berichten für Fehler ohne Abbruch zu Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a052b-103">Adding Non-Terminating Error Reporting to Your Cmdlet</span></span>

<span data-ttu-id="a052b-104">Cmdlets können nicht abschließende Fehler melden, indem Sie die [System. Management. Automation. Cmdlet. Write-error][] -Methode aufrufen und weiterhin auf dem aktuellen Eingabe Objekt oder in weiteren eingehenden Pipeline Objekten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a052b-104">Cmdlets can report nonterminating errors by calling the [System.Management.Automation.Cmdlet.WriteError][] method and still continue to operate on the current input object or on further incoming pipeline objects.</span></span> <span data-ttu-id="a052b-105">In diesem Abschnitt wird erläutert, wie ein Cmdlet erstellt wird, das nicht abschließende Fehler von seinen Eingabe Verarbeitungsmethoden meldet.</span><span class="sxs-lookup"><span data-stu-id="a052b-105">This section explains how to create a cmdlet that reports nonterminating errors from its input processing methods.</span></span>

<span data-ttu-id="a052b-106">Bei nicht beendenden Fehlern (sowie beim Beenden von Fehlern) muss das Cmdlet ein [System. Management. Automation. ErrorRecord][] -Objekt übergeben, das den Fehler identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a052b-106">For nonterminating errors (as well as terminating errors), the cmdlet must pass an [System.Management.Automation.ErrorRecord][] object identifying the error.</span></span> <span data-ttu-id="a052b-107">Jeder Fehler Daten Satz wird durch eine eindeutige Zeichenfolge identifiziert, die als "Fehler Bezeichner" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a052b-107">Each error record is identified by a unique string called the "error identifier".</span></span> <span data-ttu-id="a052b-108">Zusätzlich zum Bezeichner wird die Kategorie jedes Fehlers durch Konstanten angegeben, die durch eine [System. Management. Automation. ErrorCategory][] -Enumeration definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a052b-108">In addition to the identifier, the category of each error is specified by constants defined by a [System.Management.Automation.ErrorCategory][] enumeration.</span></span> <span data-ttu-id="a052b-109">Der Benutzer kann Fehler basierend auf der Kategorie anzeigen `$ErrorView` , indem er die Variable auf "categoryview" festlegt.</span><span class="sxs-lookup"><span data-stu-id="a052b-109">The user can view errors based on their category by setting the `$ErrorView` variable to "CategoryView".</span></span>

<span data-ttu-id="a052b-110">Weitere Informationen zu Fehler Datensätzen finden Sie unter [Windows PowerShell-Fehler Datensätze](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="a052b-110">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="a052b-111">Definieren des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a052b-111">Defining the Cmdlet</span></span>

<span data-ttu-id="a052b-112">Der erste Schritt bei der Cmdlet-Erstellung ist die Benennung des Cmdlets und das Deklarieren der .NET-Klasse, die das Cmdlet implementiert.</span><span class="sxs-lookup"><span data-stu-id="a052b-112">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="a052b-113">Dieses Cmdlet ruft Prozessinformationen ab, daher lautet der hier gewählte Verb Name "Get".</span><span class="sxs-lookup"><span data-stu-id="a052b-113">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="a052b-114">(Fast jede Art von Cmdlet, das Informationen abrufen kann, kann die Befehlszeilen Eingabe verarbeiten.) Weitere Informationen zu genehmigten Cmdlet-Verben finden Sie unter [Cmdlet-Verb Namen](approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="a052b-114">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="a052b-115">Im folgenden finden Sie die Definition für dieses `Get-Proc` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a052b-115">The following is the definition for this `Get-Proc` cmdlet.</span></span> <span data-ttu-id="a052b-116">Einzelheiten zu dieser Definition finden Sie unter [Erstellen des ersten Cmdlets](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="a052b-116">Details of this definition are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-parameters"></a><span data-ttu-id="a052b-117">Definieren von Parametern</span><span class="sxs-lookup"><span data-stu-id="a052b-117">Defining Parameters</span></span>

<span data-ttu-id="a052b-118">Bei Bedarf muss das Cmdlet Parameter für die Verarbeitung von Eingaben definieren.</span><span class="sxs-lookup"><span data-stu-id="a052b-118">If necessary, your cmdlet must define parameters for processing input.</span></span> <span data-ttu-id="a052b-119">Dieses Get-Proc Cmdlet definiert einen **namens** Parameter, wie unter [Hinzufügen von Parametern zum Verarbeiten von Command-Line Eingaben](adding-parameters-that-process-command-line-input.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a052b-119">This Get-Proc cmdlet defines a **Name** parameter as described in [Adding Parameters that Process Command-Line Input](adding-parameters-that-process-command-line-input.md).</span></span>

<span data-ttu-id="a052b-120">Hier ist die Parameter Deklaration für den **Name** -Parameter dieses Get-Proc Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a052b-120">Here is the parameter declaration for the **Name** parameter of this Get-Proc cmdlet.</span></span>

```csharp
[Parameter(
           Position = 0,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
[ValidateNotNullOrEmpty]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

```vb
<Parameter(Position:=0, ValueFromPipeline:=True, _
ValueFromPipelineByPropertyName:=True), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

## <a name="overriding-input-processing-methods"></a><span data-ttu-id="a052b-121">Überschreiben von Eingabe Verarbeitungsmethoden</span><span class="sxs-lookup"><span data-stu-id="a052b-121">Overriding Input Processing Methods</span></span>

<span data-ttu-id="a052b-122">Alle Cmdlets müssen mindestens eine der Eingabe Verarbeitungsmethoden überschreiben, die von der [System. Management. Automation. Cmdlet][] -Klasse bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a052b-122">All cmdlets must override at least one of the input processing methods provided by the [System.Management.Automation.Cmdlet][] class.</span></span> <span data-ttu-id="a052b-123">Diese Methoden werden unter [Erstellen des ersten Cmdlets](creating-a-cmdlet-without-parameters.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="a052b-123">These methods are discussed in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a052b-124">Ihr Cmdlet sollte jeden Datensatz so unabhängig wie möglich verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a052b-124">Your cmdlet should handle each record as independently as possible.</span></span>

<span data-ttu-id="a052b-125">Dieses Get-Proc Cmdlet überschreibt die [System. Management. Automation. Cmdlet. ProcessRecord][] -Methode, um den **namens** Parameter für die vom Benutzer oder einem Skript bereitgestellte Eingabe zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a052b-125">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord][] method to handle the **Name** parameter for input provided by the user or a script.</span></span> <span data-ttu-id="a052b-126">Diese Methode erhält die Prozesse für die einzelnen angeforderten Prozessnamen oder alle Prozesse, wenn kein Name angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a052b-126">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="a052b-127">Details dieser außer Kraft Setzung werden bei [der Erstellung des ersten Cmdlets](creating-a-cmdlet-without-parameters.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="a052b-127">Details of this override are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

### <a name="things-to-remember-when-reporting-errors"></a><span data-ttu-id="a052b-128">Dinge, die beim Melden von Fehlern beachtet werden sollten</span><span class="sxs-lookup"><span data-stu-id="a052b-128">Things to Remember When Reporting Errors</span></span>

<span data-ttu-id="a052b-129">Das [System. Management. Automation. ErrorRecord][] -Objekt, das das Cmdlet beim Schreiben eines Fehlers übergibt, erfordert im Kern eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="a052b-129">The [System.Management.Automation.ErrorRecord][] object that the cmdlet passes when writing an error requires an exception at its core.</span></span> <span data-ttu-id="a052b-130">Befolgen Sie die .NET-Richtlinien bei der Bestimmung der zu verwendenden Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="a052b-130">Follow the .NET guidelines when determining the exception to use.</span></span>
<span data-ttu-id="a052b-131">Wenn der Fehler in der Semantik identisch mit einer vorhandenen Ausnahme ist, sollte das Cmdlet diese Ausnahme verwenden oder davon ableiten.</span><span class="sxs-lookup"><span data-stu-id="a052b-131">Basically, if the error is semantically the same as an existing exception, the cmdlet should use or derive from that exception.</span></span> <span data-ttu-id="a052b-132">Andernfalls sollte eine neue Ausnahme-oder eine Ausnahme Hierarchie direkt von der [System. Exception][] -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a052b-132">Otherwise, it should derive a new exception or exception hierarchy directly from the [System.Exception][] class.</span></span>

<span data-ttu-id="a052b-133">Beachten Sie beim Erstellen von Fehler bezeichgern (auf die über die fullyqualifiederrorid-Eigenschaft der ErrorRecord-Klasse zugegriffen wird) Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a052b-133">When creating error identifiers (accessed through the FullyQualifiedErrorId property of the ErrorRecord class) keep the following in mind.</span></span>

- <span data-ttu-id="a052b-134">Verwenden Sie Zeichen folgen, die zu Diagnose Zwecken dienen, damit Sie bei der Überprüfung des voll qualifizierten Bezeichners ermitteln können, welcher Fehler vorliegt und wo der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a052b-134">Use strings that are targeted for diagnostic purposes so that when inspecting the fully qualified identifier you can determine what the error is and where the error came from.</span></span>

- <span data-ttu-id="a052b-135">Ein wohlgeformter voll qualifizierter Fehler Bezeichner kann wie folgt lauten.</span><span class="sxs-lookup"><span data-stu-id="a052b-135">A well formed fully qualified error identifier might be as follows.</span></span>

  `CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand`

<span data-ttu-id="a052b-136">Beachten Sie, dass im vorherigen Beispiel der Fehler Bezeichner (das erste Token) angibt, was der Fehler ist, und der verbleibende Teil gibt an, wo der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a052b-136">Notice that in the previous example, the error identifier (the first token) designates what the error is and the remaining part indicates where the error came from.</span></span>

- <span data-ttu-id="a052b-137">Bei komplexeren Szenarios kann der Fehler Bezeichner ein Punkt getrenntes Token sein, das bei der Überprüfung analysiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a052b-137">For more complex scenarios, the error identifier can be a dot separated token that can be parsed on inspection.</span></span> <span data-ttu-id="a052b-138">Dies ermöglicht es Ihnen, die Teile des Fehler Bezeichners sowie den Fehler Bezeichner und die Fehler Kategorie zu verzweigen.</span><span class="sxs-lookup"><span data-stu-id="a052b-138">This allows you too branch on the parts of the error identifier as well as the error identifier and error category.</span></span>

<span data-ttu-id="a052b-139">Mit dem-Cmdlet sollten bestimmte Fehler Bezeichner verschiedenen Codepfade zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a052b-139">The cmdlet should assign specific error identifiers to different code paths.</span></span> <span data-ttu-id="a052b-140">Beachten Sie bei der Zuweisung von Fehler bezeichmern die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="a052b-140">Keep the following information in mind for assignment of error identifiers:</span></span>

- <span data-ttu-id="a052b-141">Ein Fehler Bezeichner sollte während des gesamten Lebenszyklus des Cmdlets konstant bleiben.</span><span class="sxs-lookup"><span data-stu-id="a052b-141">An error identifier should remain constant throughout the cmdlet life cycle.</span></span> <span data-ttu-id="a052b-142">Ändern Sie nicht die Semantik eines Fehler Bezeichners zwischen den Cmdlet-Versionen.</span><span class="sxs-lookup"><span data-stu-id="a052b-142">Do not change the semantics of an error identifier between cmdlet versions.</span></span>
- <span data-ttu-id="a052b-143">Verwenden Sie Text für einen Fehler Bezeichner, der dem gemeldeten Fehler entspricht.</span><span class="sxs-lookup"><span data-stu-id="a052b-143">Use text for an error identifier that tersely corresponds to the error being reported.</span></span> <span data-ttu-id="a052b-144">Verwenden Sie keine Leerzeichen oder Interpunktions Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a052b-144">Do not use white space or punctuation.</span></span>
- <span data-ttu-id="a052b-145">Verwenden Sie das Cmdlet, um nur Fehler Bezeichner zu generieren, die reproduzierbar sind.</span><span class="sxs-lookup"><span data-stu-id="a052b-145">Have your cmdlet generate only error identifiers that are reproducible.</span></span> <span data-ttu-id="a052b-146">Beispielsweise sollte kein Bezeichner generiert werden, der einen Prozess Bezeichner enthält.</span><span class="sxs-lookup"><span data-stu-id="a052b-146">For example, it should not generate an identifier that includes a process identifier.</span></span> <span data-ttu-id="a052b-147">Fehler Bezeichner sind nur dann für einen Benutzer nützlich, wenn Sie bezeichmern entsprechen, die von anderen Benutzern erkannt werden, die das gleiche Problem aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a052b-147">Error identifiers are useful to a user only when they correspond to identifiers that are seen by other users experiencing the same problem.</span></span>

<span data-ttu-id="a052b-148">Nicht behandelte Ausnahmen werden von PowerShell unter den folgenden Bedingungen nicht abgefangen:</span><span class="sxs-lookup"><span data-stu-id="a052b-148">Unhandled exceptions are not caught by PowerShell in the following conditions:</span></span>

- <span data-ttu-id="a052b-149">Wenn ein Cmdlet einen neuen Thread erstellt und Code, der in diesem Thread ausgeführt wird, eine nicht behandelte Ausnahme auslöst, wird der Fehler von PowerShell nicht abgefangen, und der Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="a052b-149">If a cmdlet creates a new thread and code running in that thread throws an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>
- <span data-ttu-id="a052b-150">Wenn ein Objekt über Code im Debuggen verfügt oder Methoden verwerfen, die zu einer nicht behandelten Ausnahme geführt haben, wird der Fehler von PowerShell nicht abgefangen, und der Prozess wird beendet.</span><span class="sxs-lookup"><span data-stu-id="a052b-150">If an object has code in its destructor or Dispose methods that causes an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>

## <a name="reporting-nonterminating-errors"></a><span data-ttu-id="a052b-151">Melden von nicht abschließenden Fehlern</span><span class="sxs-lookup"><span data-stu-id="a052b-151">Reporting Nonterminating Errors</span></span>

<span data-ttu-id="a052b-152">Jede der Eingabe Verarbeitungsmethoden kann mithilfe der [System. Management. Automation. Cmdlet. Write-error][] -Methode einen Fehler ohne Abbruch an den Ausgabestream melden.</span><span class="sxs-lookup"><span data-stu-id="a052b-152">Any one of the input processing methods can report a nonterminating error to the output stream using the [System.Management.Automation.Cmdlet.WriteError][] method.</span></span>

<span data-ttu-id="a052b-153">Im folgenden finden Sie ein Codebeispiel aus diesem Get-Proc Cmdlet, das den [System. Management. Automation. Cmdlet. Write-error][] -Befehl in der Überschreibung der [System. Management. Automation. Cmdlet. ProcessRecord][] -Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a052b-153">Here is a code example from this Get-Proc cmdlet that illustrates the call to [System.Management.Automation.Cmdlet.WriteError][] from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord][] method.</span></span> <span data-ttu-id="a052b-154">In diesem Fall wird der-Befehl durchgeführt, wenn das Cmdlet keinen Prozess für einen angegebenen Prozess Bezeichner finden kann.</span><span class="sxs-lookup"><span data-stu-id="a052b-154">In this case, the call is made if the cmdlet cannot find a process for a specified process identifier.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no name parameter passed to cmdlet, get all processes.
  if (processNames == null)
  {
    WriteObject(Process.GetProcesses(), true);
  }
    else
    {
      // If a name parameter is passed to cmdlet, get and write
      // the associated processes.
      // Write a nonterminating error for failure to retrieve
      // a process.
      foreach (string name in processNames)
      {
        Process[] processes;

        try
        {
          processes = Process.GetProcessesByName(name);
        }
        catch (InvalidOperationException ex)
        {
          WriteError(new ErrorRecord(
                     ex,
                     "NameNotFound",
                     ErrorCategory.InvalidOperation,
                     name));
          continue;
        }

        WriteObject(processes, true);
      } // foreach (...
    } // else
  }
```

### <a name="things-to-remember-about-writing-nonterminating-errors"></a><span data-ttu-id="a052b-155">Dinge, die Sie beim Schreiben von Fehlern bei der nicht Beendigung</span><span class="sxs-lookup"><span data-stu-id="a052b-155">Things to Remember About Writing Nonterminating Errors</span></span>

<span data-ttu-id="a052b-156">Bei einem Fehler ohne Abbruch muss das Cmdlet einen bestimmten Fehler Bezeichner für jedes bestimmte Eingabe Objekt generieren.</span><span class="sxs-lookup"><span data-stu-id="a052b-156">For a nonterminating error, the cmdlet must generate a specific error identifier for each specific input object.</span></span>

<span data-ttu-id="a052b-157">Ein Cmdlet muss häufig die PowerShell-Aktion ändern, die von einem Fehler ohne Abbruch erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="a052b-157">A cmdlet frequently needs to modify the PowerShell action produced by a nonterminating error.</span></span> <span data-ttu-id="a052b-158">Hierzu können Sie den `ErrorAction` -Parameter und den `ErrorVariable` -Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="a052b-158">It can do this by defining the `ErrorAction` and `ErrorVariable` parameters.</span></span> <span data-ttu-id="a052b-159">Wenn Sie den `ErrorAction` Parameter definieren, zeigt das Cmdlet die Benutzeroptionen [System. Management. Automation. Action Preference][]an. Sie können die Aktion auch direkt beeinflussen, indem Sie die `$ErrorActionPreference` Variable festlegen.</span><span class="sxs-lookup"><span data-stu-id="a052b-159">If defining the `ErrorAction` parameter, the cmdlet presents the user options [System.Management.Automation.ActionPreference][], you can also directly influence the action by setting the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="a052b-160">Mithilfe des- `ErrorVariable` Parameters, der nicht von der-Einstellung von betroffen ist, kann das Cmdlet nicht abschließende Fehler in einer Variablen speichern `ErrorAction` .</span><span class="sxs-lookup"><span data-stu-id="a052b-160">The cmdlet can save nonterminating errors to a variable using the `ErrorVariable` parameter, which is not affected by the setting of `ErrorAction`.</span></span> <span data-ttu-id="a052b-161">Fehler können an eine vorhandene Fehler Variable angehängt werden, indem ein Pluszeichen (+) am Anfang des Variablen namens hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a052b-161">Failures can be appended to an existing error variable by adding a plus sign (+) to the front of the variable name.</span></span>

## <a name="code-sample"></a><span data-ttu-id="a052b-162">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="a052b-162">Code Sample</span></span>

<span data-ttu-id="a052b-163">Den gesamten c#-Beispielcode finden Sie unter [GetProcessSample04 Sample](./getprocesssample04-sample.md).</span><span class="sxs-lookup"><span data-stu-id="a052b-163">For the complete C# sample code, see [GetProcessSample04 Sample](./getprocesssample04-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="a052b-164">Definieren von Objekttypen und Formatierung</span><span class="sxs-lookup"><span data-stu-id="a052b-164">Define Object Types and Formatting</span></span>

<span data-ttu-id="a052b-165">PowerShell übergibt Informationen zwischen Cmdlets mithilfe von .NET-Objekten.</span><span class="sxs-lookup"><span data-stu-id="a052b-165">PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="a052b-166">Folglich muss ein Cmdlet möglicherweise seinen eigenen Typ definieren, oder das Cmdlet muss möglicherweise einen vorhandenen Typ erweitern, der von einem anderen Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a052b-166">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="a052b-167">Weitere Informationen zum Definieren neuer Typen oder zum Erweitern vorhandener Typen finden Sie unter [Erweitern von Objekttypen und Formatierung](/previous-versions/ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="a052b-167">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="a052b-168">Cmdlet wird aufgebaut</span><span class="sxs-lookup"><span data-stu-id="a052b-168">Building the Cmdlet</span></span>

<span data-ttu-id="a052b-169">Nachdem Sie ein Cmdlet implementiert haben, müssen Sie es über ein Windows PowerShell-Snap-in bei Windows PowerShell registrieren.</span><span class="sxs-lookup"><span data-stu-id="a052b-169">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="a052b-170">Weitere Informationen zum Registrieren von Cmdlets finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="a052b-170">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="a052b-171">Testen des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a052b-171">Testing the Cmdlet</span></span>

<span data-ttu-id="a052b-172">Wenn das Cmdlet in PowerShell registriert wurde, können Sie es in der Befehlszeile testen.</span><span class="sxs-lookup"><span data-stu-id="a052b-172">When your cmdlet has been registered with PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="a052b-173">Testen Sie das Beispiel Get-Proc Cmdlet, um zu sehen, ob es einen Fehler meldet:</span><span class="sxs-lookup"><span data-stu-id="a052b-173">Let's test the sample Get-Proc cmdlet to see whether it reports an error:</span></span>

- <span data-ttu-id="a052b-174">Starten Sie PowerShell, und verwenden Sie das Cmdlet "Get-Proc" zum Abrufen der Prozesse mit dem Namen "Test".</span><span class="sxs-lookup"><span data-stu-id="a052b-174">Start PowerShell, and use the Get-Proc cmdlet to retrieve the processes named "TEST".</span></span>

  ```powershell
  get-proc -name test
  ```

  <span data-ttu-id="a052b-175">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a052b-175">The following output appears.</span></span>

  ```
  get-proc : Operation is not valid due to the current state of the object.
  At line:1 char:9
  + get-proc  <<<< -name test
  ```

## <a name="see-also"></a><span data-ttu-id="a052b-176">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a052b-176">See Also</span></span>

[<span data-ttu-id="a052b-177">Hinzufügen von Parametern, die Pipelineeingaben verarbeiten</span><span class="sxs-lookup"><span data-stu-id="a052b-177">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="a052b-178">Hinzufügen von Parametern, die Command-Line Eingabe verarbeiten</span><span class="sxs-lookup"><span data-stu-id="a052b-178">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="a052b-179">Erstellen Ihres ersten Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a052b-179">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="a052b-180">[Erweitern von Objekttypen und Formatierung](/previous-versions/ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="a052b-180">[Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85))</span></span>

<span data-ttu-id="a052b-181">[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="a052b-181">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="a052b-182">Windows PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="a052b-182">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="a052b-183">Cmdlet-Beispiele</span><span class="sxs-lookup"><span data-stu-id="a052b-183">Cmdlet Samples</span></span>](./cmdlet-samples.md)

[System.Exception]: /dotnet/api/System.Exception
[System. Management. Automation. Action Preference]: /dotnet/api/System.Management.Automation.ActionPreference
[System.Management.Automation.ActionPreference]: /dotnet/api/System.Management.Automation.ActionPreference
[System. Management. Automation. Cmdlet. ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System.Management.Automation.Cmdlet.ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System. Management. Automation. Cmdlet. Write error]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System.Management.Automation.Cmdlet.WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System. Management. Automation. Cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[System.Management.Automation.Cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[System. Management. Automation. ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System.Management.Automation.ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System. Management. Automation. ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord
[System.Management.Automation.ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord
