---
ms.date: 09/13/2016
ms.topic: reference
title: Hinzufügen und Aufrufen von Befehlen
description: Hinzufügen und Aufrufen von Befehlen
ms.openlocfilehash: f539172eaf119fe5774e158c77a00276c8ba9e0a
ms.sourcegitcommit: 880b00218708724a76503000c9eca181f4e00891
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "99049424"
---
# <a name="adding-and-invoking-commands"></a><span data-ttu-id="084dd-103">Hinzufügen und Aufrufen von Befehlen</span><span class="sxs-lookup"><span data-stu-id="084dd-103">Adding and invoking commands</span></span>

<span data-ttu-id="084dd-104">Nachdem Sie einen Runspace erstellt haben, können Sie Windows powershellcommands und Skripts zu einer Pipeline hinzufügen und die Pipeline dann synchron oder asynchron aufrufen.</span><span class="sxs-lookup"><span data-stu-id="084dd-104">After creating a runspace, you can add Windows PowerShellcommands and scripts to a pipeline, and then invoke the pipeline synchronously or asynchronously.</span></span>

## <a name="creating-a-pipeline"></a><span data-ttu-id="084dd-105">Erstellen einer Pipeline</span><span class="sxs-lookup"><span data-stu-id="084dd-105">Creating a pipeline</span></span>

