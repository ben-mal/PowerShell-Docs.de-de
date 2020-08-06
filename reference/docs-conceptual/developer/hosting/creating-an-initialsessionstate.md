---
title: Erstellen eines initialsessionstate | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 946adf1006d1afcad2810c85e39f14514e837327
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779725"
---
# <a name="creating-an-initialsessionstate"></a><span data-ttu-id="f5ff9-102">Erstellen von InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="f5ff9-102">Creating an InitialSessionState</span></span>

<span data-ttu-id="f5ff9-103">PowerShell-Befehle werden in einem Runspace ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f5ff9-103">PowerShell commands run in a runspace.</span></span>
<span data-ttu-id="f5ff9-104">Um PowerShell in Ihrer Anwendung zu hosten, müssen Sie ein [System. Management. Automation. Runspaces. Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) -Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5ff9-104">To host PowerShell in your application, you must create a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>
<span data-ttu-id="f5ff9-105">Jedem Runspace ist ein [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f5ff9-105">Every runspace has an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object associated with it.</span></span>
<span data-ttu-id="f5ff9-106">Initialsessionstate gibt die Merkmale des Runspace an, z. b. welche Befehle, Variablen und Module für diesen Runspace verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f5ff9-106">The InitialSessionState specifies characteristics of the runspace, such as which commands, variables, and modules are available for that runspace.</span></span>

## <a name="create-a-default-initialsessionstate"></a><span data-ttu-id="f5ff9-107">Erstellen eines standardinitialsessionstate</span><span class="sxs-lookup"><span data-stu-id="f5ff9-107">Create a default InitialSessionState</span></span>

<span data-ttu-id="f5ff9-108">Die Methoden "up- [default](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) " und " [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) " der Klasse " **initialsessionstate** " können zum Erstellen eines " **initialsessionstate** "-Objekts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5ff9-108">The [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) and [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) methods of the **InitialSessionState** class can be used to create an **InitialSessionState** object.</span></span>
<span data-ttu-id="f5ff9-109">Die Methode " **samatedefault** " erstellt einen " **initialsessionstate** ", wobei alle integrierten Befehle geladen werden, während die **CreateDefault2** -Methode nur die Befehle lädt, die zum Hosten von PowerShell erforderlich sind (die Befehle aus dem Microsoft. PowerShell. Core-Modul).</span><span class="sxs-lookup"><span data-stu-id="f5ff9-109">The **CreateDefault** method creates an **InitialSessionState** with all of the built-in commands loaded, while the **CreateDefault2** method loads only the commands required to host PowerShell (the commands from the Microsoft.PowerShell.Core module).</span></span>

<span data-ttu-id="f5ff9-110">Wenn Sie die in der Host Anwendung verfügbaren Befehle weiter einschränken möchten, müssen Sie einen eingeschränkten Runspace erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5ff9-110">If you want to further limit the commands available in your host application you need to create a constrained runspace.</span></span>
<span data-ttu-id="f5ff9-111">Weitere Informationen finden Sie unter [Erstellen eines eingeschränkten Runspace](creating-a-constrained-runspace.md).</span><span class="sxs-lookup"><span data-stu-id="f5ff9-111">For information, see [Creating a constrained runspace](creating-a-constrained-runspace.md).</span></span>

<span data-ttu-id="f5ff9-112">Der folgende Code zeigt, wie Sie einen **initialsessionstate**erstellen, ihn einem Runspace zuweisen, der Pipeline in diesem Runspace Befehle hinzufügen und die Befehle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f5ff9-112">The following code shows how to create an **InitialSessionState**, assign it to a runspace, add commands to the pipeline in that runspace, and invoke the commands.</span></span>
<span data-ttu-id="f5ff9-113">Weitere Informationen zum Hinzufügen und Aufrufen von Befehlen finden Sie unter [Hinzufügen und Aufrufen von Befehlen](adding-and-invoking-commands.md).</span><span class="sxs-lookup"><span data-stu-id="f5ff9-113">For more information about adding and invoking commands, see [Adding and invoking commands](adding-and-invoking-commands.md).</span></span>

```csharp
namespace SampleHost
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  class HostP4b
  {
    static void Main(string[] args)
    {
      // Call the InitialSessionState.CreateDefault method to create
      // an empty InitialSessionState object, and then add the
      // elements that will be available when the runspace is opened.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      SessionStateVariableEntry var1 = new
          SessionStateVariableEntry("test1",
                                    "MyVar1",
                                    "Initial session state MyVar1 test");
      iss.Variables.Add(var1);

      SessionStateVariableEntry var2 = new
          SessionStateVariableEntry("test2",
                                    "MyVar2",
                                    "Initial session state MyVar2 test");
      iss.Variables.Add(var2);

      // Call the RunspaceFactory.CreateRunspace(InitialSessionState)
      // method to create the runspace where the pipeline is run.
      Runspace rs = RunspaceFactory.CreateRunspace(iss);
      rs.Open();

      // Call the PowerShell.Create() method to create the PowerShell object,
      // and then specify the runspace and commands to the pipeline.
      // and create the command pipeline.
      PowerShell ps = PowerShell.Create();
      ps.Runspace = rs;
      ps.AddCommand("Get-Variable");
      ps.AddArgument("test*");

      Console.WriteLine("Variable             Value");
      Console.WriteLine("--------------------------");

      // Call the PowerShell.Invoke() method to run
      // the pipeline synchronously.
      foreach (PSObject result in ps.Invoke())
      {
        Console.WriteLine("{0,-20}{1}",
            result.Members["Name"].Value,
            result.Members["Value"].Value);
      } // End foreach.

      // Close the runspace to free resources.
      rs.Close();

    } // End Main.
  } // End SampleHost.
}
```

## <a name="see-also"></a><span data-ttu-id="f5ff9-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5ff9-114">See Also</span></span>

[<span data-ttu-id="f5ff9-115">Erstellen eines eingeschränkten Runspaces</span><span class="sxs-lookup"><span data-stu-id="f5ff9-115">Creating a constrained runspace</span></span>](creating-a-constrained-runspace.md)

[<span data-ttu-id="f5ff9-116">Hinzufügen und Aufrufen von Befehlen</span><span class="sxs-lookup"><span data-stu-id="f5ff9-116">Adding and invoking commands</span></span>](adding-and-invoking-commands.md)
