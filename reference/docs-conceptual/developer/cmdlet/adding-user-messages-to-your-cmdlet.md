---
ms.date: 09/13/2016
ms.topic: reference
title: Hinzufügen von Benutzermeldungen zum Cmdlet
description: Hinzufügen von Benutzermeldungen zum Cmdlet
ms.openlocfilehash: de6fcc093af1d01287eed1eb8cc7b81cf5d2fdd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668336"
---
# <a name="adding-user-messages-to-your-cmdlet"></a><span data-ttu-id="803ef-103">Hinzufügen von Benutzermeldungen zum Cmdlet</span><span class="sxs-lookup"><span data-stu-id="803ef-103">Adding User Messages to Your Cmdlet</span></span>

<span data-ttu-id="803ef-104">Cmdlets können verschiedene Arten von Nachrichten schreiben, die dem Benutzer von der Windows PowerShell-Laufzeit angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="803ef-104">Cmdlets can write several kinds of messages that can be displayed to the user by the Windows PowerShell runtime.</span></span> <span data-ttu-id="803ef-105">Diese Meldungen enthalten die folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="803ef-105">These messages include the following types:</span></span>

- <span data-ttu-id="803ef-106">Ausführliche Meldungen, die allgemeine Benutzerinformationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="803ef-106">Verbose messages that contain general user information.</span></span>

- <span data-ttu-id="803ef-107">Debugmeldungen, die Informationen zur Problembehandlung enthalten.</span><span class="sxs-lookup"><span data-stu-id="803ef-107">Debug messages that contain troubleshooting information.</span></span>

- <span data-ttu-id="803ef-108">Warnmeldungen, die eine Benachrichtigung enthalten, dass das Cmdlet einen Vorgang ausführt, der unerwartete Ergebnisse aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="803ef-108">Warning messages that contain a notification that the cmdlet is about to perform an operation that can have unexpected results.</span></span>

- <span data-ttu-id="803ef-109">Fortschrittsberichts Meldungen mit Informationen darüber, wie viel Arbeit das Cmdlet beim Ausführen eines Vorgangs abgeschlossen hat, der lange dauert.</span><span class="sxs-lookup"><span data-stu-id="803ef-109">Progress report messages that contain information about how much work the cmdlet has completed when performing an operation that takes a long time.</span></span>

<span data-ttu-id="803ef-110">Es gibt keine Beschränkung für die Anzahl der Nachrichten, die das Cmdlet schreiben kann, oder den Typ der Nachrichten, die vom Cmdlet geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="803ef-110">There are no limits to the number of messages that your cmdlet can write or the type of messages that your cmdlet writes.</span></span> <span data-ttu-id="803ef-111">Jede Nachricht wird durch einen bestimmten-Rückruf aus der Eingabe Verarbeitungsmethode des Cmdlets geschrieben.</span><span class="sxs-lookup"><span data-stu-id="803ef-111">Each message is written by making a specific call from within the input processing method of your cmdlet.</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="803ef-112">Definieren des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="803ef-112">Defining the Cmdlet</span></span>

