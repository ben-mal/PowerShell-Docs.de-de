---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen eines Cmdlet, das das System ändert
description: Erstellen eines Cmdlet, das das System ändert
ms.openlocfilehash: 757f2c97bb4b5dcf2fb633cd35fe52bc5f6c5cf9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355543"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a><span data-ttu-id="41e4a-103">Erstellen eines Cmdlet, das das System ändert</span><span class="sxs-lookup"><span data-stu-id="41e4a-103">Creating a Cmdlet that Modifies the System</span></span>

<span data-ttu-id="41e4a-104">Manchmal muss ein Cmdlet den Lauf Zustand des Systems ändern, nicht nur den Status der Windows PowerShell-Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="41e4a-104">Sometimes a cmdlet must modify the running state of the system, not just the state of the Windows PowerShell runtime.</span></span> <span data-ttu-id="41e4a-105">In diesen Fällen sollte das Cmdlet dem Benutzer die Möglichkeit geben, zu bestätigen, ob die Änderung vorgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="41e4a-105">In these cases, the cmdlet should allow the user a chance to confirm whether or not to make the change.</span></span>

<span data-ttu-id="41e4a-106">Zur Unterstützung der Bestätigung muss ein Cmdlet zwei Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-106">To support confirmation a cmdlet must do two things.</span></span>

- <span data-ttu-id="41e4a-107">Deklarieren Sie, dass das Cmdlet die Bestätigung unterstützt, wenn Sie das [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) -Attribut angeben, indem Sie das Schlüsselwort supportsschulter dprocess auf festlegen `true` .</span><span class="sxs-lookup"><span data-stu-id="41e4a-107">Declare that the cmdlet supports confirmation when you specify the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute by setting the SupportsShouldProcess keyword to `true`.</span></span>

- <span data-ttu-id="41e4a-108">Während der Ausführung des Cmdlets wird [System. Management. Automation. Cmdlet. rudprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) aufgerufen (wie im folgenden Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="41e4a-108">Call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) during the execution of the cmdlet (as shown in the following example).</span></span>

<span data-ttu-id="41e4a-109">Durch die Unterstützung der Bestätigung macht ein Cmdlet den `Confirm` -Parameter und den-Parameter verfügbar, die `WhatIf` von Windows PowerShell bereitgestellt werden, und erfüllt außerdem die Entwicklungs Richtlinien für Cmdlets (Weitere Informationen zu Cmdlet-Entwicklungs Richtlinien finden Sie unter [Cmdlet-Entwicklungs Richtlinien](./cmdlet-development-guidelines.md)).</span><span class="sxs-lookup"><span data-stu-id="41e4a-109">By supporting confirmation, a cmdlet exposes the `Confirm` and `WhatIf` parameters that are provided by Windows PowerShell, and also meets the development guidelines for cmdlets (For more information about cmdlet development guidelines, see [Cmdlet Development Guidelines](./cmdlet-development-guidelines.md).).</span></span>

## <a name="changing-the-system"></a><span data-ttu-id="41e4a-110">Ändern des Systems</span><span class="sxs-lookup"><span data-stu-id="41e4a-110">Changing the System</span></span>

