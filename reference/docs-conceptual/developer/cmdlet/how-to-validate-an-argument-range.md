---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen eines Argumentbereichs
description: Überprüfen eines Argumentbereichs
ms.openlocfilehash: 1c1c53d43350a38beb2193200de3bd6b689366a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666925"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="93325-103">Überprüfen eines Argumentbereichs</span><span class="sxs-lookup"><span data-stu-id="93325-103">How to Validate an Argument Range</span></span>

<span data-ttu-id="93325-104">In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit den minimalen und maximalen Wert des Parameter Arguments vor dem Ausführen des Cmdlets überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="93325-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="93325-105">Diese Validierungs Regel legen Sie fest, indem Sie das validaterange-Attribut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="93325-105">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="93325-106">Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span><span class="sxs-lookup"><span data-stu-id="93325-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="93325-107">So validieren Sie einen Argument Bereich</span><span class="sxs-lookup"><span data-stu-id="93325-107">To validate an argument range</span></span>

- <span data-ttu-id="93325-108">Fügen Sie das validaterange-Attribut hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="93325-108">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="93325-109">In diesem Beispiel wird ein Bereich von 0 bis 5 für den- `InputData` Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="93325-109">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

<span data-ttu-id="93325-110">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validaterange-Attribut Deklaration](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="93325-110">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="93325-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93325-111">See Also</span></span>

[<span data-ttu-id="93325-112">Attributdeklaration: ValidateRange</span><span class="sxs-lookup"><span data-stu-id="93325-112">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

[<span data-ttu-id="93325-113">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="93325-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
