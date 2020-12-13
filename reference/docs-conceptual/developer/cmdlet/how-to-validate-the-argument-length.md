---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen einer Argumentlänge
description: Überprüfen einer Argumentlänge
ms.openlocfilehash: 460aedbe6847033f976cb7bf70b6c77ac5a3a3c9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652630"
---
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="3fab1-103">Überprüfen einer Argumentlänge</span><span class="sxs-lookup"><span data-stu-id="3fab1-103">How to Validate the Argument Length</span></span>

<span data-ttu-id="3fab1-104">In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit die Anzahl der Zeichen (die Länge) des Parameter Arguments vor dem Ausführen des Cmdlets überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="3fab1-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="3fab1-105">Diese Validierungs Regel legen Sie fest, indem Sie das validateLength-Attribut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3fab1-105">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="3fab1-106">Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span><span class="sxs-lookup"><span data-stu-id="3fab1-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="3fab1-107">So überprüfen Sie die Argument Länge</span><span class="sxs-lookup"><span data-stu-id="3fab1-107">To validate the argument length</span></span>

- <span data-ttu-id="3fab1-108">Fügen Sie das Validate-Attribut hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fab1-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="3fab1-109">In diesem Beispiel wird angegeben, dass die Länge des Arguments eine Länge von 0 bis 10 Zeichen aufweisen soll.</span><span class="sxs-lookup"><span data-stu-id="3fab1-109">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

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

<span data-ttu-id="3fab1-110">Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validateLength-Attribut Deklaration](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="3fab1-110">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3fab1-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fab1-111">See Also</span></span>

[<span data-ttu-id="3fab1-112">Attributdeklaration: ValidateLength</span><span class="sxs-lookup"><span data-stu-id="3fab1-112">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

[<span data-ttu-id="3fab1-113">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3fab1-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