<span data-ttu-id="41e4a-111">Der Vorgang "Ändern des Systems" bezieht sich auf jedes Cmdlet, das möglicherweise den Status des Systems außerhalb von Windows PowerShell ändert.</span><span class="sxs-lookup"><span data-stu-id="41e4a-111">The act of "changing the system" refers to any cmdlet that potentially changes the state of the system outside Windows PowerShell.</span></span> <span data-ttu-id="41e4a-112">Das Beenden eines Prozesses, das Aktivieren oder Deaktivieren eines Benutzerkontos oder das Hinzufügen einer Zeile zu einer Datenbanktabelle sind alle Änderungen am System, die bestätigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-112">For example, stopping a process, enabling or disabling a user account, or adding a row to a database table are all changes to the system that should be confirmed.</span></span>
<span data-ttu-id="41e4a-113">Im Gegensatz dazu ändern Vorgänge, die Daten lesen oder vorübergehende Verbindungen herstellen, das System nicht und erfordern im Allgemeinen keine Bestätigung.</span><span class="sxs-lookup"><span data-stu-id="41e4a-113">In contrast, operations that read data or establish transient connections do not change the system and generally do not require confirmation.</span></span> <span data-ttu-id="41e4a-114">Die Bestätigung wird auch nicht für Aktionen benötigt, deren Auswirkung auf in der Windows PowerShell-Laufzeit beschränkt ist, z `set-variable` . b..</span><span class="sxs-lookup"><span data-stu-id="41e4a-114">Confirmation is also not needed for actions whose effect is limited to inside the Windows PowerShell runtime, such as `set-variable`.</span></span> <span data-ttu-id="41e4a-115">Cmdlets, die eine permanente Änderung möglicherweise vornehmen, sollten die Deklaration `SupportsShouldProcess` von [System. Management. Automation. Cmdlet. dauerdprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) nur dann deklarieren, wenn Sie eine permanente Änderung durchführen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-115">Cmdlets that might or might not make a persistent change should declare `SupportsShouldProcess` and call [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) only if they are about to make a persistent change.</span></span>

> [!NOTE]
> <span data-ttu-id="41e4a-116">Die Bestätigungsprozess Bestätigung gilt nur für Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="41e4a-116">ShouldProcess confirmation applies only to cmdlets.</span></span> <span data-ttu-id="41e4a-117">Wenn ein Befehl oder ein Skript den Lauf Zustand eines Systems durch direktes Aufrufen von .NET-Methoden oder-Eigenschaften oder durch Aufrufen von Anwendungen außerhalb von Windows PowerShell ändert, ist diese Form der Bestätigung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="41e4a-117">If a command or script modifies the running state of a system by directly calling .NET methods or properties, or by calling applications outside of Windows PowerShell, this form of confirmation will not be available.</span></span>

## <a name="the-stopproc-cmdlet"></a><span data-ttu-id="41e4a-118">Das stopproc-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="41e4a-118">The StopProc Cmdlet</span></span>

