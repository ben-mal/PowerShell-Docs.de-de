---
title: Runspace02-Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 7a2dce436aceb1d8744377c37671a66398614851
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784961"
---
# <a name="runspace02-sample"></a><span data-ttu-id="17252-102">Runspace02-Beispiel</span><span class="sxs-lookup"><span data-stu-id="17252-102">Runspace02 Sample</span></span>

<span data-ttu-id="17252-103">In diesem Beispiel wird gezeigt, wie die [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Klasse zum synchronen Ausführen der Cmdlets " [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) " und " [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) " verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="17252-103">This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously.</span></span> <span data-ttu-id="17252-104">Das [Get-Process-](/powershell/module/Microsoft.PowerShell.Management/Get-Process) Cmdlet gibt [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekte für jeden Prozess zurück, der auf dem lokalen Computer ausgeführt wird, und `Sort-Object` sortiert die Objekte basierend auf Ihrer [System.Diagnostics.Process.ID \*](/dotnet/api/System.Diagnostics.Process.Id) -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="17252-104">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects for each process running on the local computer, and the `Sort-Object` sorts the objects based on their [System.Diagnostics.Process.Id\*](/dotnet/api/System.Diagnostics.Process.Id) property.</span></span> <span data-ttu-id="17252-105">Die Ergebnisse dieser Befehle werden mithilfe eines [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) -Steuer Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="17252-105">The results of these commands is displayed by using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

## <a name="requirements"></a><span data-ttu-id="17252-106">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="17252-106">Requirements</span></span>

<span data-ttu-id="17252-107">Dieses Beispiel erfordert Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="17252-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="17252-108">Zeigt</span><span class="sxs-lookup"><span data-stu-id="17252-108">Demonstrates</span></span>

<span data-ttu-id="17252-109">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="17252-109">This sample demonstrates the following.</span></span>

- <span data-ttu-id="17252-110">Erstellen eines [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts zum Ausführen von Befehlen.</span><span class="sxs-lookup"><span data-stu-id="17252-110">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object to run commands.</span></span>

- <span data-ttu-id="17252-111">Hinzufügen von Befehlen zur Pipeline des [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="17252-111">Adding commands to the pipeline of [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="17252-112">Synchrones Ausführen der Befehle.</span><span class="sxs-lookup"><span data-stu-id="17252-112">Running the commands synchronously.</span></span>

- <span data-ttu-id="17252-113">Verwenden eines [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) -Steuer Elements, um die Ausgabe der Befehle in einer Windows Forms Anwendung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="17252-113">Using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control to display the output of the commands in a Windows Forms application.</span></span>

## <a name="example"></a><span data-ttu-id="17252-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17252-114">Example</span></span>

<span data-ttu-id="17252-115">In diesem Beispiel [werden die Get-Process-](/powershell/module/Microsoft.PowerShell.Management/Get-Process) und [Sort-Object-](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) Cmdlets synchron im Standard-Runspace von Windows PowerShell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="17252-115">This sample runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously in the default runspace provided by Windows PowerShell.</span></span> <span data-ttu-id="17252-116">Die Ausgabe wird in einem Formular mithilfe eines [System. Windows. Forms. DataGridView](/dotnet/api/System.Windows.Forms.DataGridView) -Steuer Elements angezeigt.</span><span class="sxs-lookup"><span data-stu-id="17252-116">The output is displayed in a form using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using System.Windows.Forms;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace02
  {
    /// <summary>
    /// This method creates the form where the output is displayed.
    /// </summary>
    private static void CreateForm()
    {
      Form form = new Form();
      DataGridView grid = new DataGridView();
      form.Controls.Add(grid);
      grid.Dock = DockStyle.Fill;

      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create())
      {
        powershell.AddCommand("get-process").AddCommand("sort-object").AddArgument("ID");
        if (Runspace.DefaultRunspace == null)
        {
          Runspace.DefaultRunspace = powershell.Runspace;
        }

        Collection<PSObject> results = powershell.Invoke();

        // The generic collection needs to be re-wrapped in an ArrayList
        // for data-binding to work.
        ArrayList objects = new ArrayList();
        objects.AddRange(results);

        // The DataGridView will use the PSObjectTypeDescriptor type
        // to retrieve the properties.
        grid.DataSource = objects;
      }

      form.ShowDialog();
    }

    /// <summary>
    /// This sample uses a PowerShell object to run the Get-Process
    /// and Sort-Object cmdlets synchronously. Windows Forms and
    /// data binding are then used to display the results in a
    /// DataGridView control.
    /// </summary>
    /// <param name="args">The parameter is not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object.
    /// 2. Adding commands and arguments to the pipeline of
    ///    the PowerShell object.
    /// 3. Running the commands synchronously.
    /// 4. Using a DataGridView control to display the output
    ///    of the commands in a Windows Forms application.
    /// </remarks>
    private static void Main(string[] args)
    {
      Runspace02.CreateForm();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="17252-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17252-117">See Also</span></span>

[<span data-ttu-id="17252-118">Schreiben einer Windows PowerShell-Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="17252-118">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
