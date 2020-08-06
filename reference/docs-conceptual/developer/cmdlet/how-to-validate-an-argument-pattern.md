---
title: Validieren eines Argument Musters | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- ValidatePattern attribute, example
ms.openlocfilehash: 35104e786d4b809a711d97fea52ae0e348dd5ca3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782088"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="b8141-102">Überprüfen eines Argumentmusters</span><span class="sxs-lookup"><span data-stu-id="b8141-102">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="b8141-103">In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit das Zeichen Muster des Parameter Arguments vor dem Ausführen des Cmdlets überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="b8141-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="b8141-104">Diese Validierungs Regel legen Sie fest, indem Sie das validatepattern-Attribut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b8141-104">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="b8141-105">Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span><span class="sxs-lookup"><span data-stu-id="b8141-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="b8141-106">So validieren Sie ein Argument Muster</span><span class="sxs-lookup"><span data-stu-id="b8141-106">To validate an argument pattern</span></span>

- <span data-ttu-id="b8141-107">Fügen Sie das Validate-Attribut hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8141-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="b8141-108">In diesem Beispiel wird ein Muster von vier Ziffern angegeben, wobei jede Ziffer den Wert 0 bis 9 hat.</span><span class="sxs-lookup"><span data-stu-id="b8141-108">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

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

<span data-ttu-id="b8141-109">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validatepattern-Attribut Deklaration](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="b8141-109">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8141-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8141-110">See Also</span></span>

[<span data-ttu-id="b8141-111">Attributdeklaration: ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="b8141-111">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

[<span data-ttu-id="b8141-112">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b8141-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