<span data-ttu-id="41e4a-119">In diesem Thema wird ein Stop-Proc Cmdlet beschrieben, das versucht, Prozesse zu verhindern, die mithilfe des Get-Proc-Cmdlets abgerufen werden (siehe [Erstellen des ersten Cmdlets](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="41e4a-119">This topic describes a Stop-Proc cmdlet that attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="41e4a-120">Definieren des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="41e4a-120">Defining the Cmdlet</span></span>

<span data-ttu-id="41e4a-121">Der erste Schritt bei der Cmdlet-Erstellung ist die Benennung des Cmdlets und das Deklarieren der .NET-Klasse, die das Cmdlet implementiert.</span><span class="sxs-lookup"><span data-stu-id="41e4a-121">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="41e4a-122">Da Sie ein Cmdlet schreiben, um das System zu ändern, sollte es entsprechend benannt werden.</span><span class="sxs-lookup"><span data-stu-id="41e4a-122">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="41e4a-123">Dieses Cmdlet beendet System Prozesse, sodass der hier gewählte Verb Name "Stopp" ist, der von der [System. Management. Automation. verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) -Klasse definiert wird, mit dem Substantiv "proc", um anzugeben, dass das Cmdlet Prozesse beendet.</span><span class="sxs-lookup"><span data-stu-id="41e4a-123">This cmdlet stops system processes, so the verb name chosen here is "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate that the cmdlet stops processes.</span></span> <span data-ttu-id="41e4a-124">Weitere Informationen zu genehmigten Cmdlet-Verben finden Sie unter [Cmdlet-Verb Namen](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="41e4a-124">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="41e4a-125">Im folgenden finden Sie die Klassendefinition für dieses Stop-Proc-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41e4a-125">The following is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

<span data-ttu-id="41e4a-126">Beachten Sie, dass das Attribut Schlüsselwort in der [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) -Deklaration `SupportsShouldProcess` auf festgelegt ist, `true` um das Cmdlet zum Aufrufen von [System. Management. Automation. Cmdlet. Schulter dprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) und [System. Management. Automation. Cmdlet. Schulter dcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="41e4a-126">Be aware that in the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration, the `SupportsShouldProcess` attribute keyword is set to `true` to enable the cmdlet to make calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>
<span data-ttu-id="41e4a-127">Wenn dieses Schlüsselwort nicht festgelegt ist, sind der `Confirm` - `WhatIf` Parameter und der-Parameter für den Benutzer nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="41e4a-127">Without this keyword set, the `Confirm` and `WhatIf` parameters will not be available to the user.</span></span>

### <a name="extremely-destructive-actions"></a><span data-ttu-id="41e4a-128">Äußerst zerstörerische Aktionen</span><span class="sxs-lookup"><span data-stu-id="41e4a-128">Extremely Destructive Actions</span></span>

<span data-ttu-id="41e4a-129">Einige Vorgänge sind äußerst destruktiv, z. b. die Neuformatierung einer aktiven Festplatten Partition.</span><span class="sxs-lookup"><span data-stu-id="41e4a-129">Some operations are extremely destructive, such as reformatting an active hard disk partition.</span></span> <span data-ttu-id="41e4a-130">In diesen Fällen muss das Cmdlet `ConfirmImpact`  =  `ConfirmImpact.High` beim Deklarieren des [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) -Attributs festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="41e4a-130">In these cases, the cmdlet should set `ConfirmImpact` = `ConfirmImpact.High` when declaring the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute.</span></span> <span data-ttu-id="41e4a-131">Diese Einstellung erzwingt, dass das Cmdlet die Benutzer Bestätigung anfordert, auch wenn der Benutzer den Parameter nicht angegeben hat `Confirm` .</span><span class="sxs-lookup"><span data-stu-id="41e4a-131">This setting forces the cmdlet to request user confirmation even when the user has not specified the `Confirm` parameter.</span></span> <span data-ttu-id="41e4a-132">Cmdlet-Entwickler sollten jedoch die übermäßige Verwendung `ConfirmImpact` von Vorgängen vermeiden, die nur potenziell destruktiv sind, z. b. das Löschen eines Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="41e4a-132">However, cmdlet developers should avoid overusing `ConfirmImpact` for operations that are just potentially destructive, such as deleting a user account.</span></span> <span data-ttu-id="41e4a-133">Beachten Sie, dass, wenn `ConfirmImpact` auf [System. Management. Automation. confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact) 
 **High** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="41e4a-133">Remember that if `ConfirmImpact` is set to [System.Management.Automation.ConfirmImpact](/dotnet/api/System.Management.Automation.ConfirmImpact)
**High**.</span></span>

<span data-ttu-id="41e4a-134">Ebenso ist es unwahrscheinlich, dass einige Vorgänge destruktiv sind, obwohl Sie theoretisch den Lauf Zustand eines Systems außerhalb von Windows PowerShell ändern.</span><span class="sxs-lookup"><span data-stu-id="41e4a-134">Similarly, some operations are unlikely to be destructive, although they do in theory modify the running state of a system outside Windows PowerShell.</span></span> <span data-ttu-id="41e4a-135">Diese Cmdlets können `ConfirmImpact` auf [System. Management. Automation. confirmimpact. Low](/dotnet/api/system.management.automation.confirmimpact)festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="41e4a-135">Such cmdlets can set `ConfirmImpact` to [System.Management.Automation.Confirmimpact.Low](/dotnet/api/system.management.automation.confirmimpact).</span></span>
<span data-ttu-id="41e4a-136">Dadurch werden Bestätigungs Anforderungen umgangen, bei denen der Benutzer aufgefordert wurde, nur Vorgänge mit mittlerer Auswirkung und hohem Einfluss zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-136">This will bypass confirmation requests where the user has asked to confirm only medium-impact and high-impact operations.</span></span>

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="41e4a-137">Definieren von Parametern für die System Änderung</span><span class="sxs-lookup"><span data-stu-id="41e4a-137">Defining Parameters for System Modification</span></span>

<span data-ttu-id="41e4a-138">In diesem Abschnitt wird beschrieben, wie Sie die Cmdlet-Parameter definieren, einschließlich derjenigen, die zur Unterstützung der Systemänderung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="41e4a-138">This section describes how to define the cmdlet parameters, including those that are needed to support system modification.</span></span> <span data-ttu-id="41e4a-139">Weitere Informationen zum Definieren von Parametern finden Sie unter [Hinzufügen von Parametern, die die Befehlszeilen Eingabe verarbeiten](./adding-parameters-that-process-command-line-input.md) .</span><span class="sxs-lookup"><span data-stu-id="41e4a-139">See [Adding Parameters that Process CommandLine Input](./adding-parameters-that-process-command-line-input.md) if you need general information about defining parameters.</span></span>

<span data-ttu-id="41e4a-140">Das-Cmdlet "Stop-Proc" definiert drei Parameter: `Name` , `Force` und `PassThru` .</span><span class="sxs-lookup"><span data-stu-id="41e4a-140">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span>

<span data-ttu-id="41e4a-141">Der- `Name` Parameter entspricht der- `Name` Eigenschaft des Process Input-Objekts.</span><span class="sxs-lookup"><span data-stu-id="41e4a-141">The `Name` parameter corresponds to the `Name` property of the process input object.</span></span> <span data-ttu-id="41e4a-142">Beachten Sie, dass der `Name` Parameter in diesem Beispiel obligatorisch ist, da das Cmdlet fehlschlägt, wenn kein benannter Prozess zum Abbrechen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="41e4a-142">Be aware that the `Name` parameter in this sample is mandatory, as the cmdlet will fail if it does not have a named process to stop.</span></span>

<span data-ttu-id="41e4a-143">Der- `Force` Parameter ermöglicht es dem Benutzer, Aufrufe von [System. Management. Automation. Cmdlet. daudcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="41e4a-143">The `Force` parameter allows the user to override calls to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue).</span></span>
<span data-ttu-id="41e4a-144">Tatsächlich sollte jedes Cmdlet, das [System. Management. Automation. Cmdlet. schuldcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) aufruft, über einen-Parameter verfügen, `Force` sodass `Force` das Cmdlet den Aufruf von [System. Management. Automation. Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) überspringt und den Vorgang fortsetzt, wenn angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="41e4a-144">In fact, any cmdlet that calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) should have a `Force` parameter so that when `Force` is specified, the cmdlet skips the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) and proceeds with the operation.</span></span> <span data-ttu-id="41e4a-145">Beachten Sie, dass dies keine Auswirkungen auf Aufrufe von [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)hat.</span><span class="sxs-lookup"><span data-stu-id="41e4a-145">Be aware that this does not affect calls to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess).</span></span>

