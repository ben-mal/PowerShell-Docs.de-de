---
title: Erstellen von Remoterunspaces | Microsoft-Dokumentation
ms.date: 09/12/2016
ms.openlocfilehash: 2b3c76eeae70de9ef116851313953bba1a1d890f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779589"
---
# <a name="creating-remote-runspaces"></a>Erstellen von Remoterunspaces

PowerShell-Befehle, die einen **Computername** -Parameter annehmen, können auf jedem Computer ausgeführt werden, auf dem PowerShell ausgeführt wird. Zum Ausführen von Befehlen, die keinen **Computername** -Parameter verwenden, können Sie die WS-Verwaltung verwenden, um einen Runspace zu konfigurieren, der eine Verbindung mit einem angegebenen Computer herstellt, und Befehle auf diesem Computer auszuführen.

## <a name="using-a-wsmanconnection-to-create-a-remote-runspace"></a>Verwenden von wsmanconnection zum Erstellen eines Remoterunspace

 Um einen Runspace zu erstellen, der eine Verbindung mit einem Remote Computer herstellt, erstellen Sie ein [System. Management. Automation. Runspaces. wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) -Objekt. Sie geben den Ziel Endpunkt für die Verbindung an, indem Sie die [System. Management. Automation. Runspaces. wsmanconnectioninfo. ConnectionUri](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo.ConnectionUri) -Eigenschaft des-Objekts festlegen. Anschließend erstellen Sie einen Runspace, indem Sie die [System. Management. Automation. Runspaces. runspacefactory. createrunspace](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory.CreateRunspace) -Methode aufrufen und das [System. Management. Automation. Runspaces. wsmanconnectioninfo](/dotnet/api/System.Management.Automation.Runspaces.WSManConnectionInfo) -Objekt als `connectionInfo` Parameter angeben.

 Im folgenden Beispiel wird gezeigt, wie ein Runspace erstellt wird, der eine Verbindung mit einem Remote Computer herstellt. Im Beispiel `RemoteComputerUri` wird als Platzhalter für den tatsächlichen URI eines Remote Computers verwendet.

```csharp
namespace Samples
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;            // PowerShell namespace.
  using System.Management.Automation.Runspaces;  // PowerShell namespace.

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class RemoteRunspace02
  {
    /// <summary>
    /// This sample shows how to create a remote runspace that
    /// runs commands on the local computer.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    private static void Main(string[] args)
    {
      // Create a WSManConnectionInfo object using the default constructor
      // to connect to the "localHost". The WSManConnectionInfo object can
      // also be used to specify connections to remote computers.
      Uri RemoteComputerUri = new Uri("http://Server01:5985/WSMAN");
      WSManConnectionInfo connectionInfo = new WSManConnectionInfo(RemoteComputerUri);

      // Set the OperationTimeout property and OpenTimeout properties.
      // The OperationTimeout property is used to tell PowerShell
      // how long to wait (in milliseconds) before timing out for an
      // operation. The OpenTimeout property is used to tell Windows
      // PowerShell how long to wait (in milliseconds) before timing out
      // while establishing a remote connection.
      connectionInfo.OperationTimeout = 4 * 60 * 1000; // 4 minutes.
      connectionInfo.OpenTimeout = 1 * 60 * 1000; // 1 minute.

      // Create a remote runspace using the connection information.
      //using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace())
      using (Runspace remoteRunspace = RunspaceFactory.CreateRunspace(connectionInfo))
      {
        // Establish the connection by calling the Open() method to open the runspace.
        // The OpenTimeout value set previously will be applied while establishing
        // the connection. Establishing a remote connection involves sending and
        // receiving some data, so the OperationTimeout will also play a role in this process.
          remoteRunspace.Open();

        // Create a PowerShell object to run commands in the remote runspace.
        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = remoteRunspace;
          powershell.AddCommand("get-process");
          powershell.Invoke();

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the results.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                              "{0,-20} {1}",
                              result.Members["ProcessName"].Value,
                              result.Members["HandleCount"].Value);
          }
        }

        // Close the connection. Call the Close() method to close the remote
        // runspace. The Dispose() method (called by using primitive) will call
        // the Close() method if it is not already called.
        remoteRunspace.Close();
      }
    }
  }
}
```
