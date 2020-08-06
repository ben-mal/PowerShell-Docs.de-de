---
title: Deklarieren von Cmdlet-Parametern | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 97e86a1eb715f149a8383a1a4529c00da4f0eba8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774387"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="61c0f-102">Deklarieren von Cmdlet-Parametern</span><span class="sxs-lookup"><span data-stu-id="61c0f-102">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="61c0f-103">In diesen Beispielen wird gezeigt, wie benannte, positionelle, erforderliche, optionale und Switch-Parameter deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="61c0f-103">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="61c0f-104">Diese Beispiele zeigen auch, wie ein parameteralias definiert wird.</span><span class="sxs-lookup"><span data-stu-id="61c0f-104">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="61c0f-105">Deklarieren eines benannten Parameters</span><span class="sxs-lookup"><span data-stu-id="61c0f-105">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="61c0f-106">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="61c0f-106">Define a public property as shown in the following code.</span></span> <span data-ttu-id="61c0f-107">Wenn Sie das Parameter Attribut hinzufügen, lassen Sie das- `Position` Schlüsselwort aus dem-Attribut Weg.</span><span class="sxs-lookup"><span data-stu-id="61c0f-107">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="61c0f-108">Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="61c0f-108">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="61c0f-109">Deklarieren eines Positions Parameters</span><span class="sxs-lookup"><span data-stu-id="61c0f-109">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="61c0f-110">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="61c0f-110">Define a public property as shown in the following code.</span></span> <span data-ttu-id="61c0f-111">Wenn Sie das Parameter-Attribut hinzufügen, legen Sie das- `Position` Schlüsselwort auf die Argument Position fest.</span><span class="sxs-lookup"><span data-stu-id="61c0f-111">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="61c0f-112">Der Wert 0 gibt die erste Position an.</span><span class="sxs-lookup"><span data-stu-id="61c0f-112">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="61c0f-113">Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="61c0f-113">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="61c0f-114">Deklarieren eines obligatorischen Parameters</span><span class="sxs-lookup"><span data-stu-id="61c0f-114">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="61c0f-115">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="61c0f-115">Define a public property as shown in the following code.</span></span> <span data-ttu-id="61c0f-116">Wenn Sie das Parameter-Attribut hinzufügen, legen Sie das- `Mandatory` Schlüsselwort auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="61c0f-116">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="61c0f-117">Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="61c0f-117">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="61c0f-118">So deklarieren Sie einen optionalen Parameter</span><span class="sxs-lookup"><span data-stu-id="61c0f-118">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="61c0f-119">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="61c0f-119">Define a public property as shown in the following code.</span></span> <span data-ttu-id="61c0f-120">Wenn Sie das Parameter Attribut hinzufügen, lassen Sie das `Mandatory` Schlüsselwort aus.</span><span class="sxs-lookup"><span data-stu-id="61c0f-120">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="61c0f-121">Deklarieren eines Switch-Parameters</span><span class="sxs-lookup"><span data-stu-id="61c0f-121">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="61c0f-122">Definieren Sie eine öffentliche Eigenschaft als Typ " [System. Management. Automation. Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter)", und deklarieren Sie dann das Parameter Attribut.</span><span class="sxs-lookup"><span data-stu-id="61c0f-122">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="61c0f-123">Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="61c0f-123">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="61c0f-124">Deklarieren eines Parameters mit Aliasen</span><span class="sxs-lookup"><span data-stu-id="61c0f-124">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="61c0f-125">Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="61c0f-125">Define a public property as shown in the following code.</span></span> <span data-ttu-id="61c0f-126">Fügen Sie ein Alias Attribut hinzu, das die Aliase für den Parameter auflistet.</span><span class="sxs-lookup"><span data-stu-id="61c0f-126">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="61c0f-127">In diesem Beispiel werden drei Aliase für denselben Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="61c0f-127">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="61c0f-128">Der erste Alias stellt eine Verknüpfung bereit.</span><span class="sxs-lookup"><span data-stu-id="61c0f-128">The first alias provides a shortcut.</span></span> <span data-ttu-id="61c0f-129">Die zweite und dritte Aliase stellen Namen bereit, die Sie für verschiedene Szenarien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="61c0f-129">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="61c0f-130">Weitere Informationen zum Alias Attribut finden Sie unter [Alias Attribut Deklaration](./alias-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="61c0f-130">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="61c0f-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61c0f-131">See Also</span></span>

[<span data-ttu-id="61c0f-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="61c0f-132">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="61c0f-133">Attributdeklaration: Parameter</span><span class="sxs-lookup"><span data-stu-id="61c0f-133">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="61c0f-134">Attributdeklaration: Alias</span><span class="sxs-lookup"><span data-stu-id="61c0f-134">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="61c0f-135">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="61c0f-135">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
