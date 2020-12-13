---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet-Codebeispiele
description: Cmdlet-Codebeispiele
ms.openlocfilehash: 91dd2019300504697ad9a7a0c155a04600d09c58
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652911"
---
# <a name="examples-of-cmdlet-code"></a><span data-ttu-id="b8175-103">Cmdlet-Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="b8175-103">Examples of Cmdlet Code</span></span>

<span data-ttu-id="b8175-104">Dieser Abschnitt enthält Beispiele für Cmdlet-Code, den Sie verwenden können, um mit dem Schreiben Ihrer eigenen Cmdlets zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="b8175-104">This section contains examples of cmdlet code that you can use to start writing your own cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8175-105">Eine schrittweise Anleitung zum Schreiben von Cmdlets finden Sie in den [Tutorials zum Schreiben von Cmdlets](./tutorials-for-writing-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="b8175-105">If you want step-by-step instructions for writing cmdlets, see [Tutorials for Writing Cmdlets](./tutorials-for-writing-cmdlets.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b8175-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b8175-106">In This Section</span></span>

<span data-ttu-id="b8175-107">[Schreiben eines einfachen Cmdlets](./how-to-write-a-simple-cmdlet.md) Dieses Beispiel zeigt die grundlegende Struktur des Cmdlet-Codes.</span><span class="sxs-lookup"><span data-stu-id="b8175-107">[How to Write a Simple Cmdlet](./how-to-write-a-simple-cmdlet.md) This example shows the basic structure of cmdlet code.</span></span>

<span data-ttu-id="b8175-108">[Deklarieren von Cmdlet-Parametern](./how-to-declare-cmdlet-parameters.md) In diesem Beispiel wird gezeigt, wie die verschiedenen Typen von Parametern deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="b8175-108">[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md) This example shows how to declare the different types of parameters.</span></span>

<span data-ttu-id="b8175-109">[Deklarieren von Parameter Sätzen](./how-to-declare-parameter-sets.md) Dieses Beispiel zeigt, wie Sie Sätze von Parametern deklarieren können, die die Aktion ändern können, die ein Cmdlet ausführt.</span><span class="sxs-lookup"><span data-stu-id="b8175-109">[How to Declare Parameter Sets](./how-to-declare-parameter-sets.md) This example shows how to declare sets of parameters that can change the action a cmdlet performs.</span></span>

<span data-ttu-id="b8175-110">[Validieren von Parameter Eingaben](./how-to-validate-parameter-input.md) In diesen Beispielen wird gezeigt, wie Parameter Eingaben überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="b8175-110">[How to Validate Parameter Input](./how-to-validate-parameter-input.md) These examples show how to validate parameter input.</span></span>

<span data-ttu-id="b8175-111">[Deklarieren dynamischer Parameter](./how-to-declare-dynamic-parameters.md) Dieses Beispiel zeigt, wie ein Parameter deklariert wird, der zur Laufzeit hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b8175-111">[How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md) This example shows how to declare a parameter that is added at runtime.</span></span>

<span data-ttu-id="b8175-112">[Aufrufen von Skripts in einem Cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md) Dieses Beispiel zeigt, wie ein Skript aufgerufen wird, das für ein Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b8175-112">[How to Invoke Scripts Within a Cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md) This example shows how to invoke a script that is supplied to a cmdlet.</span></span>

<span data-ttu-id="b8175-113">[Überschreiben von Eingabe Verarbeitungsmethoden](./how-to-override-input-processing-methods.md) Diese Beispiele zeigen die grundlegende Struktur, die zum Überschreiben der BeginProcessing-, ProcessRecord-und EndProcessing-Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8175-113">[How To Override Input Processing Methods](./how-to-override-input-processing-methods.md) These examples show the basic structure used to override the BeginProcessing, ProcessRecord, and EndProcessing methods.</span></span>

<span data-ttu-id="b8175-114">Vorgehens [Weise bei der Unterstützung von "schuldprocess](./how-to-request-confirmations.md) " Dieses Beispiel zeigt, wie die Methoden " [System. Management. Automation. Cmdlet. Schulter dprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) " und " [System. Management. Automation. Cmdlet. daudcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) " innerhalb eines Cmdlets aufgerufen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="b8175-114">[How to Support ShouldProcess Calls](./how-to-request-confirmations.md) This example shows how the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods should be called from within a cmdlet.</span></span>

<span data-ttu-id="b8175-115">[Unterstützung von Transaktionen](./how-to-support-transactions.md) Dieses Beispiel zeigt, wie Sie angeben, dass das Cmdlet Transaktionen unterstützt und wie Sie die Aktion implementieren, die durchgeführt wird, wenn das Cmdlet innerhalb einer Transaktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8175-115">[How to Support Transactions](./how-to-support-transactions.md) This example shows how to indicate that the cmdlet supports transactions and how to implement the action that is taken when the cmdlet is used within a transaction.</span></span>

<span data-ttu-id="b8175-116">Vorgehens [Weise beim unterstützen von Aufträgen](./how-to-support-jobs.md) In diesem Beispiel wird gezeigt, wie Aufträge beim Schreiben von Cmdlets unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b8175-116">[How to Support Jobs](./how-to-support-jobs.md) This example shows how to support jobs when you write cmdlets.</span></span>

<span data-ttu-id="b8175-117">[Aufrufen eines Cmdlets innerhalb eines Cmdlets](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) In diesem Beispiel wird gezeigt, wie ein Cmdlet aus einem anderen Cmdlet aufgerufen wird, mit dem Sie die Funktionalität des aufgerufenen Cmdlets zum Cmdlet hinzufügen können, das Sie entwickeln.</span><span class="sxs-lookup"><span data-stu-id="b8175-117">[How to Invoke a Cmdlet From Within a Cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8175-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8175-118">See Also</span></span>

[<span data-ttu-id="b8175-119">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b8175-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
