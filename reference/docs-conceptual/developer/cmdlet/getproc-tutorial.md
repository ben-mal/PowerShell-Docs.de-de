---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc-Tutorial
description: GetProc-Tutorial
ms.openlocfilehash: 9379e791dd5361fcf5b79061bf0a601ebeb84f42
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652789"
---
# <a name="getproc-tutorial"></a><span data-ttu-id="0a1ff-103">GetProc-Tutorial</span><span class="sxs-lookup"><span data-stu-id="0a1ff-103">GetProc Tutorial</span></span>

<span data-ttu-id="0a1ff-104">Dieser Abschnitt enthält ein Tutorial zum Erstellen eines Get-Proc Cmdlets, das dem von Windows PowerShell bereitgestellten Cmdlet " [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) " sehr ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-104">This section provides a tutorial for creating a Get-Proc cmdlet that is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="0a1ff-105">Dieses Tutorial enthält Code Fragmente, die veranschaulichen, wie Cmdlets implementiert werden, und eine Erläuterung des Codes.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-105">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="0a1ff-106">Themen in diesem Tutorial</span><span class="sxs-lookup"><span data-stu-id="0a1ff-106">Topics in this Tutorial</span></span>

<span data-ttu-id="0a1ff-107">Die Themen in diesem Lernprogramm sind so konzipiert, dass Sie sequenziell gelesen werden, wobei jedes Thema auf den im vorherigen Thema behandelten Themen aufbaut.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-107">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="0a1ff-108">[Erstellen eines Cmdlets ohne Parameter](./creating-a-cmdlet-without-parameters.md) In diesem Abschnitt wird beschrieben, wie Sie ein Cmdlet erstellen, das Informationen vom lokalen Computer abruft, ohne Parameter zu verwenden, und dann die Informationen in die Pipeline schreibt.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-108">[Creating a Cmdlet without Parameters](./creating-a-cmdlet-without-parameters.md) This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="0a1ff-109">[Hinzufügen von Parametern, die Command-Line Eingabe verarbeiten](./adding-parameters-that-process-command-line-input.md) In diesem Abschnitt wird beschrieben, wie Sie dem Get-Proc-Cmdlet einen Parameter hinzufügen, damit das Cmdlet Eingaben auf der Grundlage von expliziten Objekten verarbeiten kann, die an das Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-109">[Adding Parameters that Process Command-Line Input](./adding-parameters-that-process-command-line-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process input based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="0a1ff-110">In der hier beschriebenen Implementierung werden Prozesse anhand ihres Namens abgerufen und dann in die Pipeline geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-110">The implementation described here retrieves processes based on their name, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="0a1ff-111">[Hinzufügen von Parametern, die Pipeline Eingaben verarbeiten](./adding-parameters-that-process-pipeline-input.md) In diesem Abschnitt wird beschrieben, wie Sie dem Get-Proc-Cmdlet einen Parameter hinzufügen, damit das Cmdlet Objekte verarbeiten kann, die über die Pipeline an das Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-111">[Adding Parameters that Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process objects passed to it through the pipeline.</span></span> <span data-ttu-id="0a1ff-112">Das hier beschriebene Implementierungs-Cmdlet ruft Prozesse auf der Grundlage von Objekten ab, die an das Cmdlet übergeben werden, und schreibt dann die Informationen in die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-112">The implementation cmdlet described here retrieves processes based on objects passed to the cmdlet, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="0a1ff-113">[Hinzufügen der Fehlerberichterstattung für nicht abschließende Informationen zum Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) In diesem Abschnitt wird beschrieben, wie einem Cmdlet eine nicht abschließende Fehlerberichterstattung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-113">[Adding Nonterminating Error Reporting to Your Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) This section describes how to add nonterminating error reporting to a cmdlet.</span></span> <span data-ttu-id="0a1ff-114">Die hier beschriebene Implementierung erkennt nicht abschließende Fehler, die bei der Verarbeitung von Eingaben auftreten, und schreibt einen Fehler Daten Satz in den Fehler Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="0a1ff-114">The implementation described here detects nonterminating errors that occur when processing input, and writes an error record to the error stream.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a1ff-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a1ff-115">See Also</span></span>

[<span data-ttu-id="0a1ff-116">Erstellen eines Cmdlet ohne Parameter</span><span class="sxs-lookup"><span data-stu-id="0a1ff-116">Creating a Cmdlet without Parameters</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="0a1ff-117">Hinzufügen von Parametern, die Command-Line Eingabe verarbeiten</span><span class="sxs-lookup"><span data-stu-id="0a1ff-117">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="0a1ff-118">Hinzufügen von Parametern, die Pipelineeingaben verarbeiten</span><span class="sxs-lookup"><span data-stu-id="0a1ff-118">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="0a1ff-119">Hinzufügen der Fehlerberichterstattung für nicht abschließende Informationen zum Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0a1ff-119">Adding Nonterminating Error Reporting to Your Cmdlet</span></span>](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[<span data-ttu-id="0a1ff-120">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="0a1ff-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