<span data-ttu-id="41e4a-146">Mit dem- `PassThru` Parameter kann der Benutzer angeben, ob das Cmdlet ein Ausgabe Objekt über die Pipeline übergibt, in diesem Fall, nachdem ein Prozess angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="41e4a-146">The `PassThru` parameter allows the user to indicate whether the cmdlet passes an output object through the pipeline, in this case, after a process is stopped.</span></span> <span data-ttu-id="41e4a-147">Beachten Sie, dass dieser Parameter nicht an eine Eigenschaft des Eingabe Objekts, sondern an das Cmdlet selbst gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="41e4a-147">Be aware that this parameter is tied to the cmdlet itself instead of to a property of the input object.</span></span>

<span data-ttu-id="41e4a-148">Hier ist die Parameter Deklaration für das Cmdlet "Stop-Proc".</span><span class="sxs-lookup"><span data-stu-id="41e4a-148">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="41e4a-149">Überschreiben einer Eingabe Verarbeitungsmethode</span><span class="sxs-lookup"><span data-stu-id="41e4a-149">Overriding an Input Processing Method</span></span>

<span data-ttu-id="41e4a-150">Das Cmdlet muss eine Eingabe Verarbeitungsmethode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="41e4a-150">The cmdlet must override an input processing method.</span></span> <span data-ttu-id="41e4a-151">Der folgende Code veranschaulicht die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -außer Kraft setzung, die im Beispiel Stop-Proc-Cmdlet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="41e4a-151">The following code illustrates the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override used in the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="41e4a-152">Diese Methode stellt für jeden angeforderten Prozessnamen sicher, dass es sich bei dem Prozess nicht um einen speziellen Prozess handelt, versucht, den Prozess zu beenden, und sendet dann ein Ausgabe Objekt, wenn der `PassThru` Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="41e4a-152">For each requested process name, this method ensures that the process is not a special process, tries to stop the process, and then sends an output object if the `PassThru` parameter is specified.</span></span>

