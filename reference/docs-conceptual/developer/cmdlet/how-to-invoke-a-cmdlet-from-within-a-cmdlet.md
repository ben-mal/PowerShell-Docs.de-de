---
title: Aufrufen eines Cmdlets innerhalb eines Cmdlets | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 2d5b0788d3310d0dd7b311f86c497afe8eec9d11
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784145"
---
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a>Aufrufen eines Cmdlet in einem Cmdlet

In diesem Beispiel wird gezeigt, wie ein Cmdlet aus einem anderen Cmdlet aufgerufen wird, mit dem Sie die Funktionalität des aufgerufenen Cmdlets zum Cmdlet hinzufügen können, das Sie entwickeln. In diesem Beispiel wird das- `Get-Process` Cmdlet aufgerufen, um die Prozesse zu erhalten, die auf dem lokalen Computer ausgeführt werden. Der `Get-Process` Cmdlet-Befehl entspricht dem folgenden Befehl. Dieser Befehl ruft alle Prozesse ab, deren Namen mit den Zeichen "a" bis "t" beginnen.

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> Sie können nur die Cmdlets aufrufen, die direkt von der [System. Management. Automation. Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) -Klasse abgeleitet werden. Sie können kein Cmdlet aufrufen, das von der [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) -Klasse abgeleitet wird.

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a>So rufen Sie ein Cmdlet innerhalb eines Cmdlets auf

1. Stellen Sie sicher, dass auf die Assembly, die das aufzurufende Cmdlet definiert, verwiesen wird und dass die entsprechende `using` Anweisung hinzugefügt wird. In diesem Beispiel werden die folgenden Namespaces hinzugefügt.

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. Erstellen Sie in der Eingabe Verarbeitungsmethode des Cmdlets eine neue Instanz des aufzurufenden Cmdlets. In diesem Beispiel wird ein Objekt vom Typ [Microsoft. PowerShell. Commands. getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) zusammen mit der Zeichenfolge erstellt, die die Argumente enthält, die beim Aufrufen des Cmdlets verwendet werden.

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. Rufen Sie die [System. Management. Automation. Cmdlet. aufrufen *](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) -Methode auf, um das `Get-Process` Cmdlet aufzurufen.

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a>Beispiel

In diesem Beispiel wird das `Get-Process` Cmdlet in der [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) -Methode eines Cmdlets aufgerufen.

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;   // Windows PowerShell assembly.
using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify an
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "GreetingInvoke")]
  public class SendGreetingInvokeCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the BeginProcessing method to invoke
    // the Get-Process cmdlet.
    protected override void BeginProcessing()
    {
      GetProcessCommand gp = new GetProcessCommand();
      gp.Name = new string[] { "[a-t]*" };
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
