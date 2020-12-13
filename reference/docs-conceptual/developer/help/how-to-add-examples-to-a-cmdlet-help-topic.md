---
ms.date: 09/12/2016
ms.topic: reference
title: Hinzufügen von Beispielen zu einem Cmdlet-Hilfethema
description: Hinzufügen von Beispielen zu einem Cmdlet-Hilfethema
ms.openlocfilehash: 6b72e29c93740b7953d9b68fc8e68c02eb2f4dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654718"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a><span data-ttu-id="528a0-103">Hinzufügen von Beispielen zu einem Cmdlet-Hilfethema</span><span class="sxs-lookup"><span data-stu-id="528a0-103">How to Add Examples to a Cmdlet Help Topic</span></span>

## <a name="things-to-know-about-examples-in-cmdlet-help"></a><span data-ttu-id="528a0-104">Informationen zu Beispielen in der Cmdlet-Hilfe</span><span class="sxs-lookup"><span data-stu-id="528a0-104">Things to Know about Examples in Cmdlet Help</span></span>

- <span data-ttu-id="528a0-105">Listet alle Parameternamen im Befehl auf, auch wenn die Parameternamen optional sind.</span><span class="sxs-lookup"><span data-stu-id="528a0-105">List all of the parameter names in the command, even when the parameter names are optional.</span></span> <span data-ttu-id="528a0-106">Dies unterstützt den Benutzer dabei, den Befehl problemlos zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="528a0-106">This helps the user to interpret the command easily.</span></span>

- <span data-ttu-id="528a0-107">Vermeiden Sie Aliase und partielle Parameternamen, auch wenn Sie in PowerShell funktionieren.</span><span class="sxs-lookup"><span data-stu-id="528a0-107">Avoid aliases and partial parameter names, even though they work in PowerShell.</span></span>

- <span data-ttu-id="528a0-108">Erläutern Sie in der Beispiel Beschreibung das rationale für die Konstruktion des Befehls.</span><span class="sxs-lookup"><span data-stu-id="528a0-108">In the example description, explain the rational for the construction of the command.</span></span> <span data-ttu-id="528a0-109">Erläutern Sie, warum Sie bestimmte Parameter und Werte ausgewählt haben und wie Sie Variablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="528a0-109">Explain why you chose particular parameters and values, and how you use variables.</span></span>

- <span data-ttu-id="528a0-110">Wenn der Befehl Ausdrücke verwendet, erklären Sie diese ausführlich.</span><span class="sxs-lookup"><span data-stu-id="528a0-110">If the command uses expressions, explain them in detail.</span></span>

- <span data-ttu-id="528a0-111">Wenn der Befehl Eigenschaften und Methoden von Objekten verwendet, insbesondere Eigenschaften, die nicht in der Standard Anzeige angezeigt werden, verwenden Sie das Beispiel als Gelegenheit, um den Benutzer über das Objekt zu informieren.</span><span class="sxs-lookup"><span data-stu-id="528a0-111">If the command uses properties and methods of objects, especially properties that do not appear in the default display, use the example as an opportunity tell the user about the object.</span></span>

## <a name="help-views-that-display-examples"></a><span data-ttu-id="528a0-112">Hilfe Ansichten, in denen Beispiele angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="528a0-112">Help Views that Display Examples</span></span>

<span data-ttu-id="528a0-113">Beispiele werden nur in den ausführlichen und vollständigen Ansichten der Cmdlet-Hilfe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="528a0-113">Examples appear only in the Detailed and Full views of cmdlet Help.</span></span>

## <a name="adding-an-examples-node"></a><span data-ttu-id="528a0-114">Hinzufügen eines Knotens für Beispiele</span><span class="sxs-lookup"><span data-stu-id="528a0-114">Adding an Examples Node</span></span>

<span data-ttu-id="528a0-115">Der folgende XML-Code zeigt, wie ein **Beispiele** -Knoten hinzugefügt wird, der einen einzelnen **Beispiel** Knoten enthält.</span><span class="sxs-lookup"><span data-stu-id="528a0-115">The following XML shows how to add an **Examples** node that contains a single **Example** node.</span></span> <span data-ttu-id="528a0-116">Fügen Sie zusätzliche Beispiel Knoten für die einzelnen Beispiele hinzu, die Sie in das Thema einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="528a0-116">Add additional example nodes for each examples you want to include in the topic.</span></span>

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a><span data-ttu-id="528a0-117">Hinzufügen eines Beispiel Titels</span><span class="sxs-lookup"><span data-stu-id="528a0-117">Adding an Example Title</span></span>

