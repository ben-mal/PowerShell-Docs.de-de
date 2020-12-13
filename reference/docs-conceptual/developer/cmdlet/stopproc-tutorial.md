---
ms.date: 09/13/2016
ms.topic: reference
title: StopProc-Tutorial
description: StopProc-Tutorial
ms.openlocfilehash: 95229ee3c4905d295bd6991fe8ccf8c9840c3cdd
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646435"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="cdcb1-103">StopProc-Tutorial</span><span class="sxs-lookup"><span data-stu-id="cdcb1-103">StopProc Tutorial</span></span>

<span data-ttu-id="cdcb1-104">Dieser Abschnitt enthält ein Lernprogramm zum Erstellen des-Stop-Proc Cmdlets, das dem von Windows PowerShell bereitgestellten Cmdlet " [Process-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) " sehr ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="cdcb1-104">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="cdcb1-105">Dieses Tutorial enthält Code Fragmente, die veranschaulichen, wie Cmdlets implementiert werden, und eine Erläuterung des Codes.</span><span class="sxs-lookup"><span data-stu-id="cdcb1-105">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="cdcb1-106">Themen in diesem Tutorial</span><span class="sxs-lookup"><span data-stu-id="cdcb1-106">Topics in this Tutorial</span></span>

<span data-ttu-id="cdcb1-107">Die Themen in diesem Lernprogramm sind so konzipiert, dass Sie sequenziell gelesen werden, wobei jedes Thema auf den im vorherigen Thema behandelten Themen aufbaut.</span><span class="sxs-lookup"><span data-stu-id="cdcb1-107">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="cdcb1-108">[Erstellen eines Cmdlets, das das System ändert](./creating-a-cmdlet-that-modifies-the-system.md) In diesem Abschnitt wird beschrieben, wie Sie ein Cmdlet erstellen, das Systemänderungen unterstützt, z. b. das Beenden eines auf dem Computer ausgeführtes Verfahren</span><span class="sxs-lookup"><span data-stu-id="cdcb1-108">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="cdcb1-109">[Hinzufügen von Benutzer Nachrichten zum Cmdlet](./adding-user-messages-to-your-cmdlet.md) In diesem Abschnitt wird beschrieben, wie Sie die Möglichkeit zum Schreiben von Benutzer Nachrichten, Debugmeldungen, Warnmeldungen und Statusinformationen in das Cmdlet hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="cdcb1-109">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="cdcb1-110">[Hinzufügen von Aliasen, Platzhalter Erweiterungen und Hilfe zu Cmdlet-Parametern](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) In diesem Abschnitt wird beschrieben, wie Sie ein Cmdlet erstellen, das Parameter Aliase, Hilfe und Platzhalter Erweiterungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cdcb1-110">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="cdcb1-111">[Hinzufügen von Parameter Sätzen zu Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) In diesem Abschnitt wird beschrieben, wie Parametersätze einem Cmdlet hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cdcb1-111">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="cdcb1-112">Mithilfe von Parametersätzen kann das Cmdlet basierend auf den Parametern, die vom Benutzer angegeben werden, unterschiedlich funktionieren.</span><span class="sxs-lookup"><span data-stu-id="cdcb1-112">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdcb1-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cdcb1-113">See Also</span></span>

[<span data-ttu-id="cdcb1-114">Erstellen eines Cmdlet, das das System ändert</span><span class="sxs-lookup"><span data-stu-id="cdcb1-114">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="cdcb1-115">Hinzufügen von Benutzermeldungen zum Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cdcb1-115">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="cdcb1-116">Hinzufügen von Aliasen, Platzhaltererweiterung und Hilfe zu Cmdlet-Parametern</span><span class="sxs-lookup"><span data-stu-id="cdcb1-116">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="cdcb1-117">Hinzufügen von Parameter Sätzen zu Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cdcb1-117">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="cdcb1-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="cdcb1-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
