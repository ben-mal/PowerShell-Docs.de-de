---
ms.date: 09/13/2016
ms.topic: reference
title: Aufrufen eines Cmdlet in einem Cmdlet
description: Aufrufen eines Cmdlet in einem Cmdlet
ms.openlocfilehash: d137ac895f66000329de76a2c16a74b02c0e82ca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667044"
---
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="3bf66-103">Aufrufen eines Cmdlet in einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3bf66-103">How to Invoke a Cmdlet from Within a Cmdlet</span></span>

<span data-ttu-id="3bf66-104">In diesem Beispiel wird gezeigt, wie ein Cmdlet aus einem anderen Cmdlet aufgerufen wird, mit dem Sie die Funktionalität des aufgerufenen Cmdlets zum Cmdlet hinzufügen können, das Sie entwickeln.</span><span class="sxs-lookup"><span data-stu-id="3bf66-104">This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span> <span data-ttu-id="3bf66-105">In diesem Beispiel wird das- `Get-Process` Cmdlet aufgerufen, um die Prozesse zu erhalten, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3bf66-105">In this example, the `Get-Process` cmdlet is invoked to get the processes that are running on the local computer.</span></span> <span data-ttu-id="3bf66-106">Der `Get-Process` Cmdlet-Befehl entspricht dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="3bf66-106">The call to the `Get-Process` cmdlet is equivalent to the following command.</span></span> <span data-ttu-id="3bf66-107">Dieser Befehl ruft alle Prozesse ab, deren Namen mit den Zeichen "a" bis "t" beginnen.</span><span class="sxs-lookup"><span data-stu-id="3bf66-107">This command retrieves all the processes whose names start with the characters "a" through "t".</span></span>

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> <span data-ttu-id="3bf66-108">Sie können nur die Cmdlets aufrufen, die direkt von der [System. Management. Automation. Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3bf66-108">You can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="3bf66-109">Sie können kein Cmdlet aufrufen, das von der [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="3bf66-109">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="3bf66-110">So rufen Sie ein Cmdlet innerhalb eines Cmdlets auf</span><span class="sxs-lookup"><span data-stu-id="3bf66-110">To invoke a cmdlet from within a cmdlet</span></span>

1. <span data-ttu-id="3bf66-111">Stellen Sie sicher, dass auf die Assembly, die das aufzurufende Cmdlet definiert, verwiesen wird und dass die entsprechende `using` Anweisung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3bf66-111">Ensure that the assembly that defines the cmdlet to be invoked is referenced and that the appropriate `using` statement is added.</span></span> <span data-ttu-id="3bf66-112">In diesem Beispiel werden die folgenden Namespaces hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3bf66-112">In this example, the following namespaces are added.</span></span>

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. <span data-ttu-id="3bf66-113">Erstellen Sie in der Eingabe Verarbeitungsmethode des Cmdlets eine neue Instanz des aufzurufenden Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3bf66-113">In the input processing method of the cmdlet, create a new instance of the cmdlet to be invoked.</span></span> <span data-ttu-id="3bf66-114">In diesem Beispiel wird ein Objekt vom Typ [Microsoft. PowerShell. Commands. getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) zusammen mit der Zeichenfolge erstellt, die die Argumente enthält, die beim Aufrufen des Cmdlets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3bf66-114">In this example, an object of type [Microsoft.PowerShell.Commands.Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) is created along with the string that contains the arguments that are used when the cmdlet is invoked.</span></span>

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. <span data-ttu-id="3bf66-115">Rufen Sie die [System. Management. Automation. Cmdlet. aufrufen \*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) -Methode auf, um das `Get-Process` Cmdlet aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="3bf66-115">Call the [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method to invoke the `Get-Process` cmdlet.</span></span>

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a><span data-ttu-id="3bf66-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3bf66-116">Example</span></span>

<span data-ttu-id="3bf66-117">In diesem Beispiel wird das `Get-Process` Cmdlet in der [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) -Methode eines Cmdlets aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3bf66-117">In this example, the `Get-Process` cmdlet is invoked from within the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method of a cmdlet.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3bf66-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3bf66-118">See Also</span></span>

[<span data-ttu-id="3bf66-119">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3bf66-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
