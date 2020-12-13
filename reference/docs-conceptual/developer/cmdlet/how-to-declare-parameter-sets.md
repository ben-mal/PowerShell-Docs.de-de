---
ms.date: 09/13/2016
ms.topic: reference
title: Deklarieren von Parametersätzen
description: Deklarieren von Parametersätzen
ms.openlocfilehash: bd4d504a9fe6c7f7626901c49bc08851244f0995
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667061"
---
# <a name="how-to-declare-parameter-sets"></a><span data-ttu-id="8fab3-103">Deklarieren von Parametersätzen</span><span class="sxs-lookup"><span data-stu-id="8fab3-103">How to Declare Parameter Sets</span></span>

<span data-ttu-id="8fab3-104">In diesem Beispiel wird gezeigt, wie zwei Parametersätze definiert werden, wenn Sie die Parameter für ein Cmdlet deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8fab3-104">This example shows how to define two parameter sets when you declare the parameters for a cmdlet.</span></span> <span data-ttu-id="8fab3-105">Jeder Parametersatz verfügt sowohl über einen eindeutigen Parameter als auch über einen freigegebenen Parameter, der von beiden Parametersätzen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8fab3-105">Each parameter set has both a unique parameter and a shared parameter that is used by both parameter sets.</span></span> <span data-ttu-id="8fab3-106">Weitere Informationen zu Parametersätzen, einschließlich der Angabe des Standardparameter Satzes, finden Sie unter [Cmdlet-Parametersätze](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="8fab3-106">For more information about parameters sets, including how to specify the default parameter set, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fab3-107">Definieren Sie nach Möglichkeit den eindeutigen Parameter eines Parameter Satzes als erforderlichen Parameter.</span><span class="sxs-lookup"><span data-stu-id="8fab3-107">Whenever possible, define the unique parameter of a parameter set as a required parameter.</span></span> <span data-ttu-id="8fab3-108">Wenn Sie jedoch möchten, dass das Cmdlet ohne Angabe von Parametern ausgeführt wird, kann der Unique-Parameter ein optionaler Parameter sein.</span><span class="sxs-lookup"><span data-stu-id="8fab3-108">However, if you want your cmdlet to run without specifying any parameters, the unique parameter can be an optional parameter.</span></span> <span data-ttu-id="8fab3-109">Beispielsweise ist der Unique-Parameter des `Get-Command` Cmdlets optional.</span><span class="sxs-lookup"><span data-stu-id="8fab3-109">For example, the unique parameter of the `Get-Command` cmdlet is optional.</span></span>

## <a name="how-to-define-two-parameter-sets"></a><span data-ttu-id="8fab3-110">Definieren von zwei Parameter Sätzen</span><span class="sxs-lookup"><span data-stu-id="8fab3-110">How to Define Two Parameter Sets</span></span>

1. <span data-ttu-id="8fab3-111">Fügen Sie dem `ParameterSet` Parameter-Attribut für den Unique-Parameter des ersten Parameter Satzes das-Schlüsselwort hinzu.</span><span class="sxs-lookup"><span data-stu-id="8fab3-111">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the first parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test01")]
   public string UserName
   {
     get { return userName; }
     set { userName = value; }
   }
   private string userName;
   ```

2. <span data-ttu-id="8fab3-112">Fügen Sie das- `ParameterSet` Schlüsselwort zum Parameter-Attribut für den eindeutigen Parameter des zweiten Parameter Satzes hinzu.</span><span class="sxs-lookup"><span data-stu-id="8fab3-112">Add the `ParameterSet` keyword to the Parameter attribute for the unique parameter of the second parameter set.</span></span>

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test02")]
   public string ComputerName
   {
     get { return computerName; }
     set { computerName = value; }
   }
   private string computerName;
   ```

3. <span data-ttu-id="8fab3-113">Fügen Sie für den Parameter, der zu beiden Parametersätzen gehört, ein Parameter Attribut für jeden Parametersatz hinzu, und fügen Sie dann `ParameterSet` jedem Satz das Schlüsselwort hinzu.</span><span class="sxs-lookup"><span data-stu-id="8fab3-113">For the parameter that belongs to both parameter sets, add a Parameter attribute for each parameter set and then add the `ParameterSet` keyword to each set.</span></span> <span data-ttu-id="8fab3-114">In jedem Parameter Attribut können Sie angeben, wie dieser Parameter definiert wird.</span><span class="sxs-lookup"><span data-stu-id="8fab3-114">In each Parameter attribute, you can specify how that parameter is defined.</span></span> <span data-ttu-id="8fab3-115">Ein Parameter kann in einem Satz optional sein und in einem anderen obligatorisch sein.</span><span class="sxs-lookup"><span data-stu-id="8fab3-115">A parameter can be optional in one set and mandatory in another.</span></span>

   ```csharp
   [Parameter(Mandatory= true, ParameterSetName = "Test01")]
   [Parameter(ParameterSetName = "Test02")]
   public string SharedParam
   {
       get { return sharedParam; }
       set { sharedParam = value; }
   }
   private string sharedParam;
   ```

## <a name="see-also"></a><span data-ttu-id="8fab3-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8fab3-116">See Also</span></span>

[<span data-ttu-id="8fab3-117">Cmdlet-Parametersätze</span><span class="sxs-lookup"><span data-stu-id="8fab3-117">Cmdlet Parameter Sets</span></span>](./cmdlet-parameter-sets.md)

[<span data-ttu-id="8fab3-118">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="8fab3-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