```csharp
protected override void ProcessRecord()
{
  foreach (string name in processNames)
  {
    // For every process name passed to the cmdlet, get the associated
    // process(es). For failures, write a non-terminating error
    Process[] processes;

    try
    {
      processes = Process.GetProcessesByName(name);
    }
    catch (InvalidOperationException ioe)
    {
      WriteError(new ErrorRecord(ioe,"Unable to access the target process by name",
                 ErrorCategory.InvalidOperation, name));
      continue;
    }

    // Try to stop the process(es) that have been retrieved for a name
    foreach (Process process in processes)
    {
      string processName;

      try
      {
        processName = process.ProcessName;
      }

      catch (Win32Exception e)
        {
          WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                     ErrorCategory.ReadError, process));
          continue;
        }

        // Call Should Process to confirm the operation first.
        // This is always false if WhatIf is set.
        if (!ShouldProcess(string.Format("{0} ({1})", processName,
                           process.Id)))
        {
          continue;
        }
        // Call ShouldContinue to make sure the user really does want
        // to stop a critical process that could possibly stop the computer.
        bool criticalProcess =
             criticalProcessNames.Contains(processName.ToLower());

        if (criticalProcess &&!force)
        {
          string message = String.Format
                ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                processName);

          // It is possible that ProcessRecord is called multiple times
          // when the Name parameter receives objects as input from the
          // pipeline. So to retain YesToAll and NoToAll input that the
          // user may enter across multiple calls to ProcessRecord, this
          // information is stored as private members of the cmdlet.
          if (!ShouldContinue(message, "Warning!",
                              ref yesToAll,
                              ref noToAll))
          {
            continue;
          }
        } // if (criticalProcess...
        // Stop the named process.
        try
        {
          process.Kill();
        }
        catch (Exception e)
        {
          if ((e is Win32Exception) || (e is SystemException) ||
              (e is InvalidOperationException))
          {
            // This process could not be stopped so write
            // a non-terminating error.
            string message = String.Format("{0} {1} {2}",
                             "Could not stop process \"", processName,
                             "\".");
            WriteError(new ErrorRecord(e, message,
                       ErrorCategory.CloseError, process));
                       continue;
          } // if ((e is...
          else throw;
        } // catch

        // If the PassThru parameter argument is
        // True, pass the terminated process on.
        if (passThru)
        {
          WriteObject(process);
        }
    } // foreach (Process...
  } // foreach (string...
} // ProcessRecord
```

