---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace04-Beispiel
description: Runspace04-Beispiel
ms.openlocfilehash: 5a2e1137963e02def419bb924c63b0d651b0fdfa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657746"
---
# <a name="runspace04-sample"></a><span data-ttu-id="8210e-103">Runspace04-Beispiel</span><span class="sxs-lookup"><span data-stu-id="8210e-103">Runspace04 Sample</span></span>

<span data-ttu-id="8210e-104">Dieses Beispiel zeigt, wie Sie mit der [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Klasse Befehle ausführen und abschließende Fehler abfangen, die beim Ausführen der Befehle ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="8210e-104">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span> <span data-ttu-id="8210e-105">Zwei Befehle werden ausgeführt. An den letzten Befehl wird ein ungültiges Parameterargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="8210e-105">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span> <span data-ttu-id="8210e-106">Daher werden keine Objekte zurückgegeben, und ein Fehler mit Abbruch wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8210e-106">As a result, no objects are returned and a terminating error is thrown.</span></span>

## <a name="requirements"></a><span data-ttu-id="8210e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8210e-107">Requirements</span></span>

<span data-ttu-id="8210e-108">Dieses Beispiel erfordert Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="8210e-108">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="8210e-109">Zeigt</span><span class="sxs-lookup"><span data-stu-id="8210e-109">Demonstrates</span></span>

<span data-ttu-id="8210e-110">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="8210e-110">This sample demonstrates the following.</span></span>

- <span data-ttu-id="8210e-111">Ein [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="8210e-111">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="8210e-112">Hinzufügen von Befehlen zur Pipeline des [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="8210e-112">Adding commands to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="8210e-113">Hinzufügen von Parameter Argumenten zur Pipeline.</span><span class="sxs-lookup"><span data-stu-id="8210e-113">Adding parameter arguments to the pipeline.</span></span>

- <span data-ttu-id="8210e-114">Synchrones Aufrufen der Befehle.</span><span class="sxs-lookup"><span data-stu-id="8210e-114">Invoking the commands synchronously.</span></span>

- <span data-ttu-id="8210e-115">Verwenden von [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten zum Extrahieren und Anzeigen von Eigenschaften aus den Objekten, die von den Befehlen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8210e-115">Using [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects to extract and display properties from the objects returned by the commands.</span></span>

- <span data-ttu-id="8210e-116">Abrufen und Anzeigen von Fehler Datensätzen, die während der Ausführung der Befehle generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8210e-116">Retrieving and displaying error records that were generated during the running of the commands.</span></span>

- <span data-ttu-id="8210e-117">Abfangen und Anzeigen von abschließenden Ausnahmen, die von den Befehlen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="8210e-117">Catching and displaying terminating exceptions thrown by the commands.</span></span>

## <a name="example"></a><span data-ttu-id="8210e-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8210e-118">Example</span></span>

<span data-ttu-id="8210e-119">Dieses Beispiel führt Befehle synchron im von Windows PowerShell bereitgestellten standardrunspace aus.</span><span class="sxs-lookup"><span data-stu-id="8210e-119">This sample runs commands synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="8210e-120">Mit dem letzten Befehl wird ein Beendigungs Fehler ausgelöst, da ein ungültiges Parameter Argument an den Befehl übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="8210e-120">The last command throws a terminating error because a parameter argument that is not valid is passed to the command.</span></span> <span data-ttu-id="8210e-121">Der abschließende Fehler wird aufgefangen und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8210e-121">The terminating error is trapped and displayed.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace04
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands.
    /// The commands generate a terminating exception that the caller
    /// should catch and process.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run commands.
    /// 2. Adding commands to the pipeline of  the PowerShell object.
    /// 3. Passing input objects to the commands from the calling program.
    /// 4. Using PSObject objects to extract and display properties from the
    ///    objects returned by the commands.
    /// 5. Retrieving and displaying error records that were generated
    ///    while running the commands.
    /// 6. Catching and displaying terminating exceptions generated
    ///    while running the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object.
      using (PowerShell powershell = PowerShell.Create())
      {
        // Add the commands to the PowerShell object.
        powershell.AddCommand("Get-ChildItem").AddCommand("Select-String").AddArgument("*");

        // Run the commands synchronously. Because of the bad regular expression,
        // no objects will be returned. Instead, an exception will be thrown.
        try
        {
          foreach (PSObject result in powershell.Invoke())
          {
            Console.WriteLine("'{0}'", result.ToString());
          }

          // Process any error records that were generated while running the commands.
          Console.WriteLine("\nThe following non-terminating errors occurred:\n");
          PSDataCollection<ErrorRecord> errors = powershell.Streams.Error;
          if (errors != null && errors.Count > 0)
          {
            foreach (ErrorRecord err in errors)
            {
              System.Console.WriteLine("    error: {0}", err.ToString());
            }
          }
        }
        catch (RuntimeException runtimeException)
        {
          // Trap any exception generated by the commands. These exceptions
          // will all be derived from the RuntimeException exception.
          System.Console.WriteLine(
                        "Runtime exception: {0}: {1}\n{2}",
                        runtimeException.ErrorRecord.InvocationInfo.InvocationName,
                        runtimeException.Message,
                        runtimeException.ErrorRecord.InvocationInfo.PositionMessage);
        }
      }

      System.Console.WriteLine("\nHit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="8210e-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8210e-122">See Also</span></span>

[<span data-ttu-id="8210e-123">Schreiben einer Windows PowerShell-Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="8210e-123">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
