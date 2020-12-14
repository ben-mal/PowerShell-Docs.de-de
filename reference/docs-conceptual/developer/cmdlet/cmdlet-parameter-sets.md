---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet-Parametersätze
description: Cmdlet-Parametersätze
ms.openlocfilehash: e84af7faf5b7459d8dbe06847526efe804e2c5e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668285"
---
# <a name="cmdlet-parameter-sets"></a><span data-ttu-id="385e1-103">Cmdlet-Parametersätze</span><span class="sxs-lookup"><span data-stu-id="385e1-103">Cmdlet parameter sets</span></span>

<span data-ttu-id="385e1-104">PowerShell verwendet Parametersätze, damit Sie ein einzelnes Cmdlet schreiben können, das verschiedene Aktionen für verschiedene Szenarien ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="385e1-104">PowerShell uses parameter sets to enable you to write a single cmdlet that can do different actions for different scenarios.</span></span> <span data-ttu-id="385e1-105">Parametersätze ermöglichen es Ihnen, dem Benutzer verschiedene Parameter verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="385e1-105">Parameter sets enable you to expose different parameters to the user.</span></span> <span data-ttu-id="385e1-106">Und, um basierend auf den vom Benutzer angegebenen Parametern unterschiedliche Informationen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="385e1-106">And, to return different information based on the parameters specified by the user.</span></span>

## <a name="examples-of-parameter-sets"></a><span data-ttu-id="385e1-107">Beispiele für Parametersätze</span><span class="sxs-lookup"><span data-stu-id="385e1-107">Examples of parameter sets</span></span>

<span data-ttu-id="385e1-108">Das PowerShell- `Get-EventLog` Cmdlet gibt beispielsweise unterschiedliche Informationen zurück, je nachdem, ob der Benutzer den **List** -oder **logName** -Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="385e1-108">For example, the PowerShell `Get-EventLog` cmdlet returns different information depending on whether the user specifies the **List** or **LogName** parameter.</span></span> <span data-ttu-id="385e1-109">Wenn der **List** -Parameter angegeben wird, gibt das Cmdlet Informationen zu den Protokolldateien selbst zurück, jedoch nicht zu den darin enthaltenen Ereignis Informationen.</span><span class="sxs-lookup"><span data-stu-id="385e1-109">If the **List** parameter is specified, the cmdlet returns information about the log files themselves but not the event information they contain.</span></span> <span data-ttu-id="385e1-110">Wenn der **logName** -Parameter angegeben wird, gibt das Cmdlet Informationen zu den Ereignissen in einem bestimmten Ereignisprotokoll zurück.</span><span class="sxs-lookup"><span data-stu-id="385e1-110">If the **LogName** parameter is specified, the cmdlet returns information about the events in a specific event log.</span></span> <span data-ttu-id="385e1-111">Mit den Parametern **List** und **logName** werden zwei separate Parametersätze identifiziert.</span><span class="sxs-lookup"><span data-stu-id="385e1-111">The **List** and **LogName** parameters identify two separate parameter sets.</span></span>

## <a name="unique-parameter"></a><span data-ttu-id="385e1-112">Unique-Parameter</span><span class="sxs-lookup"><span data-stu-id="385e1-112">Unique parameter</span></span>

<span data-ttu-id="385e1-113">Jeder Parametersatz muss über einen eindeutigen Parameter verfügen, der von der PowerShell-Laufzeit verwendet wird, um den entsprechenden Parametersatz verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="385e1-113">Each parameter set must have a unique parameter that the PowerShell runtime uses to expose the appropriate parameter set.</span></span> <span data-ttu-id="385e1-114">Wenn möglich, sollte der Unique-Parameter ein obligatorischer Parameter sein.</span><span class="sxs-lookup"><span data-stu-id="385e1-114">If possible, the unique parameter should be a mandatory parameter.</span></span> <span data-ttu-id="385e1-115">Wenn ein Parameter obligatorisch ist, muss der Benutzer den-Parameter angeben, und die PowerShell-Laufzeit verwendet diesen Parameter, um den Parametersatz zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="385e1-115">When a parameter is mandatory, the user must specify the parameter, and the PowerShell runtime uses that parameter to identify the parameter set.</span></span> <span data-ttu-id="385e1-116">Der Unique-Parameter kann nicht obligatorisch sein, wenn das Cmdlet ohne Angabe von Parametern ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="385e1-116">The unique parameter can't be mandatory if your cmdlet is designed to run without specifying any parameters.</span></span>

