---
ms.date: 09/13/2016
ms.topic: reference
title: Deklarieren von Cmdlet-Parametern
description: Deklarieren von Cmdlet-Parametern
ms.openlocfilehash: ed53f9788c9afb142b137e08966dff33551b9d0f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667095"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="69dd2-103">Deklarieren von Cmdlet-Parametern</span><span class="sxs-lookup"><span data-stu-id="69dd2-103">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="69dd2-104">In diesen Beispielen wird gezeigt, wie benannte, positionelle, erforderliche, optionale und Switch-Parameter deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="69dd2-104">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="69dd2-105">Diese Beispiele zeigen auch, wie ein parameteralias definiert wird.</span><span class="sxs-lookup"><span data-stu-id="69dd2-105">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="69dd2-106">Deklarieren eines benannten Parameters</span><span class="sxs-lookup"><span data-stu-id="69dd2-106">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="69dd2-107">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="69dd2-107">Define a public property as shown in the following code.</span></span> <span data-ttu-id="69dd2-108">Wenn Sie das Parameter Attribut hinzufügen, lassen Sie das- `Position` Schlüsselwort aus dem-Attribut Weg.</span><span class="sxs-lookup"><span data-stu-id="69dd2-108">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="69dd2-109">Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="69dd2-109">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="69dd2-110">Deklarieren eines Positions Parameters</span><span class="sxs-lookup"><span data-stu-id="69dd2-110">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="69dd2-111">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="69dd2-111">Define a public property as shown in the following code.</span></span> <span data-ttu-id="69dd2-112">Wenn Sie das Parameter-Attribut hinzufügen, legen Sie das- `Position` Schlüsselwort auf die Argument Position fest.</span><span class="sxs-lookup"><span data-stu-id="69dd2-112">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="69dd2-113">Der Wert 0 gibt die erste Position an.</span><span class="sxs-lookup"><span data-stu-id="69dd2-113">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="69dd2-114">Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="69dd2-114">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="69dd2-115">Deklarieren eines obligatorischen Parameters</span><span class="sxs-lookup"><span data-stu-id="69dd2-115">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="69dd2-116">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="69dd2-116">Define a public property as shown in the following code.</span></span> <span data-ttu-id="69dd2-117">Wenn Sie das Parameter-Attribut hinzufügen, legen Sie das- `Mandatory` Schlüsselwort auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="69dd2-117">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="69dd2-118">Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="69dd2-118">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="69dd2-119">So deklarieren Sie einen optionalen Parameter</span><span class="sxs-lookup"><span data-stu-id="69dd2-119">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="69dd2-120">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="69dd2-120">Define a public property as shown in the following code.</span></span> <span data-ttu-id="69dd2-121">Wenn Sie das Parameter Attribut hinzufügen, lassen Sie das `Mandatory` Schlüsselwort aus.</span><span class="sxs-lookup"><span data-stu-id="69dd2-121">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="69dd2-122">Deklarieren eines Switch-Parameters</span><span class="sxs-lookup"><span data-stu-id="69dd2-122">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="69dd2-123">Definieren Sie eine öffentliche Eigenschaft als Typ " [System. Management. Automation. Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter)", und deklarieren Sie dann das Parameter Attribut.</span><span class="sxs-lookup"><span data-stu-id="69dd2-123">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="69dd2-124">Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="69dd2-124">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="69dd2-125">Deklarieren eines Parameters mit Aliasen</span><span class="sxs-lookup"><span data-stu-id="69dd2-125">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="69dd2-126">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="69dd2-126">Define a public property as shown in the following code.</span></span> <span data-ttu-id="69dd2-127">Fügen Sie ein Alias Attribut hinzu, das die Aliase für den Parameter auflistet.</span><span class="sxs-lookup"><span data-stu-id="69dd2-127">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="69dd2-128">In diesem Beispiel werden drei Aliase für denselben Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="69dd2-128">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="69dd2-129">Der erste Alias stellt eine Verknüpfung bereit.</span><span class="sxs-lookup"><span data-stu-id="69dd2-129">The first alias provides a shortcut.</span></span> <span data-ttu-id="69dd2-130">Die zweite und dritte Aliase stellen Namen bereit, die Sie für verschiedene Szenarien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="69dd2-130">The second and third aliases provide names you can use for different scenarios.</span></span>

    ```csharp
    [Alias("UN","Writer","Editor")]
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="69dd2-131">Weitere Informationen zum Alias Attribut finden Sie unter [Alias Attribut Deklaration](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="69dd2-131">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="69dd2-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69dd2-132">See Also</span></span>

[<span data-ttu-id="69dd2-133">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="69dd2-133">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="69dd2-134">Attributdeklaration: Parameter</span><span class="sxs-lookup"><span data-stu-id="69dd2-134">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="69dd2-135">Attributdeklaration: Alias</span><span class="sxs-lookup"><span data-stu-id="69dd2-135">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="69dd2-136">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="69dd2-136">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
