---
title: Validieren der Argument Länge | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, example
ms.openlocfilehash: aa0545def6d9628f6b41090a425f0c5af25f6ad7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784077"
---
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="1b5a7-102">Überprüfen einer Argumentlänge</span><span class="sxs-lookup"><span data-stu-id="1b5a7-102">How to Validate the Argument Length</span></span>

<span data-ttu-id="1b5a7-103">In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit die Anzahl der Zeichen (die Länge) des Parameter Arguments vor dem Ausführen des Cmdlets überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="1b5a7-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="1b5a7-104">Diese Validierungs Regel legen Sie fest, indem Sie das validateLength-Attribut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1b5a7-104">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="1b5a7-105">Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span><span class="sxs-lookup"><span data-stu-id="1b5a7-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="1b5a7-106">So überprüfen Sie die Argument Länge</span><span class="sxs-lookup"><span data-stu-id="1b5a7-106">To validate the argument length</span></span>

- <span data-ttu-id="1b5a7-107">Fügen Sie das Validate-Attribut hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b5a7-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="1b5a7-108">In diesem Beispiel wird angegeben, dass die Länge des Arguments eine Länge von 0 bis 10 Zeichen aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="1b5a7-108">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="1b5a7-109">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validateLength-Attribut Deklaration](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="1b5a7-109">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b5a7-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b5a7-110">See Also</span></span>

[<span data-ttu-id="1b5a7-111">Attributdeklaration: ValidateLength</span><span class="sxs-lookup"><span data-stu-id="1b5a7-111">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

[<span data-ttu-id="1b5a7-112">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1b5a7-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
