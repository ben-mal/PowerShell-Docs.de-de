---
title: Bestätigungsmeldungen | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 8f8192f6ed96b1eeb22e3b28ce1366eee8e7c16a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782190"
---
# <a name="confirmation-messages"></a><span data-ttu-id="0a103-102">Bestätigungsmeldungen</span><span class="sxs-lookup"><span data-stu-id="0a103-102">Confirmation Messages</span></span>

<span data-ttu-id="0a103-103">Im folgenden finden Sie unterschiedliche Bestätigungsmeldungen, die je nach den Varianten der Methoden " [System. Management. Automation. Cmdlet. Schulter dprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) " und " [System. Management. Automation. Cmdlet. schuldcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) " angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="0a103-103">Here are different confirmation messages that can be displayed depending on the variants of the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods that are called.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a103-104">Beispielcode, der zeigt, wie Bestätigungen angefordert werden, finden Sie unter [anfordern von Bestätigungen](./how-to-request-confirmations.md).</span><span class="sxs-lookup"><span data-stu-id="0a103-104">For sample code that shows how to request confirmations, see [How to Request Confirmations](./how-to-request-confirmations.md).</span></span>

## <a name="specifying-the-resource"></a><span data-ttu-id="0a103-105">Angeben der Ressource</span><span class="sxs-lookup"><span data-stu-id="0a103-105">Specifying the Resource</span></span>

<span data-ttu-id="0a103-106">Sie können die zu ändernde Ressource angeben, indem Sie das [System. Management. Automation. Cmdlet aufrufen. Displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) -Methode.</span><span class="sxs-lookup"><span data-stu-id="0a103-106">You can specify the resource that is about to be changed by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="0a103-107">In diesem Fall stellen Sie die Ressource mithilfe des `target` -Parameters der-Methode bereit, und der Vorgang wird von Windows PowerShell hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0a103-107">In this case, you supply the resource by using the `target` parameter of the method, and the operation is added by Windows PowerShell.</span></span> <span data-ttu-id="0a103-108">In der folgenden Meldung ist der Text "MyResource" die Ressource, auf die reagiert wird, und der Vorgang ist der Name des Befehls, der den-Vorgang ausführt.</span><span class="sxs-lookup"><span data-stu-id="0a103-108">In the following message, the text "MyResource" is the resource acted on and the operation is the name of the command that makes the call.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="0a103-109">Wenn der Benutzer für die Bestätigungs Anforderung **Ja** oder **Ja** (wie im folgenden Beispiel gezeigt) auswählt, wird ein [System. Management. Automation. Cmdlet. ermdcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) -Methode aufgerufen, wodurch eine zweite Bestätigungsmeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a103-109">If the user selects **Yes** or **Yes to All** to the confirmation request (as shown in the following example), a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a><span data-ttu-id="0a103-110">Angeben des Vorgangs und der Ressource</span><span class="sxs-lookup"><span data-stu-id="0a103-110">Specifying the Operation and Resource</span></span>

<span data-ttu-id="0a103-111">Sie können die zu ändernde Ressource und den von dem Befehl auszuführenden Vorgang angeben, indem Sie das [System. Management. Automation. Cmdlet. tiondprocess% 2a aufrufen? Displayproperty = FullName](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) -Methode.</span><span class="sxs-lookup"><span data-stu-id="0a103-111">You can specify the resource that is about to be changed and the operation that the command is about to perform by calling the [System.Management.Automation.Cmdlet.Shouldprocess%2A?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0) method.</span></span> <span data-ttu-id="0a103-112">In diesem Fall stellen Sie die Ressource mithilfe des `target` -Parameters und des-Vorgangs bereit, indem Sie den- `target` Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a103-112">In this case, you supply the resource by using the `target` parameter and the operation by using the `target` parameter.</span></span> <span data-ttu-id="0a103-113">In der folgenden Meldung ist der Text "MyResource" die Ressource, die ausgeführt wird, und "myaction" ist der Vorgang, der ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a103-113">In the following message, the text "MyResource" is the resource acted on and "MyAction" is the operation to be performed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="0a103-114">Wenn der Benutzer für die vorherige Nachricht **Ja** oder **Ja** ausgewählt hat, wird ein Rückruf der [System. Management. Automation. Cmdlet. ermdcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) -Methode durchgeführt, wodurch eine zweite Bestätigungsmeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a103-114">If the user selects **Yes** or **Yes to All** to the previous message, a call to the [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) method is made, which causes a second confirmation message to be displayed.</span></span>

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a><span data-ttu-id="0a103-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a103-115">See Also</span></span>

[<span data-ttu-id="0a103-116">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0a103-116">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
