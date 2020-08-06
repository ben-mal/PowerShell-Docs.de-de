---
title: Stop proc-Tutorial | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e298c729b7ac59141638052d19b95ab77aa25cd6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786474"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="432c6-102">StopProc-Tutorial</span><span class="sxs-lookup"><span data-stu-id="432c6-102">StopProc Tutorial</span></span>

<span data-ttu-id="432c6-103">Dieser Abschnitt enthält ein Tutorial zum Erstellen des Cmdlets "Break-proc", das dem von Windows PowerShell bereitgestellten Cmdlet " [Process-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) " sehr ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="432c6-103">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="432c6-104">Dieses Tutorial enthält Code Fragmente, die veranschaulichen, wie Cmdlets implementiert werden, und eine Erläuterung des Codes.</span><span class="sxs-lookup"><span data-stu-id="432c6-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="432c6-105">Themen in diesem Tutorial</span><span class="sxs-lookup"><span data-stu-id="432c6-105">Topics in this Tutorial</span></span>

<span data-ttu-id="432c6-106">Die Themen in diesem Lernprogramm sind so konzipiert, dass Sie sequenziell gelesen werden, wobei jedes Thema auf den im vorherigen Thema behandelten Themen aufbaut.</span><span class="sxs-lookup"><span data-stu-id="432c6-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="432c6-107">[Erstellen eines Cmdlets, das das System ändert](./creating-a-cmdlet-that-modifies-the-system.md) In diesem Abschnitt wird beschrieben, wie Sie ein Cmdlet erstellen, das Systemänderungen unterstützt, z. b. das Beenden eines auf dem Computer ausgeführtes Verfahren</span><span class="sxs-lookup"><span data-stu-id="432c6-107">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="432c6-108">[Hinzufügen von Benutzer Nachrichten zum Cmdlet](./adding-user-messages-to-your-cmdlet.md) In diesem Abschnitt wird beschrieben, wie Sie die Möglichkeit zum Schreiben von Benutzer Nachrichten, Debugmeldungen, Warnmeldungen und Statusinformationen in das Cmdlet hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="432c6-108">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="432c6-109">[Hinzufügen von Aliasen, Platzhalter Erweiterungen und Hilfe zu Cmdlet-Parametern](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) In diesem Abschnitt wird beschrieben, wie Sie ein Cmdlet erstellen, das Parameter Aliase, Hilfe und Platzhalter Erweiterungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="432c6-109">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="432c6-110">[Hinzufügen von Parameter Sätzen zu Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) In diesem Abschnitt wird beschrieben, wie Parametersätze einem Cmdlet hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="432c6-110">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="432c6-111">Mithilfe von Parametersätzen kann das Cmdlet basierend auf den Parametern, die vom Benutzer angegeben werden, unterschiedlich funktionieren.</span><span class="sxs-lookup"><span data-stu-id="432c6-111">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="432c6-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="432c6-112">See Also</span></span>

[<span data-ttu-id="432c6-113">Erstellen eines Cmdlet, das das System ändert</span><span class="sxs-lookup"><span data-stu-id="432c6-113">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="432c6-114">Hinzufügen von Benutzermeldungen zum Cmdlet</span><span class="sxs-lookup"><span data-stu-id="432c6-114">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="432c6-115">Hinzufügen von Aliasen, Platzhaltererweiterung und Hilfe zu Cmdlet-Parametern</span><span class="sxs-lookup"><span data-stu-id="432c6-115">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="432c6-116">Hinzufügen von Parameter Sätzen zu Cmdlets</span><span class="sxs-lookup"><span data-stu-id="432c6-116">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="432c6-117">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="432c6-117">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