## <a name="multiple-parameter-sets"></a><span data-ttu-id="385e1-117">Mehrere Parametersätze</span><span class="sxs-lookup"><span data-stu-id="385e1-117">Multiple parameter sets</span></span>

<span data-ttu-id="385e1-118">In der folgenden Abbildung werden in der linken Spalte drei gültige Parametersätze angezeigt.</span><span class="sxs-lookup"><span data-stu-id="385e1-118">In the following illustration, the left column shows three valid parameter sets.</span></span> <span data-ttu-id="385e1-119">Der **Parameter a** ist eindeutig für den ersten Parametersatz, der **Parameter B** ist für den zweiten Parametersatz eindeutig, und der **Parameter C** ist für den dritten Parametersatz eindeutig.</span><span class="sxs-lookup"><span data-stu-id="385e1-119">**Parameter A** is unique to the first parameter set, **parameter B** is unique to the second parameter set, and **parameter C** is unique to the third parameter set.</span></span> <span data-ttu-id="385e1-120">In der rechten Spalte haben die Parametersätze keinen eindeutigen Parameter.</span><span class="sxs-lookup"><span data-stu-id="385e1-120">In the right column, the parameter sets don't have a unique parameter.</span></span>

![Abbildung von Parametersätzen](media/cmdlet-parameter-sets/ps-parametersets.gif)

## <a name="parameter-set-requirements"></a><span data-ttu-id="385e1-122">Parameter Satz Anforderungen</span><span class="sxs-lookup"><span data-stu-id="385e1-122">Parameter set requirements</span></span>

<span data-ttu-id="385e1-123">Die folgenden Anforderungen gelten für alle Parametersätze.</span><span class="sxs-lookup"><span data-stu-id="385e1-123">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="385e1-124">Jeder Parametersatz muss mindestens einen eindeutigen Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="385e1-124">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="385e1-125">Wenn möglich, machen Sie diesen Parameter zu einem obligatorischen Parameter.</span><span class="sxs-lookup"><span data-stu-id="385e1-125">If possible, make this parameter a mandatory parameter.</span></span>

- <span data-ttu-id="385e1-126">Ein Parametersatz, der mehrere Positions Parameter enthält, muss eindeutige Positionen für jeden Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="385e1-126">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="385e1-127">Es können nicht zwei Positions Parameter dieselbe Position angeben.</span><span class="sxs-lookup"><span data-stu-id="385e1-127">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="385e1-128">Nur ein Parameter in einer Menge kann das- `ValueFromPipeline` Schlüsselwort mit dem Wert deklarieren `true` .</span><span class="sxs-lookup"><span data-stu-id="385e1-128">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span>
  <span data-ttu-id="385e1-129">Mehrere Parameter können das `ValueFromPipelineByPropertyName` Schlüsselwort mit dem Wert definieren `true` .</span><span class="sxs-lookup"><span data-stu-id="385e1-129">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="385e1-130">Wenn für einen Parameter kein Parametersatz angegeben ist, gehört der Parameter zu allen Parametersätzen.</span><span class="sxs-lookup"><span data-stu-id="385e1-130">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

> [!NOTE]
> <span data-ttu-id="385e1-131">Für ein Cmdlet oder eine Funktion gibt es ein Limit von 32-Parametersätzen.</span><span class="sxs-lookup"><span data-stu-id="385e1-131">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="385e1-132">Standardparameter Sätze</span><span class="sxs-lookup"><span data-stu-id="385e1-132">Default parameter sets</span></span>

