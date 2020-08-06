---
title: Erstellen eines eingeschränkten Runspace | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 30ecb80dbd96278ee9aa5a609d27bfc4eaa423e9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779810"
---
# <a name="creating-a-constrained-runspace"></a>Erstellen eines eingeschränkten Runspaces

Aus Leistungs-oder Sicherheitsgründen möchten Sie möglicherweise die Windows PowerShell-Befehle einschränken, die für die Host Anwendung verfügbar sind. Zu diesem Zweck erstellen Sie eine leere [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) , indem Sie den [System.Management.Automation.Runspaces.Initialsessionstate aufrufen. Create *](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) -Methode, und fügen Sie dann nur die Befehle hinzu, die Sie verfügbar machen möchten.

 Wenn Sie einen Runspace verwenden, der nur die von Ihnen angegebenen Befehle lädt, wird die Leistung erheblich verbessert.

 Verwenden Sie die Methoden der [System. Management. Automation. Runspaces. sessionstatecmdletentry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) -Klasse, um Cmdlets für den anfänglichen Sitzungs Status zu definieren.

 Sie können auch die Befehle als privat festlegen. Private Befehle können von der Host Anwendung, jedoch nicht von Benutzern der Anwendung verwendet werden.

## <a name="adding-commands-to-an-empty-runspace"></a>Hinzufügen von Befehlen zu einem leeren Runspace

 Im folgenden Beispiel wird veranschaulicht, wie ein leerer initialsessionstate erstellt und ihm Befehle hinzugefügt werden.

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using Microsoft.PowerShell.Commands;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for the application.
  /// </summary>
  internal class Runspace10b
  {
    /// <summary>
    /// This sample shows how to create an empty initial session state,
    /// how to add commands to the session state, and then how to create a
    /// runspace that has only those two commands. A PowerShell object
    /// is used to run the Get-Command cmdlet to show that only two commands
    /// are available.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    private static void Main(string[] args)
    {
      // Create an empty InitialSessionState and then add two commands.
      InitialSessionState iss = InitialSessionState.Create();

      // Add the Get-Process and Get-Command cmdlets to the session state.
      SessionStateCmdletEntry ssce1 = new SessionStateCmdletEntry(
                                                            "get-process",
                                                            typeof(GetProcessCommand),
                                                            null);
      iss.Commands.Add(ssce1);

      SessionStateCmdletEntry ssce2 = new SessionStateCmdletEntry(
                                                            "get-command",
                                                            typeof(GetCommandCommand),
                                                            null);
      iss.Commands.Add(ssce2);

      // Create a runspace.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();
        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = myRunSpace;

          // Create a pipeline with the Get-Command command.
          powershell.AddCommand("get-command");

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Verb                 Noun");
          Console.WriteLine("----------------------------");

          // Display each result object.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                             "{0,-20} {1}",
                             result.Members["verb"].Value,
                             result.Members["Noun"].Value);
          }
        }

        // Close the runspace and release any resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="making-commands-private"></a>Erstellen von Befehlen als privat

 Sie können einen Befehl auch als privat festlegen, indem Sie die [System. Management. Automation. CommandInfo. Visibility](/dotnet/api/System.Management.Automation.CommandInfo.Visibility) -Eigenschaft von System. Management [. Automation. sessionstateentryvisibility](/dotnet/api/System.Management.Automation.SessionStateEntryVisibility) **private**festlegen. Die Host Anwendung und andere Befehle können diesen Befehl abrufen, der Benutzer der Anwendung jedoch nicht. Im folgenden Beispiel ist der Befehl [Get-ChildItem](/powershell/module/Microsoft.PowerShell.Management/Get-ChildItem) privat.

```csharp
defaultSessionState = InitialSessionState.CreateDefault();
commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
defaultSessionState.Commands[commandIndex].Visibility = SessionStateEntryVisibility.Private;

this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
this.runspace.Open();
```

## <a name="see-also"></a>Weitere Informationen

 [Erstellen von InitialSessionState](./creating-an-initialsessionstate.md)
