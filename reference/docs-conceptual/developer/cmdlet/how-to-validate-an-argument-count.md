---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen einer Argumentanzahl
description: Überprüfen einer Argumentanzahl
ms.openlocfilehash: 46a32d61138fb50bceea98171f76749c9d96734d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666942"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="c8d33-103">Überprüfen einer Argumentanzahl</span><span class="sxs-lookup"><span data-stu-id="c8d33-103">How to Validate an Argument Count</span></span>

<span data-ttu-id="c8d33-104">In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit die Anzahl der Argumente (die Anzahl) überprüfen kann, die ein Parameter annimmt, bevor das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8d33-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="c8d33-105">Diese Validierungs Regel legen Sie fest, indem Sie das validatecount-Attribut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c8d33-105">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="c8d33-106">Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatezähltattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span><span class="sxs-lookup"><span data-stu-id="c8d33-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="c8d33-107">So überprüfen Sie eine Argument Anzahl</span><span class="sxs-lookup"><span data-stu-id="c8d33-107">To validate an argument count</span></span>

- <span data-ttu-id="c8d33-108">Fügen Sie das Validate-Attribut hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8d33-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="c8d33-109">In diesem Beispiel wird angegeben, dass der-Parameter ein Argument oder bis zu drei Argumente akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c8d33-109">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

    ```csharp
    [ValidateCount(1, 3)]
    [Parameter(Position = 0, Mandatory = true)]
    public string[] UserNames
    {
      get { return userNames; }
      set { userNames = value; }
    }

    private string[] userNames;
    ```

<span data-ttu-id="c8d33-110">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validatecount-Attribut Deklaration](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="c8d33-110">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8d33-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8d33-111">See Also</span></span>

[<span data-ttu-id="c8d33-112">Attributdeklaration: ValidateCount</span><span class="sxs-lookup"><span data-stu-id="c8d33-112">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="c8d33-113">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c8d33-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