## <a name="calling-the-shouldprocess-method"></a><span data-ttu-id="41e4a-153">Aufrufen der Methode "tiondprocess"</span><span class="sxs-lookup"><span data-stu-id="41e4a-153">Calling the ShouldProcess Method</span></span>

<span data-ttu-id="41e4a-154">Die Eingabe Verarbeitungsmethode des Cmdlets muss die [System. Management. Automation. Cmdlet. Schulter dprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Methode aufgerufen werden, um die Ausführung eines Vorgangs vor einer Änderung (z. b. das Löschen von Dateien) zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-154">The input processing method of your cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) method to confirm execution of an operation before a change (for example, deleting files) is made to the running state of the system.</span></span> <span data-ttu-id="41e4a-155">Dadurch kann die Windows PowerShell-Laufzeit das richtige "WhatIf"-und "Confirm"-Verhalten innerhalb der Shell bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-155">This allows the Windows PowerShell runtime to supply the correct "WhatIf" and "Confirm" behavior within the shell.</span></span>

> [!NOTE]
> <span data-ttu-id="41e4a-156">Wenn ein Cmdlet angibt, dass es von unterstützt wird, und den [System. Management. Automation. Cmdlet.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) --Prozess nicht aufzurufen, kann der Benutzer das System möglicherweise unerwartet ändern.</span><span class="sxs-lookup"><span data-stu-id="41e4a-156">If a cmdlet states that it supports should process and fails to make the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) call, the user might modify the system unexpectedly.</span></span>

<span data-ttu-id="41e4a-157">Der [System. Management. Automation. Cmdlet. tiondprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Befehl sendet den Namen der Ressource, die an den Benutzer geändert werden soll, wobei die Windows PowerShell-Laufzeit alle Befehlszeilen Einstellungen oder Einstellungs Variablen berücksichtigt, um zu bestimmen, was dem Benutzer angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="41e4a-157">The call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) sends the name of the resource to be changed to the user, with the Windows PowerShell runtime taking into account any command-line settings or preference variables in determining what should be displayed to the user.</span></span>