<span data-ttu-id="084dd-106">Die [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Klasse bietet mehrere Methoden zum Hinzufügen von Befehlen, Parametern und Skripts zur Pipeline.</span><span class="sxs-lookup"><span data-stu-id="084dd-106">The [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class provides several methods to add commands, parameters, and scripts to the pipeline.</span></span> <span data-ttu-id="084dd-107">Sie können die Pipeline synchron aufrufen, indem Sie eine Überladung der [System. Management. Automation. PowerShell. Call \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) -Methode aufrufen, oder asynchron durch Aufrufen einer Überladung von [System. Management. Automation. PowerShell. beginCall \*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) und der [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) -Methode.</span><span class="sxs-lookup"><span data-stu-id="084dd-107">You can invoke the pipeline synchronously by calling an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, or asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) and then the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

### <a name="addcommand"></a><span data-ttu-id="084dd-108">AddCommand</span><span class="sxs-lookup"><span data-stu-id="084dd-108">AddCommand</span></span>

1. <span data-ttu-id="084dd-109">Erstellen Sie ein [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="084dd-109">Create a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="084dd-110">Fügen Sie den Befehl hinzu, den Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="084dd-110">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="084dd-111">Rufen Sie den Befehl auf.</span><span class="sxs-lookup"><span data-stu-id="084dd-111">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

<span data-ttu-id="084dd-112">Wenn Sie die [System. Management. Automation. PowerShell. AddCommand \*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) -Methode mehrmals aufrufen, bevor Sie die [System. Management. Automation. PowerShell. Call\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) -Methode aufrufen, wird das Ergebnis des ersten Befehls an die zweite weitergeleitet usw.</span><span class="sxs-lookup"><span data-stu-id="084dd-112">If you call the [System.Management.Automation.Powershell.Addcommand\*](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method more than once before you call the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span> <span data-ttu-id="084dd-113">Wenn Sie das Ergebnis eines vorherigen Befehls nicht an einen Befehl übergeben möchten, fügen Sie es hinzu, indem Sie stattdessen die [System. Management. Automation. PowerShell. addstatement \*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="084dd-113">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="084dd-114">AddParameter</span><span class="sxs-lookup"><span data-stu-id="084dd-114">AddParameter</span></span>

 <span data-ttu-id="084dd-115">Das vorherige Beispiel führt einen einzelnen Befehl ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="084dd-115">The previous example executes a single command without any parameters.</span></span> <span data-ttu-id="084dd-116">Sie können dem Befehl mithilfe der [System. Management. Automation. PSCommand. AddParameter \*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) -Methode Parameter hinzufügen. der folgende Code ruft beispielsweise eine Liste aller Prozesse ab, die `PowerShell` auf dem Computer mit dem Namen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="084dd-116">You can add parameters to the command by using the [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

<span data-ttu-id="084dd-117">Sie können zusätzliche Parameter hinzufügen, indem Sie [System. Management. Automation. PSCommand. AddParameter \*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) wiederholt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="084dd-117">You can add additional parameters by calling [System.Management.Automation.Pscommand.Addparameter\*](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) repeatedly.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Command")
                   .AddParameter("Name", "Get-VM")
                   .AddParameter("Module", "Hyper-V")
                   .Invoke();
```

<span data-ttu-id="084dd-118">Sie können auch ein Wörterbuch mit Parameternamen und-Werten hinzufügen, indem Sie die [System. Management. Automation. PowerShell. AddParameters \*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="084dd-118">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.Powershell.Addparameters\*](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Name", "Get-VM");

parameters.Add("Module", "Hyper-V");
PowerShell.Create().AddCommand("Get-Command")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="084dd-119">Addstatement</span><span class="sxs-lookup"><span data-stu-id="084dd-119">AddStatement</span></span>

<span data-ttu-id="084dd-120">Sie können die Batch Verarbeitung simulieren, indem Sie die [System. Management. Automation. PowerShell. addstatement \*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) -Methode verwenden, mit der am Ende der Pipeline eine zusätzliche Anweisung hinzugefügt wird. der folgende Code Ruft eine Liste der ausgelaufenden Prozesse mit dem Namen ab `PowerShell` und ruft dann die Liste der ausgelaufenden Dienste ab.</span><span class="sxs-lookup"><span data-stu-id="084dd-120">You can simulate batching by using the [System.Management.Automation.Powershell.Addstatement\*](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="084dd-121">AddScript</span><span class="sxs-lookup"><span data-stu-id="084dd-121">AddScript</span></span>

<span data-ttu-id="084dd-122">Sie können ein vorhandenes Skript ausführen, indem Sie die [System. Management. Automation. PowerShell. addScript \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="084dd-122">You can run an existing script by calling the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span> <span data-ttu-id="084dd-123">Das folgende Beispiel fügt der Pipeline ein Skript hinzu und führt es aus.</span><span class="sxs-lookup"><span data-stu-id="084dd-123">The following example adds a script to the pipeline and runs it.</span></span> <span data-ttu-id="084dd-124">In diesem Beispiel wird davon ausgegangen, dass bereits ein Skript namens `MyScript.ps1` in einem Ordner namens vorhanden ist `D:\PSScripts` .</span><span class="sxs-lookup"><span data-stu-id="084dd-124">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(File.ReadAllText(@"D:\PSScripts\MyScript.ps1")).Invoke();
```

<span data-ttu-id="084dd-125">Es gibt auch eine Version der [System. Management. Automation. PowerShell. addScript \*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) -Methode, die einen booleschen Parameter namens annimmt `useLocalScope` .</span><span class="sxs-lookup"><span data-stu-id="084dd-125">There is also a version of the [System.Management.Automation.Powershell.Addscript\*](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method that takes a boolean parameter named `useLocalScope`.</span></span> <span data-ttu-id="084dd-126">Wenn dieser Parameter auf festgelegt ist `true` , wird das Skript im lokalen Gültigkeitsbereich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="084dd-126">If this parameter is set to `true`, then the script is run in the local scope.</span></span> <span data-ttu-id="084dd-127">Mit dem folgenden Code wird das Skript im lokalen Gültigkeitsbereich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="084dd-127">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(File.ReadAllText(@"D:\PSScripts\MyScript.ps1"), true).Invoke();
```

### <a name="invoking-a-pipeline-synchronously"></a><span data-ttu-id="084dd-128">Synchrones Aufrufen einer Pipeline</span><span class="sxs-lookup"><span data-stu-id="084dd-128">Invoking a pipeline synchronously</span></span>

<span data-ttu-id="084dd-129">Nachdem Sie der Pipeline Elemente hinzugefügt haben, rufen Sie Sie auf.</span><span class="sxs-lookup"><span data-stu-id="084dd-129">After you add elements to the pipeline, you invoke it.</span></span> <span data-ttu-id="084dd-130">Um die Pipeline synchron aufzurufen, rufen Sie eine Überladung der [System. Management. Automation. PowerShell. aufrufen \*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="084dd-130">To invoke the pipeline synchronously, you call an overload of the [System.Management.Automation.Powershell.Invoke\*](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method.</span></span> <span data-ttu-id="084dd-131">Im folgenden Beispiel wird gezeigt, wie eine Pipeline synchron aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="084dd-131">The following example shows how to synchronously invoke a pipeline.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS1e
{
  class HostPS1e
  {
    static void Main(string[] args)
    {
      // Using the PowerShell.Create and AddCommand
      // methods, create a command pipeline.
      PowerShell ps = PowerShell.Create().AddCommand ("Sort-Object");

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the supplied input.
      foreach (PSObject result in ps.Invoke(new int[] { 3, 1, 6, 2, 5, 4 }))
      {
          Console.WriteLine("{0}", result);
      } // End foreach.
    } // End Main.
  } // End HostPS1e.
}
```

### <a name="invoking-a-pipeline-asynchronously"></a><span data-ttu-id="084dd-132">Asynchrones Aufrufen einer Pipeline</span><span class="sxs-lookup"><span data-stu-id="084dd-132">Invoking a pipeline asynchronously</span></span>

<span data-ttu-id="084dd-133">Sie rufen eine Pipeline asynchron auf, indem Sie eine Überladung von [System. Management. Automation. PowerShell. beginCall \*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) aufrufen, um ein [IAsyncResult](/dotnet/api/system.iasyncresult) -Objekt zu erstellen, und dann die [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) -Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="084dd-133">You invoke a pipeline asynchronously by calling an overload of the [System.Management.Automation.Powershell.Begininvoke\*](/dotnet/api/System.Management.Automation.PowerShell.BeginInvoke) to create an [IAsyncResult](/dotnet/api/system.iasyncresult) object, and then calling the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

 <span data-ttu-id="084dd-134">Im folgenden Beispiel wird gezeigt, wie eine Pipeline asynchron aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="084dd-134">The following example shows how to invoke a pipeline asynchronously.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;

namespace HostPS3
{
  class HostPS3
  {
    static void Main(string[] args)
    {
      // Use the PowerShell.Create and PowerShell.AddCommand
      // methods to create a command pipeline that includes
      // Get-Process cmdlet. Do not include spaces immediately
      // before or after the cmdlet name as that will cause
      // the command to fail.
      PowerShell ps = PowerShell.Create().AddCommand("Get-Process");

      // Create an IAsyncResult object and call the
      // BeginInvoke method to start running the
      // command pipeline asynchronously.
      IAsyncResult asyncpl = ps.BeginInvoke();

      // Using the PowerShell.Invoke method, run the command
      // pipeline using the default runspace.
      foreach (PSObject result in ps.EndInvoke(asyncpl))
      {
        Console.WriteLine("{0,-20}{1}",
                result.Members["ProcessName"].Value,
                result.Members["Id"].Value);
      } // End foreach.
      System.Console.WriteLine("Hit any key to exit.");
      System.Console.ReadKey();
    } // End Main.
  } // End HostPS3.
}
```

## <a name="see-also"></a><span data-ttu-id="084dd-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="084dd-135">See Also</span></span>

 [<span data-ttu-id="084dd-136">Erstellen von InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="084dd-136">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

 [<span data-ttu-id="084dd-137">Erstellen eines eingeschränkten Runspaces</span><span class="sxs-lookup"><span data-stu-id="084dd-137">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)