<span data-ttu-id="803ef-113">Der erste Schritt bei der Cmdlet-Erstellung ist die Benennung des Cmdlets und das Deklarieren der .NET-Klasse, die das Cmdlet implementiert.</span><span class="sxs-lookup"><span data-stu-id="803ef-113">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="803ef-114">Jede Art von Cmdlet kann Benutzer Benachrichtigungen von den Eingabe Verarbeitungsmethoden schreiben. im Allgemeinen können Sie dieses Cmdlet mit einem beliebigen Verb benennen, das angibt, welche Systemänderungen das Cmdlet ausführt.</span><span class="sxs-lookup"><span data-stu-id="803ef-114">Any sort of cmdlet can write user notifications from its input processing methods; so, in general, you can name this cmdlet using any verb that indicates what system modifications the cmdlet performs.</span></span> <span data-ttu-id="803ef-115">Weitere Informationen zu genehmigten Cmdlet-Verben finden Sie unter [Cmdlet-Verb Namen](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="803ef-115">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="803ef-116">Das Cmdlet "Stop-Proc" wurde entwickelt, um das System zu ändern. Daher muss die [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) -Deklaration für die .NET-Klasse das `SupportsShouldProcess` Attribute-Schlüsselwort einschließen und auf festgelegt werden `true` .</span><span class="sxs-lookup"><span data-stu-id="803ef-116">The Stop-Proc cmdlet is designed to modify the system; therefore, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration for the .NET class must include the `SupportsShouldProcess` attribute keyword and be set to `true`.</span></span>

<span data-ttu-id="803ef-117">Der folgende Code ist die Definition für diese Stop-Proc Cmdlet-Klasse.</span><span class="sxs-lookup"><span data-stu-id="803ef-117">The following code is the definition for this Stop-Proc cmdlet class.</span></span> <span data-ttu-id="803ef-118">Weitere Informationen zu dieser Definition finden Sie unter [Erstellen eines Cmdlets, das das System ändert](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="803ef-118">For more information about this definition, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="803ef-119">Definieren von Parametern für die System Änderung</span><span class="sxs-lookup"><span data-stu-id="803ef-119">Defining Parameters for System Modification</span></span>

<span data-ttu-id="803ef-120">Das-Cmdlet "Stop-Proc" definiert drei Parameter: `Name` , `Force` und `PassThru` .</span><span class="sxs-lookup"><span data-stu-id="803ef-120">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span> <span data-ttu-id="803ef-121">Weitere Informationen zum Definieren dieser Parameter finden Sie unter [Erstellen eines Cmdlets, das das System ändert](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="803ef-121">For more information about defining these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

<span data-ttu-id="803ef-122">Hier ist die Parameter Deklaration für das Cmdlet "Stop-Proc".</span><span class="sxs-lookup"><span data-stu-id="803ef-122">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

```csharp
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;

/// <summary>
/// Specify the Force parameter that allows the user to override
/// the ShouldContinue call to force the stop operation. This
/// parameter should always be used with caution.
/// </summary>
[Parameter]
public SwitchParameter Force
{
  get { return force; }
  set { force = value; }
}
private bool force;

/// <summary>
/// Specify the PassThru parameter that allows the user to specify
/// that the cmdlet should pass the process object down the pipeline
/// after the process has been stopped.
/// </summary>
[Parameter]
public SwitchParameter PassThru
{
  get { return passThru; }
  set { passThru = value; }
}
private bool passThru;
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="803ef-123">Überschreiben einer Eingabe Verarbeitungsmethode</span><span class="sxs-lookup"><span data-stu-id="803ef-123">Overriding an Input Processing Method</span></span>

<span data-ttu-id="803ef-124">Ihr Cmdlet muss eine Eingabe Verarbeitungsmethode überschreiben, meistens handelt es sich um [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="803ef-124">Your cmdlet must override an input processing method, most often it will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="803ef-125">Dieses Stop-Proc-Cmdlet überschreibt die Eingabe Verarbeitungsmethode [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="803ef-125">This Stop-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) input processing method.</span></span> <span data-ttu-id="803ef-126">In dieser Implementierung des Stop-Proc-Cmdlets werden Aufrufe zum Schreiben ausführlicher Nachrichten, Debugmeldungen und Warnmeldungen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="803ef-126">In this implementation of the Stop-Proc cmdlet, calls are made to write verbose messages, debug messages, and warning messages.</span></span>

> [!NOTE]
> <span data-ttu-id="803ef-127">Weitere Informationen dazu, wie diese Methode die Methoden " [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) " und " [System. Management. Automation. Cmdlet. dendcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) " aufruft, finden Sie unter [Erstellen eines Cmdlets, das das System ändert](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="803ef-127">For more information about how this method calls the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="writing-a-verbose-message"></a><span data-ttu-id="803ef-128">Schreiben einer ausführlichen Nachricht</span><span class="sxs-lookup"><span data-stu-id="803ef-128">Writing a Verbose Message</span></span>

<span data-ttu-id="803ef-129">Die [System. Management. Automation. Cmdlet. Write-Verbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) -Methode wird verwendet, um allgemeine Informationen auf Benutzerebene zu schreiben, die mit bestimmten Fehlerbedingungen nicht verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="803ef-129">The [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method is used to write general user-level information that is unrelated to specific error conditions.</span></span> <span data-ttu-id="803ef-130">Der Systemadministrator kann diese Informationen dann verwenden, um mit der Verarbeitung anderer Befehle fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="803ef-130">The system administrator can then use that information to continue processing other commands.</span></span> <span data-ttu-id="803ef-131">Außerdem sollten alle Informationen, die mit dieser Methode geschrieben wurden, nach Bedarf lokalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="803ef-131">In addition, any information written using this method should be localized as needed.</span></span>

<span data-ttu-id="803ef-132">Der folgende Code aus diesem Stop-Proc Cmdlet zeigt zwei Aufrufe der [System. Management. Automation. Cmdlet. Write](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) Items-Methode aus der außer Kraft setzung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode.</span><span class="sxs-lookup"><span data-stu-id="803ef-132">The following code from this Stop-Proc cmdlet shows two calls to the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a><span data-ttu-id="803ef-133">Schreiben einer Debugmeldung</span><span class="sxs-lookup"><span data-stu-id="803ef-133">Writing a Debug Message</span></span>

<span data-ttu-id="803ef-134">Die [System. Management. Automation. Cmdlet. Write-Debug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) -Methode wird verwendet, um Debugmeldungen zu schreiben, die für die Problembehandlung des Cmdlets verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="803ef-134">The [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method is used to write debug messages that can be used to troubleshoot the operation of the cmdlet.</span></span> <span data-ttu-id="803ef-135">Der-Befehl wird von einer Eingabe Verarbeitungsmethode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="803ef-135">The call is made from an input processing method.</span></span>

> [!NOTE]
> <span data-ttu-id="803ef-136">Windows PowerShell definiert auch einen `Debug` Parameter, der sowohl ausführliche als auch Debuginformationen darstellt.</span><span class="sxs-lookup"><span data-stu-id="803ef-136">Windows PowerShell also defines a `Debug` parameter that presents both verbose and debug information.</span></span> <span data-ttu-id="803ef-137">Wenn das Cmdlet diesen Parameter unterstützt, muss das [System. Management. Automation. Cmdlet. Write-Debug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) nicht im gleichen Code aufgerufen werden, der [System. Management. Automation. Cmdlet. Write-Verbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose)aufruft.</span><span class="sxs-lookup"><span data-stu-id="803ef-137">If your cmdlet supports this parameter, it does not need to call [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) in the same code that calls [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span></span>

<span data-ttu-id="803ef-138">Die folgenden beiden Code Abschnitte aus dem Beispiel Stop-Proc-Cmdlet zeigen Aufrufe der [System. Management. Automation. Cmdlet. Write Team Debug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) -Methode aus der Überschreibung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode an.</span><span class="sxs-lookup"><span data-stu-id="803ef-138">The following two sections of code from the sample Stop-Proc cmdlet show calls to the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="803ef-139">Diese Debugmeldung wird unmittelbar vor dem Aufruf von [System. Management. Automation. Cmdlet. Schulter Process](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) geschrieben.</span><span class="sxs-lookup"><span data-stu-id="803ef-139">This debug message is written immediately before [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) is called.</span></span>

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

<span data-ttu-id="803ef-140">Diese Debugmeldung wird unmittelbar vor dem Aufruf von [System. Management. Automation. Cmdlet. Write-Object](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) geschrieben.</span><span class="sxs-lookup"><span data-stu-id="803ef-140">This debug message is written immediately before [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) is called.</span></span>

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

<span data-ttu-id="803ef-141">Windows PowerShell leitet automatisch alle [System. Management. Automation. Cmdlet. Write-Debug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) -Aufrufe an die Ablauf Verfolgungs Infrastruktur und-Cmdlets weiter.</span><span class="sxs-lookup"><span data-stu-id="803ef-141">Windows PowerShell automatically routes any [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) calls to the tracing infrastructure and cmdlets.</span></span> <span data-ttu-id="803ef-142">Dies ermöglicht es, dass die Methodenaufrufe auf die Host Anwendung, eine Datei oder einen Debugger nachverfolgt werden, ohne dass Sie zusätzliche Entwicklungsaufgaben innerhalb des Cmdlets ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="803ef-142">This allows the method calls to be traced to the hosting application, a file, or a debugger without your having to do any extra development work within the cmdlet.</span></span> <span data-ttu-id="803ef-143">Der folgende Befehlszeilen Eintrag implementiert einen Ablauf Verfolgungs Vorgang.</span><span class="sxs-lookup"><span data-stu-id="803ef-143">The following command-line entry implements a tracing operation.</span></span>

<span data-ttu-id="803ef-144">**PS> Trace-Expression-Vorgang zum Abbrechen der Prozedur "-proc-File proc. log-Command".**</span><span class="sxs-lookup"><span data-stu-id="803ef-144">**PS> trace-expression stop-proc -file proc.log -command stop-proc notepad**</span></span>

## <a name="writing-a-warning-message"></a><span data-ttu-id="803ef-145">Schreiben einer Warnmeldung</span><span class="sxs-lookup"><span data-stu-id="803ef-145">Writing a Warning Message</span></span>

<span data-ttu-id="803ef-146">Die [System. Management. Automation. Cmdlet. WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) -Methode wird verwendet, um eine Warnung zu schreiben, wenn das Cmdlet einen Vorgang ausführt, der möglicherweise ein unerwartetes Ergebnis hat, z. b. eine schreibgeschützte Datei.</span><span class="sxs-lookup"><span data-stu-id="803ef-146">The [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method is used to write a warning when the cmdlet is about to perform an operation that might have an unexpected result, for example, overwriting a read-only file.</span></span>

<span data-ttu-id="803ef-147">Der folgende Code aus dem Beispiel Stop-Proc-Cmdlet zeigt den aufzurufenden Befehl der [System. Management. Automation. Cmdlet. Write-Warning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) -Methode aus der Überschreibung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode.</span><span class="sxs-lookup"><span data-stu-id="803ef-147">The following code from the sample Stop-Proc cmdlet shows the call to the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a><span data-ttu-id="803ef-148">Schreiben einer Fortschrittsmeldung</span><span class="sxs-lookup"><span data-stu-id="803ef-148">Writing a Progress Message</span></span>

<span data-ttu-id="803ef-149">Der [System. Management. Automation. Cmdlet. Write Progress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) wird zum Schreiben von Statusmeldungen verwendet, wenn die Ausführung von Cmdlet-Vorgängen eine längere Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="803ef-149">The [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) is used to write progress messages when cmdlet operations take an extended amount of time to complete.</span></span> <span data-ttu-id="803ef-150">Ein System [. Management. Automation. Cmdlet. Write](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) -Vorgang übergibt ein [System. Management. Automation. progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) -Objekt, das zum Rendern an den Benutzer an die Host Anwendung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="803ef-150">A call to [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passes a [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) object that is sent to the hosting application for rendering to the user.</span></span>

> [!NOTE]
> <span data-ttu-id="803ef-151">Dieses Stop-Proc-Cmdlet enthält keinen aufrufsvorgang der [System. Management. Automation. Cmdlet. Write Progress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) -Methode.</span><span class="sxs-lookup"><span data-stu-id="803ef-151">This Stop-Proc cmdlet does not include a call to the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

<span data-ttu-id="803ef-152">Der folgende Code ist ein Beispiel für eine Fortschrittsmeldung, die von einem Cmdlet geschrieben wird, das versucht, ein Element zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="803ef-152">The following code is an example of a progress message written by a cmdlet that is attempting to copy an item.</span></span>

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a><span data-ttu-id="803ef-153">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="803ef-153">Code Sample</span></span>

<span data-ttu-id="803ef-154">Den gesamten c#-Beispielcode finden Sie unter [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span><span class="sxs-lookup"><span data-stu-id="803ef-154">For the complete C# sample code, see [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="803ef-155">Definieren von Objekttypen und Formatierung</span><span class="sxs-lookup"><span data-stu-id="803ef-155">Define Object Types and Formatting</span></span>

<span data-ttu-id="803ef-156">Windows PowerShell übergibt Informationen zwischen Cmdlets mithilfe von .NET-Objekten.</span><span class="sxs-lookup"><span data-stu-id="803ef-156">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="803ef-157">Folglich muss ein Cmdlet möglicherweise seinen eigenen Typ definieren, oder das Cmdlet muss möglicherweise einen vorhandenen Typ erweitern, der von einem anderen Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="803ef-157">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="803ef-158">Weitere Informationen zum Definieren neuer Typen oder zum Erweitern vorhandener Typen finden Sie unter [Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="803ef-158">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="803ef-159">Cmdlet wird aufgebaut</span><span class="sxs-lookup"><span data-stu-id="803ef-159">Building the Cmdlet</span></span>

<span data-ttu-id="803ef-160">Nachdem ein Cmdlet implementiert wurde, muss es über ein Windows PowerShell-Snap-in in Windows PowerShell registriert werden.</span><span class="sxs-lookup"><span data-stu-id="803ef-160">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="803ef-161">Weitere Informationen zum Registrieren von Cmdlets finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="803ef-161">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="803ef-162">Testen des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="803ef-162">Testing the Cmdlet</span></span>

<span data-ttu-id="803ef-163">Wenn das Cmdlet bei Windows PowerShell registriert wurde, können Sie es in der Befehlszeile testen.</span><span class="sxs-lookup"><span data-stu-id="803ef-163">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="803ef-164">Testen Sie nun das Cmdlet "Sample Stop-Proc".</span><span class="sxs-lookup"><span data-stu-id="803ef-164">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="803ef-165">Weitere Informationen zur Verwendung von Cmdlets über die Befehlszeile finden Sie unter [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="803ef-165">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="803ef-166">Im folgenden Befehlszeilen Eintrag wird Stop-Proc verwendet, um den Prozess mit dem Namen "Notepad" anzuhalten, ausführliche Benachrichtigungen bereitzustellen und Debuginformationen zu drucken.</span><span class="sxs-lookup"><span data-stu-id="803ef-166">The following command-line entry uses Stop-Proc to stop the process named "NOTEPAD", provide verbose notifications, and print debug information.</span></span>

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

    <span data-ttu-id="803ef-167">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="803ef-167">The following output appears.</span></span>

    ```
    VERBOSE: Attempting to stop process " notepad ".
    DEBUG: Acquired name for pid 5584 : "notepad"

    Confirm
    Continue with this operation?
    [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): Y

    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (5584)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    VERBOSE: Stopped process "notepad", pid 5584.
    ```

## <a name="see-also"></a><span data-ttu-id="803ef-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="803ef-168">See Also</span></span>

[<span data-ttu-id="803ef-169">Erstellen Sie ein Cmdlet, das das System ändert.</span><span class="sxs-lookup"><span data-stu-id="803ef-169">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="803ef-170">Erstellen eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="803ef-170">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="803ef-171">[Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="803ef-171">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="803ef-172">[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="803ef-172">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="803ef-173">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="803ef-173">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