<span data-ttu-id="41e4a-158">Im folgenden Beispiel wird der System [. Management. Automation. Cmdlet. dendprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Befehl aus der Überschreibung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode im Sample Stop-Proc-Cmdlet gezeigt.</span><span class="sxs-lookup"><span data-stu-id="41e4a-158">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a><span data-ttu-id="41e4a-159">Aufrufen der Methode "schuldcontinue"</span><span class="sxs-lookup"><span data-stu-id="41e4a-159">Calling the ShouldContinue Method</span></span>

<span data-ttu-id="41e4a-160">Der Aufrufe der [System. Management. Automation. Cmdlet. Schulter dcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) -Methode sendet eine sekundäre Nachricht an den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="41e4a-160">The call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method sends a secondary message to the user.</span></span> <span data-ttu-id="41e4a-161">Dieser-Befehl wird nach dem Aufrufen von [System. Management. Automation. Cmdlet. daudprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) zurückgegeben `true` und, wenn der- `Force` Parameter nicht auf festgelegt wurde `true` .</span><span class="sxs-lookup"><span data-stu-id="41e4a-161">This call is made after the call to [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) returns `true` and if the `Force` parameter was not set to `true`.</span></span> <span data-ttu-id="41e4a-162">Der Benutzer kann dann Feedback geben, um anzugeben, ob der Vorgang fortgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="41e4a-162">The user can then provide feedback to say whether the operation should be continued.</span></span> <span data-ttu-id="41e4a-163">Ihr Cmdlet ruft die [System. Management. Automation. Cmdlet. tiondcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) auf, um eine zusätzliche Überprüfung auf potenziell gefährliche System Änderungen vorzunehmen, oder wenn Sie dem Benutzer die Optionen Yes-to-all und No-to-all bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="41e4a-163">Your cmdlet calls [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) as an additional check for potentially dangerous system modifications or when you want to provide yes-to-all and no-to-all options to the user.</span></span>

<span data-ttu-id="41e4a-164">Im folgenden Beispiel wird der System [. Management. Automation. Cmdlet.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) Wing-Befehl von der Überschreibung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode des Cmdlets Sample Stop-Proc gezeigt.</span><span class="sxs-lookup"><span data-stu-id="41e4a-164">The following example shows the call to [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method in the sample Stop-Proc cmdlet.</span></span>

```csharp
if (criticalProcess &&!force)
{
  string message = String.Format
        ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
        processName);

  // It is possible that ProcessRecord is called multiple times
  // when the Name parameter receives objects as input from the
  // pipeline. So to retain YesToAll and NoToAll input that the
  // user may enter across multiple calls to ProcessRecord, this
  // information is stored as private members of the cmdlet.
  if (!ShouldContinue(message, "Warning!",
                      ref yesToAll,
                      ref noToAll))
  {
    continue;
  }
} // if (criticalProcess...
```

## <a name="stopping-input-processing"></a><span data-ttu-id="41e4a-165">Beenden der Eingabe Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="41e4a-165">Stopping Input Processing</span></span>

<span data-ttu-id="41e4a-166">Die Eingabe Verarbeitungsmethode eines Cmdlets, das Systemänderungen vornimmt, muss eine Möglichkeit zum Beenden der Verarbeitung von Eingaben bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-166">The input processing method of a cmdlet that makes system modifications must provide a way of stopping the processing of input.</span></span> <span data-ttu-id="41e4a-167">Bei diesem Stop-Proc Cmdlet wird von der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode der System. [Diagnostics. Process. Kill \*](/dotnet/api/System.Diagnostics.Process.Kill) -Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-167">In the case of this Stop-Proc cmdlet, a call is made from the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to the [System.Diagnostics.Process.Kill\*](/dotnet/api/System.Diagnostics.Process.Kill) method.</span></span> <span data-ttu-id="41e4a-168">Da der- `PassThru` Parameter auf festgelegt ist, wird von `true` [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) auch [System. Management. Automation. Cmdlet. Write Object](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) aufgerufen, um das Prozess Objekt an die Pipeline zu senden.</span><span class="sxs-lookup"><span data-stu-id="41e4a-168">Because the `PassThru` parameter is set to `true`, [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) also calls [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) to send the process object to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="41e4a-169">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="41e4a-169">Code Sample</span></span>

<span data-ttu-id="41e4a-170">Den gesamten c#-Beispielcode finden Sie unter [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span><span class="sxs-lookup"><span data-stu-id="41e4a-170">For the complete C# sample code, see [StopProcessSample01 Sample](./stopprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="41e4a-171">Definieren von Objekttypen und Formatierung</span><span class="sxs-lookup"><span data-stu-id="41e4a-171">Defining Object Types and Formatting</span></span>

<span data-ttu-id="41e4a-172">Windows PowerShell übergibt Informationen zwischen Cmdlets mithilfe von .NET-Objekten.</span><span class="sxs-lookup"><span data-stu-id="41e4a-172">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="41e4a-173">Folglich muss ein Cmdlet möglicherweise seinen eigenen Typ definieren, oder das Cmdlet muss möglicherweise einen vorhandenen Typ erweitern, der von einem anderen Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="41e4a-173">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="41e4a-174">Weitere Informationen zum Definieren neuer Typen oder zum Erweitern vorhandener Typen finden Sie unter [Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="41e4a-174">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="41e4a-175">Cmdlet wird aufgebaut</span><span class="sxs-lookup"><span data-stu-id="41e4a-175">Building the Cmdlet</span></span>

<span data-ttu-id="41e4a-176">Nachdem ein Cmdlet implementiert wurde, muss es über ein Windows PowerShell-Snap-in in Windows PowerShell registriert werden.</span><span class="sxs-lookup"><span data-stu-id="41e4a-176">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="41e4a-177">Weitere Informationen zum Registrieren von Cmdlets finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="41e4a-177">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="41e4a-178">Testen des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="41e4a-178">Testing the Cmdlet</span></span>

<span data-ttu-id="41e4a-179">Wenn das Cmdlet bei Windows PowerShell registriert wurde, können Sie es in der Befehlszeile testen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-179">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="41e4a-180">Es folgen mehrere Tests, bei denen das Stop-Proc-Cmdlet getestet wird.</span><span class="sxs-lookup"><span data-stu-id="41e4a-180">Here are several tests that test the Stop-Proc cmdlet.</span></span> <span data-ttu-id="41e4a-181">Weitere Informationen zur Verwendung von Cmdlets über die Befehlszeile finden Sie unter [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="41e4a-181">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="41e4a-182">Starten Sie Windows PowerShell, und verwenden Sie das Cmdlet "Stop-Proc", um die Verarbeitung wie unten dargestellt zu starten</span><span class="sxs-lookup"><span data-stu-id="41e4a-182">Start Windows PowerShell and use the Stop-Proc cmdlet to stop processing as shown below.</span></span> <span data-ttu-id="41e4a-183">Da das Cmdlet den `Name` Parameter als obligatorisch angibt, fragt das Cmdlet den Parameter ab.</span><span class="sxs-lookup"><span data-stu-id="41e4a-183">Because the cmdlet specifies the `Name` parameter as mandatory, the cmdlet queries for the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

    <span data-ttu-id="41e4a-184">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41e4a-184">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- <span data-ttu-id="41e4a-185">Nun verwenden wir das Cmdlet, um den Prozess mit dem Namen "Notepad" zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="41e4a-185">Now let's use the cmdlet to stop the process named "NOTEPAD".</span></span> <span data-ttu-id="41e4a-186">Mit dem-Cmdlet werden Sie aufgefordert, die Aktion zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="41e4a-186">The cmdlet asks you to confirm the action.</span></span>

    ```powershell
    PS> stop-proc -Name notepad
    ```

    <span data-ttu-id="41e4a-187">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41e4a-187">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="41e4a-188">Verwenden Sie Stop-Proc wie gezeigt, um den kritischen Prozess mit dem Namen "Winlogon" zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="41e4a-188">Use Stop-Proc as shown to stop the critical process named "WINLOGON".</span></span> <span data-ttu-id="41e4a-189">Sie werden dazu aufgefordert, diese Aktion auszuführen, da dies dazu führt, dass das Betriebssystem neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="41e4a-189">You are prompted and warned about performing this action because it will cause the operating system to reboot.</span></span>

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

    <span data-ttu-id="41e4a-190">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41e4a-190">The following output appears.</span></span>

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- <span data-ttu-id="41e4a-191">Versuchen Sie jetzt, den Winlogon-Prozess anzuhalten, ohne eine Warnung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="41e4a-191">Let's now try to stop the WINLOGON process without receiving a warning.</span></span> <span data-ttu-id="41e4a-192">Beachten Sie, dass dieser Befehls Eintrag den- `Force` Parameter verwendet, um die Warnung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="41e4a-192">Be aware that this command entry uses the `Force` parameter to override the warning.</span></span>

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

    <span data-ttu-id="41e4a-193">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41e4a-193">The following output appears.</span></span>

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="41e4a-194">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41e4a-194">See Also</span></span>

[<span data-ttu-id="41e4a-195">Hinzufügen von Parametern, die Command-Line Eingabe verarbeiten</span><span class="sxs-lookup"><span data-stu-id="41e4a-195">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

<span data-ttu-id="41e4a-196">[Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="41e4a-196">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="41e4a-197">[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="41e4a-197">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="41e4a-198">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="41e4a-198">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="41e4a-199">Cmdlet-Beispiele</span><span class="sxs-lookup"><span data-stu-id="41e4a-199">Cmdlet Samples</span></span>](./cmdlet-samples.md)
