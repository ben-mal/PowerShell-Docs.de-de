---
title: Validieren einer Argument Anzahl | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateCount attribute, example
ms.openlocfilehash: e7c0eb364a6975cec089b984c2100d476631a12d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782122"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="41f16-102">Überprüfen einer Argumentanzahl</span><span class="sxs-lookup"><span data-stu-id="41f16-102">How to Validate an Argument Count</span></span>

<span data-ttu-id="41f16-103">In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit die Anzahl der Argumente (die Anzahl) überprüfen kann, die ein Parameter annimmt, bevor das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="41f16-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="41f16-104">Diese Validierungs Regel legen Sie fest, indem Sie das validatecount-Attribut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="41f16-104">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="41f16-105">Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatezähltattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span><span class="sxs-lookup"><span data-stu-id="41f16-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="41f16-106">So überprüfen Sie eine Argument Anzahl</span><span class="sxs-lookup"><span data-stu-id="41f16-106">To validate an argument count</span></span>

- <span data-ttu-id="41f16-107">Fügen Sie das Validate-Attribut hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="41f16-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="41f16-108">In diesem Beispiel wird angegeben, dass der-Parameter ein Argument oder bis zu drei Argumente akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="41f16-108">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

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

<span data-ttu-id="41f16-109">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validatecount-Attribut Deklaration](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="41f16-109">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41f16-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41f16-110">See Also</span></span>

[<span data-ttu-id="41f16-111">Attributdeklaration: ValidateCount</span><span class="sxs-lookup"><span data-stu-id="41f16-111">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="41f16-112">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="41f16-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