<span data-ttu-id="385e1-133">Wenn mehrere Parametersätze definiert sind, können Sie das- `DefaultParameterSetName` Schlüsselwort des **Cmdlet** -Attributs verwenden, um den Standardparameter Satz anzugeben.</span><span class="sxs-lookup"><span data-stu-id="385e1-133">When multiple parameter sets are defined, you can use the `DefaultParameterSetName` keyword of the **Cmdlet** attribute to specify the default parameter set.</span></span> <span data-ttu-id="385e1-134">PowerShell verwendet den Standardparameter Satz, wenn der festgelegte Parameter auf der Grundlage der vom Befehl bereitgestellten Informationen nicht bestimmt werden kann.</span><span class="sxs-lookup"><span data-stu-id="385e1-134">PowerShell uses the default parameter set if it can't determine the parameter set to use based on the information provided by the command.</span></span> <span data-ttu-id="385e1-135">Weitere Informationen zum **Cmdlet** -Attribut finden Sie unter [Cmdlet-Attribut Deklaration](./cmdlet-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="385e1-135">For more information about the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="385e1-136">Deklarieren von Parametersätzen</span><span class="sxs-lookup"><span data-stu-id="385e1-136">Declaring parameter sets</span></span>

<span data-ttu-id="385e1-137">Um einen Parametersatz zu erstellen, müssen Sie das- `ParameterSetName` Schlüsselwort angeben, wenn Sie das **Parameter** Attribut für jeden Parameter im Parametersatz deklarieren.</span><span class="sxs-lookup"><span data-stu-id="385e1-137">To create a parameter set, you must specify the `ParameterSetName` keyword when you declare the **Parameter** attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="385e1-138">Fügen Sie für Parameter, die mehreren Parametersätzen angehören, ein **Parameter** Attribut für jeden Parametersatz hinzu.</span><span class="sxs-lookup"><span data-stu-id="385e1-138">For parameters that belong to multiple parameter sets, add a **Parameter** attribute for each parameter set.</span></span> <span data-ttu-id="385e1-139">Mit diesem Attribut können Sie den Parameter für jeden Parametersatz anders definieren.</span><span class="sxs-lookup"><span data-stu-id="385e1-139">This attribute enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="385e1-140">Beispielsweise können Sie einen Parameter in einem Satz als obligatorisch definieren und optional in einem anderen.</span><span class="sxs-lookup"><span data-stu-id="385e1-140">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="385e1-141">Jeder Parametersatz muss jedoch einen eindeutigen Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="385e1-141">However, each parameter set must contain one unique parameter.</span></span> <span data-ttu-id="385e1-142">Weitere Informationen finden Sie unter [Parameter Attribut Deklaration](parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="385e1-142">For more information, see [Parameter Attribute Declaration](parameter-attribute-declaration.md).</span></span>

<span data-ttu-id="385e1-143">Im folgenden Beispiel ist der **username** -Parameter der eindeutige Parameter des `Test01` Parameter Satzes, und der **Computername** -Parameter ist der eindeutige Parameter des `Test02` Parameter Satzes.</span><span class="sxs-lookup"><span data-stu-id="385e1-143">In the following example, the **UserName** parameter is the unique parameter of the `Test01` parameter set, and the **ComputerName** parameter is the unique parameter of the `Test02` parameter set.</span></span> <span data-ttu-id="385e1-144">Der **sharedparam** -Parameter gehört zu beiden Sätzen und ist für den `Test01` Parametersatz obligatorisch, aber optional für den `Test02` Parametersatz.</span><span class="sxs-lookup"><span data-stu-id="385e1-144">The **SharedParam** parameter belongs to both sets and is mandatory for the `Test01` parameter set but optional for the `Test02` parameter set.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true, ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;

[Parameter(Position = 0, Mandatory = true, ParameterSetName = "Test02")]
public string ComputerName
{
  get { return computerName; }
  set { computerName = value; }
}
private string computerName;

[Parameter(Mandatory= true, ParameterSetName = "Test01")]
[Parameter(ParameterSetName = "Test02")]
public string SharedParam
{
    get { return sharedParam; }
    set { sharedParam = value; }
}
private string sharedParam;
```
