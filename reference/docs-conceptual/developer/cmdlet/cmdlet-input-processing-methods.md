---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet-Eingabeverarbeitungsmethoden
description: Cmdlet-Eingabeverarbeitungsmethoden
ms.openlocfilehash: e1a7b58517d6285250edbf16d14810388c242218
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653396"
---
# <a name="cmdlet-input-processing-methods"></a><span data-ttu-id="3ae8c-103">Cmdlet-Eingabeverarbeitungsmethoden</span><span class="sxs-lookup"><span data-stu-id="3ae8c-103">Cmdlet Input Processing Methods</span></span>

<span data-ttu-id="3ae8c-104">Cmdlets müssen eine oder mehrere der in diesem Thema beschriebenen Eingabe Verarbeitungsmethoden überschreiben, um Ihre Arbeit zu erledigen.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-104">Cmdlets must override one or more of the input processing methods described in this topic to perform their work.</span></span>
<span data-ttu-id="3ae8c-105">Diese Methoden ermöglichen es dem Cmdlet, Vorgänge der vorab Verarbeitung, der Eingabe Verarbeitung und der Nachbearbeitung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-105">These methods allow the cmdlet to perform operations of pre-processing, input processing, and post-processing.</span></span>
<span data-ttu-id="3ae8c-106">Diese Methoden ermöglichen auch das Abbrechen der Cmdlet-Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-106">These methods also allow you to stop cmdlet processing.</span></span>
<span data-ttu-id="3ae8c-107">Ein ausführlicheres Beispiel für die Verwendung dieser Methoden finden Sie unter [selectstr-Tutorial](selectstr-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="3ae8c-107">For a more detailed example of how to use these methods, see [SelectStr Tutorial](selectstr-tutorial.md).</span></span>

## <a name="pre-processing-operations"></a><span data-ttu-id="3ae8c-108">Vorverarbeitungs Vorgänge</span><span class="sxs-lookup"><span data-stu-id="3ae8c-108">Pre-Processing Operations</span></span>

<span data-ttu-id="3ae8c-109">Cmdlets sollten die [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) -Methode überschreiben, um Vorverarbeitungs Vorgänge hinzuzufügen, die für alle Datensätze gültig sind, die später vom Cmdlet verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-109">Cmdlets should override the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method to add any preprocessing operations that are valid for all the records that will be processed later by the cmdlet.</span></span>
<span data-ttu-id="3ae8c-110">Wenn PowerShell eine Befehls Pipeline verarbeitet, ruft PowerShell diese Methode für jede Instanz des Cmdlets in der Pipeline einmal auf.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-110">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="3ae8c-111">Weitere Informationen dazu, wie PowerShell die Befehls Pipeline aufruft, finden Sie unter [Cmdlet processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="3ae8c-111">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="3ae8c-112">Der folgende Code zeigt eine Implementierung der BeginProcessing-Methode.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-112">The following code shows an implementation of the BeginProcessing method.</span></span>

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a><span data-ttu-id="3ae8c-113">Eingabe Verarbeitungsvorgänge</span><span class="sxs-lookup"><span data-stu-id="3ae8c-113">Input Processing Operations</span></span>

<span data-ttu-id="3ae8c-114">Cmdlets können die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode überschreiben, um die Eingabe zu verarbeiten, die an das Cmdlet gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-114">Cmdlets can override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to process the input that is sent to the cmdlet.</span></span>
<span data-ttu-id="3ae8c-115">Wenn PowerShell eine Befehls Pipeline verarbeitet, ruft PowerShell diese Methode für jeden Eingabedaten Satz auf, der vom Cmdlet verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-115">When PowerShell processes a command pipeline, PowerShell calls this method for each input record that is processed by the cmdlet.</span></span>
<span data-ttu-id="3ae8c-116">Weitere Informationen dazu, wie PowerShell die Befehls Pipeline aufruft, finden Sie unter [Cmdlet processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="3ae8c-116">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="3ae8c-117">Der folgende Code zeigt eine Implementierung der ProcessRecord-Methode.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-117">The following code shows an implementation of the ProcessRecord method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a><span data-ttu-id="3ae8c-118">Vorgänge nach der Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="3ae8c-118">Post-Processing Operations</span></span>

<span data-ttu-id="3ae8c-119">Cmdlets sollten die [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) -Methode überschreiben, um alle nach Verarbeitungsvorgänge hinzuzufügen, die für alle vom Cmdlet verarbeiteten Datensätze gültig sind.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-119">Cmdlets should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method to add any post-processing operations that are valid for all the records that were processed by the cmdlet.</span></span>
<span data-ttu-id="3ae8c-120">Beispielsweise muss das Cmdlet möglicherweise Objektvariablen bereinigen, nachdem die Verarbeitung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-120">For example, your cmdlet might have to clean up object variables after it is finished processing.</span></span>

<span data-ttu-id="3ae8c-121">Wenn PowerShell eine Befehls Pipeline verarbeitet, ruft PowerShell diese Methode für jede Instanz des Cmdlets in der Pipeline einmal auf.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-121">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="3ae8c-122">Es ist jedoch wichtig zu beachten, dass die PowerShell-Runtime die EndProcessing-Methode nicht aufruft, wenn das Cmdlet in der Mitte durch die Eingabe Verarbeitung abgebrochen wird oder wenn in einem beliebigen Teil des Cmdlets ein Abbruch Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-122">However, it is important to remember that the PowerShell runtime will not call the EndProcessing method if the cmdlet is canceled midway through its input processing or if a terminating error occurs in any part of the cmdlet.</span></span>
<span data-ttu-id="3ae8c-123">Aus diesem Grund sollte ein Cmdlet, das die Objekt Bereinigung erfordert, das komplette [System. iverwerf-](/dotnet/api/System.IDisposable) Muster implementieren, einschließlich eines Finalizers, damit die Laufzeit die EndProcessing-und die [System. iverwerf.](/dotnet/api/System.IDisposable.Dispose) verwerfen-Methode am Ende der Verarbeitung abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-123">For this reason, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including a finalizer, so that the runtime can call both the EndProcessing and [System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span>
<span data-ttu-id="3ae8c-124">Weitere Informationen dazu, wie PowerShell die Befehls Pipeline aufruft, finden Sie unter [Cmdlet processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="3ae8c-124">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="3ae8c-125">Der folgende Code zeigt eine Implementierung der EndProcessing-Methode.</span><span class="sxs-lookup"><span data-stu-id="3ae8c-125">The following code shows an implementation of the EndProcessing method.</span></span>

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a><span data-ttu-id="3ae8c-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ae8c-126">See Also</span></span>

[<span data-ttu-id="3ae8c-127">System. Management. Automation. Cmdlet. BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="3ae8c-127">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="3ae8c-128">System. Management. Automation. Cmdlet. ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="3ae8c-128">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="3ae8c-129">System. Management. Automation. Cmdlet. EndProcessing</span><span class="sxs-lookup"><span data-stu-id="3ae8c-129">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="3ae8c-130">SelectStr-Tutorial</span><span class="sxs-lookup"><span data-stu-id="3ae8c-130">SelectStr Tutorial</span></span>](selectstr-tutorial.md)

[<span data-ttu-id="3ae8c-131">System.IDisposable</span><span class="sxs-lookup"><span data-stu-id="3ae8c-131">System.IDisposable</span></span>](/dotnet/api/System.IDisposable)

[<span data-ttu-id="3ae8c-132">Referenz zu Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ae8c-132">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
