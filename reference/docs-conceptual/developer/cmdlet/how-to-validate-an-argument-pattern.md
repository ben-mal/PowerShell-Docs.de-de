---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen eines Argumentmusters
description: Überprüfen eines Argumentmusters
ms.openlocfilehash: ab5777c918a53c0a3900f87c52e7f14f9cb9b726
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666908"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="dc3f8-103">Überprüfen eines Argumentmusters</span><span class="sxs-lookup"><span data-stu-id="dc3f8-103">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="dc3f8-104">In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit das Zeichen Muster des Parameter Arguments vor dem Ausführen des Cmdlets überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="dc3f8-105">Diese Validierungs Regel legen Sie fest, indem Sie das validatepattern-Attribut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-105">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="dc3f8-106">Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span><span class="sxs-lookup"><span data-stu-id="dc3f8-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="dc3f8-107">So validieren Sie ein Argument Muster</span><span class="sxs-lookup"><span data-stu-id="dc3f8-107">To validate an argument pattern</span></span>

- <span data-ttu-id="dc3f8-108">Fügen Sie das Validate-Attribut hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="dc3f8-109">In diesem Beispiel wird ein Muster von vier Ziffern angegeben, wobei jede Ziffer den Wert 0 bis 9 hat.</span><span class="sxs-lookup"><span data-stu-id="dc3f8-109">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

    ```csharp
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }

    private int inputData;
    ```

<span data-ttu-id="dc3f8-110">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validatepattern-Attribut Deklaration](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="dc3f8-110">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc3f8-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc3f8-111">See Also</span></span>

[<span data-ttu-id="dc3f8-112">Attributdeklaration: ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="dc3f8-112">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

[<span data-ttu-id="dc3f8-113">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="dc3f8-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
