---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen eines Argumentsatzes
description: Überprüfen eines Argumentsatzes
ms.openlocfilehash: 50ec0a48277893584d896e14ad6aa843682a28cc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650361"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="cbd25-103">Überprüfen eines Argumentsatzes</span><span class="sxs-lookup"><span data-stu-id="cbd25-103">How to Validate an Argument Set</span></span>

<span data-ttu-id="cbd25-104">Dieses Beispiel zeigt, wie Sie eine Validierungs Regel angeben, mit der die Windows PowerShell-Laufzeit das Parameter Argument vor dem Ausführen des Cmdlets überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="cbd25-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="cbd25-105">Diese Validierungs Regel stellt einen Satz gültiger Werte für das Parameter Argument bereit.</span><span class="sxs-lookup"><span data-stu-id="cbd25-105">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="cbd25-106">Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span><span class="sxs-lookup"><span data-stu-id="cbd25-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="cbd25-107">So validieren Sie einen Argument Satz</span><span class="sxs-lookup"><span data-stu-id="cbd25-107">To validate an argument set</span></span>

- <span data-ttu-id="cbd25-108">Fügen Sie das validateset-Attribut hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cbd25-108">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="cbd25-109">In diesem Beispiel wird ein Satz von drei möglichen Werten für den- `UserName` Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="cbd25-109">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

    ```csharp
    [ValidateSet("Steve", "Mary", "Carl", IgnoreCase = true)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }

    private string userName;
    ```

<span data-ttu-id="cbd25-110">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validateset-Attribut Deklaration](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="cbd25-110">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cbd25-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbd25-111">See Also</span></span>

[<span data-ttu-id="cbd25-112">System. Management. Automation. validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="cbd25-112">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="cbd25-113">Attributdeklaration: ValidateSet</span><span class="sxs-lookup"><span data-stu-id="cbd25-113">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="cbd25-114">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cbd25-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
