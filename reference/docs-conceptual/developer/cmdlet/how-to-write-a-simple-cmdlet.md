---
ms.date: 01/15/2019
ms.topic: reference
title: Schreiben eines einfaches Cmdlet
description: Schreiben eines einfaches Cmdlet
ms.openlocfilehash: 59dce5d797f80647e0b70a1f80faf67198652082
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646495"
---
# <a name="how-to-write-a-cmdlet"></a><span data-ttu-id="c98d6-103">Schreiben eines Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c98d6-103">How to write a cmdlet</span></span>

<span data-ttu-id="c98d6-104">In diesem Artikel wird gezeigt, wie Sie ein Cmdlet schreiben.</span><span class="sxs-lookup"><span data-stu-id="c98d6-104">This article shows how to write a cmdlet.</span></span> <span data-ttu-id="c98d6-105">Das `Send-Greeting` Cmdlet nimmt einen einzelnen Benutzernamen als Eingabe an und schreibt dann eine Begrüßung an diesen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c98d6-105">The `Send-Greeting` cmdlet takes a single user name as input and then writes a greeting to that user.</span></span> <span data-ttu-id="c98d6-106">Obwohl das Cmdlet nicht viel Arbeit leistet, veranschaulicht dieses Beispiel die Hauptabschnitte eines Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c98d6-106">Although the cmdlet does not do much work, this example demonstrates the major sections of a cmdlet.</span></span>

## <a name="steps-to-write-a-cmdlet"></a><span data-ttu-id="c98d6-107">Schritte zum Schreiben eines Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c98d6-107">Steps to write a cmdlet</span></span>

1. <span data-ttu-id="c98d6-108">Verwenden Sie das **Cmdlet** -Attribut, um die Klasse als Cmdlet zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c98d6-108">To declare the class as a cmdlet, use the **Cmdlet** attribute.</span></span> <span data-ttu-id="c98d6-109">Das **Cmdlet** -Attribut gibt das Verb und das Substantiv für den Namen des Cmdlets an.</span><span class="sxs-lookup"><span data-stu-id="c98d6-109">The **Cmdlet** attribute specifies the verb and the noun for the cmdlet name.</span></span>

   <span data-ttu-id="c98d6-110">Weitere Informationen zum **Cmdlet** -Attribut finden Sie unter [CmdletAttribute-Deklaration](cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="c98d6-110">For more information about the **Cmdlet** attribute, see [CmdletAttribute Declaration](cmdlet-attribute-declaration.md).</span></span>

2. <span data-ttu-id="c98d6-111">Geben Sie den Namen der Klasse an.</span><span class="sxs-lookup"><span data-stu-id="c98d6-111">Specify the name of the class.</span></span>

3. <span data-ttu-id="c98d6-112">Legen Sie fest, dass das Cmdlet von einer der folgenden Klassen abgeleitet ist:</span><span class="sxs-lookup"><span data-stu-id="c98d6-112">Specify that the cmdlet derives from either of the following classes:</span></span>

   * [<span data-ttu-id="c98d6-113">System. Management. Automation. Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c98d6-113">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)
   * [<span data-ttu-id="c98d6-114">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="c98d6-114">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

4. <span data-ttu-id="c98d6-115">Um die Parameter für das Cmdlet zu definieren, verwenden Sie das **Parameter** Attribut.</span><span class="sxs-lookup"><span data-stu-id="c98d6-115">To define the parameters for the cmdlet, use the **Parameter** attribute.</span></span> <span data-ttu-id="c98d6-116">In diesem Fall wird nur ein erforderlicher Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="c98d6-116">In this case, only one required parameter is specified.</span></span>

   <span data-ttu-id="c98d6-117">Weitere Informationen zum **Parameter** -Attribut finden Sie unter [Parameterattribute-Deklaration](parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="c98d6-117">For more information about the **Parameter** attribute, see [ParameterAttribute Declaration](parameter-attribute-declaration.md).</span></span>

5. <span data-ttu-id="c98d6-118">Überschreiben Sie die Eingabe Verarbeitungsmethode, die die Eingabe verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c98d6-118">Override the input processing method that processes the input.</span></span> <span data-ttu-id="c98d6-119">In diesem Fall wird die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode überschrieben.</span><span class="sxs-lookup"><span data-stu-id="c98d6-119">In this case, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden.</span></span>

6. <span data-ttu-id="c98d6-120">Um die Begrüßung zu schreiben, verwenden Sie die Methode [System. Management. Automation. Cmdlet. Write-Object](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span><span class="sxs-lookup"><span data-stu-id="c98d6-120">To write the greeting, use the method [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject).</span></span>
   <span data-ttu-id="c98d6-121">Die Begrüßung wird im folgenden Format angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c98d6-121">The greeting is displayed in the following format:</span></span>

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a><span data-ttu-id="c98d6-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c98d6-122">Example</span></span>

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

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

## <a name="see-also"></a><span data-ttu-id="c98d6-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c98d6-123">See also</span></span>

[<span data-ttu-id="c98d6-124">System. Management. Automation. Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c98d6-124">System.Management.Automation.Cmdlet</span></span>](/dotnet/api/System.Management.Automation.Cmdlet)

[<span data-ttu-id="c98d6-125">System. Management. Automation. PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="c98d6-125">System.Management.Automation.PSCmdlet</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet)

[<span data-ttu-id="c98d6-126">System. Management. Automation. Cmdlet. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="c98d6-126">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="c98d6-127">System. Management. Automation. Cmdlet. Write Object</span><span class="sxs-lookup"><span data-stu-id="c98d6-127">System.Management.Automation.Cmdlet.WriteObject</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[<span data-ttu-id="c98d6-128">CmdletAttribute-Deklaration</span><span class="sxs-lookup"><span data-stu-id="c98d6-128">CmdletAttribute Declaration</span></span>](cmdlet-attribute-declaration.md)

[<span data-ttu-id="c98d6-129">ParameterAttribute-Deklaration</span><span class="sxs-lookup"><span data-stu-id="c98d6-129">ParameterAttribute Declaration</span></span>](parameter-attribute-declaration.md)

[<span data-ttu-id="c98d6-130">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c98d6-130">Writing a Windows PowerShell Cmdlet</span></span>](writing-a-windows-powershell-cmdlet.md)
