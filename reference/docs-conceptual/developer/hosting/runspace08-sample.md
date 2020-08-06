---
title: Runspace08-Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4fcf58eceb415f9f02391c22d2719e9140c77ea9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783159"
---
# <a name="runspace08-sample"></a><span data-ttu-id="75e1d-102">Runspace08-Beispiel</span><span class="sxs-lookup"><span data-stu-id="75e1d-102">Runspace08 Sample</span></span>

<span data-ttu-id="75e1d-103">In diesem Beispiel wird gezeigt, wie der Pipeline eines [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts Befehle und Argumente hinzugefügt werden und wie die Befehle synchron ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="75e1d-103">This sample shows how to add commands and arguments to the pipeline of a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object and how to run the commands synchronously.</span></span>

## <a name="requirements"></a><span data-ttu-id="75e1d-104">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="75e1d-104">Requirements</span></span>

<span data-ttu-id="75e1d-105">Dieses Beispiel erfordert Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="75e1d-105">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="75e1d-106">Zeigt</span><span class="sxs-lookup"><span data-stu-id="75e1d-106">Demonstrates</span></span>

<span data-ttu-id="75e1d-107">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="75e1d-107">This sample demonstrates the following.</span></span>

- <span data-ttu-id="75e1d-108">Erstellen eines [System. Management. Automation. Runspaces. Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) -Objekts mithilfe der [System. Management. Automation. Runspaces. runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="75e1d-108">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object by using the [System.Management.Automation.Runspaces.Runspacefactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) class.</span></span>

- <span data-ttu-id="75e1d-109">Erstellen eines [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts, das den Runspace verwendet.</span><span class="sxs-lookup"><span data-stu-id="75e1d-109">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="75e1d-110">Hinzufügen von Cmdlets zur Pipeline des [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="75e1d-110">Adding cmdlets to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="75e1d-111">Synchrones Ausführen der Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="75e1d-111">Running the cmdlets synchronously.</span></span>

- <span data-ttu-id="75e1d-112">Extrahieren von Eigenschaften aus den [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten, die vom Befehl zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="75e1d-112">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="75e1d-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75e1d-113">Example</span></span>

<span data-ttu-id="75e1d-114">In diesem Beispiel werden die Cmdlets " [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) " und " [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) " mithilfe eines [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="75e1d-114">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.Generic;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace08
  {
    /// <summary>
    /// This sample shows how to use a PowerShell object to run commands. The
    /// PowerShell object builds a pipeline that include the get-process cmdlet,
    /// which is then piped to the sort-object cmdlet. Parameters are added to the
    /// sort-object cmdlet to sort the HandleCount property in descending order.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates:
    /// 1. Creating a PowerShell object
    /// 2. Adding individual commands to the PowerShell object.
    /// 3. Adding parameters to the commands.
    /// 4. Running the pipeline of the PowerShell object synchronously.
    /// 5. Working with PSObject objects to extract properties
    ///    from the objects returned by the commands.
    /// </remarks>
    private static void Main(string[] args)
    {
      Collection<PSObject> results; // Holds the result of the pipeline execution.

      // Create the PowerShell object. Notice that no runspace is specified so a
      // new default runspace is used.
      PowerShell powershell = PowerShell.Create();

      // Use the using statement so that we can dispose of the PowerShell object
      // when we are done.
      using (powershell)
      {
        // Add the get-process cmdlet to the pipeline of the PowerShell object.
        powershell.AddCommand("get-process");

        // Add the sort-object cmdlet and its parameters to the pipeline of
        // the PowerShell object so that we can sort the HandleCount property
        //  in descending order.
        powershell.AddCommand("sort-object").AddParameter("descending").AddParameter("property", "handlecount");

        // Run the commands of the pipeline synchronously.
        results = powershell.Invoke();
      }

      // Even after disposing of the PowerShell object, we still
      // need to set the powershell variable to null so that the
      // garbage collector can clean it up.
      powershell = null;

      Console.WriteLine("Process              HandleCount");
      Console.WriteLine("--------------------------------");

      // Display the results returned by the commands.
      foreach (PSObject result in results)
      {
        Console.WriteLine(
                          "{0,-20} {1}",
                          result.Members["ProcessName"].Value,
                          result.Members["HandleCount"].Value);
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="75e1d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75e1d-115">See Also</span></span>

[<span data-ttu-id="75e1d-116">Schreiben einer Windows PowerShell-Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="75e1d-116">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
