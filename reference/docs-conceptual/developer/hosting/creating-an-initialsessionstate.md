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
# <a name="creating-an-initialsessionstate"></a>Erstellen von InitialSessionState

PowerShell-Befehle werden in einem Runspace ausgeführt.
Um PowerShell in Ihrer Anwendung zu hosten, müssen Sie ein [System. Management. Automation. Runspaces. Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) -Objekt erstellen.
Jedem Runspace ist ein [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt zugeordnet.
Initialsessionstate gibt die Merkmale des Runspace an, z. b. welche Befehle, Variablen und Module für diesen Runspace verfügbar sind.

## <a name="create-a-default-initialsessionstate"></a>Erstellen eines standardinitialsessionstate

Die Methoden "up- [default](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) " und " [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) " der Klasse " **initialsessionstate** " können zum Erstellen eines " **initialsessionstate** "-Objekts verwendet werden.
Die Methode " **samatedefault** " erstellt einen " **initialsessionstate** ", wobei alle integrierten Befehle geladen werden, während die **CreateDefault2** -Methode nur die Befehle lädt, die zum Hosten von PowerShell erforderlich sind (die Befehle aus dem Microsoft. PowerShell. Core-Modul).

Wenn Sie die in der Host Anwendung verfügbaren Befehle weiter einschränken möchten, müssen Sie einen eingeschränkten Runspace erstellen.
Weitere Informationen finden Sie unter [Erstellen eines eingeschränkten Runspace](creating-a-constrained-runspace.md).

Der folgende Code zeigt, wie Sie einen **initialsessionstate**erstellen, ihn einem Runspace zuweisen, der Pipeline in diesem Runspace Befehle hinzufügen und die Befehle aufrufen.
Weitere Informationen zum Hinzufügen und Aufrufen von Befehlen finden Sie unter [Hinzufügen und Aufrufen von Befehlen](adding-and-invoking-commands.md).

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

## <a name="see-also"></a>Weitere Informationen

[Erstellen eines eingeschränkten Runspaces](creating-a-constrained-runspace.md)

[Hinzufügen und Aufrufen von Befehlen](adding-and-invoking-commands.md)