<span data-ttu-id="528a0-118">Der folgende XML-Code zeigt, wie Sie einen **Titel** für das Beispiel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="528a0-118">The following XML shows how to add a **title** for the example.</span></span> <span data-ttu-id="528a0-119">Der **Titel** wird verwendet, um das Beispiel von anderen Beispielen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="528a0-119">The **title** is used to set the example apart from other examples.</span></span> <span data-ttu-id="528a0-120">PowerShell verwendet einen Standard Header, der eine sequenzielle Beispiel Zahl enthält.</span><span class="sxs-lookup"><span data-stu-id="528a0-120">PowerShell uses a standard header that includes a sequential example number.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a><span data-ttu-id="528a0-121">Hinzufügen vorheriger Zeichen</span><span class="sxs-lookup"><span data-stu-id="528a0-121">Adding Preceding Characters</span></span>

<span data-ttu-id="528a0-122">Der folgende XML-Code zeigt, wie Sie Zeichen hinzufügen, z. b. die Windows PowerShell-Eingabeaufforderung, die unmittelbar vor dem Beispiel Befehl (ohne dazwischen liegende Leerzeichen) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="528a0-122">The following XML shows how to add characters, such as the Windows PowerShell prompt, that are displayed immediately before the example command (without any intervening spaces).</span></span> <span data-ttu-id="528a0-123">PowerShell verwendet die Windows PowerShell-Eingabeaufforderung: `C:\PS>` .</span><span class="sxs-lookup"><span data-stu-id="528a0-123">PowerShell uses the Windows PowerShell prompt: `C:\PS>`.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
</command:example>
</command:examples>
```

## <a name="adding-the-command"></a><span data-ttu-id="528a0-124">Hinzufügen des Befehls</span><span class="sxs-lookup"><span data-stu-id="528a0-124">Adding the Command</span></span>

<span data-ttu-id="528a0-125">Der folgende XML-Code zeigt, wie der tatsächliche Befehl des Beispiels hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="528a0-125">The following XML shows how to add the actual command of the example.</span></span> <span data-ttu-id="528a0-126">Wenn Sie den Befehl hinzufügen, geben Sie den vollständigen Namen (keinen Alias verwenden) von Cmdlets und Parametern ein.</span><span class="sxs-lookup"><span data-stu-id="528a0-126">When adding the command, type the entire name (do not use alias) of cmdlets and parameters.</span></span> <span data-ttu-id="528a0-127">Verwenden Sie nach Möglichkeit auch Kleinbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="528a0-127">Also, use lowercase characters whenever possible.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
</command:example>
</command:examples>
```

## <a name="adding-a-description"></a><span data-ttu-id="528a0-128">Hinzufügen einer Beschreibung</span><span class="sxs-lookup"><span data-stu-id="528a0-128">Adding a Description</span></span>

<span data-ttu-id="528a0-129">Der folgende XML-Code zeigt, wie eine Beschreibung für das Beispiel hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="528a0-129">The following XML shows how to add a description for the example.</span></span> <span data-ttu-id="528a0-130">PowerShell verwendet einen einzelnen Satz von `<maml:para>` Tags für die Beschreibung, auch wenn mehrere `<maml:para>` Tags verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="528a0-130">PowerShell uses a single set of `<maml:para>` tags for the description, even though multiple `<maml:para>` tags can be used.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
    </dev:remarks>
</command:example>
</command:examples>
```

## <a name="adding-example-output"></a><span data-ttu-id="528a0-131">Hinzufügen einer Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="528a0-131">Adding Example Output</span></span>

<span data-ttu-id="528a0-132">Der folgende XML-Code zeigt, wie die Ausgabe des Befehls hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="528a0-132">The following XML shows how to add the output of the command.</span></span> <span data-ttu-id="528a0-133">Die Befehls Ergebnisinformationen sind optional, aber in einigen Fällen ist es hilfreich, die Auswirkungen der Verwendung bestimmter Parameter zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="528a0-133">The command results information is optional, but in some cases it is helpful to demonstrate the effect of using specific parameters.</span></span>
<span data-ttu-id="528a0-134">PowerShell verwendet zwei Sätze von leeren `<maml:para>` Tags, um die Befehlsausgabe des Befehls zu trennen.</span><span class="sxs-lookup"><span data-stu-id="528a0-134">PowerShell uses two sets of blank `<maml:para>` tags to separate the command output from the command.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
      <maml:para></maml:para>
      <maml:para></maml:para>
      <maml:para> command output </maml:para>
</dev:remarks>
</command:example>
</command:examples>
```
