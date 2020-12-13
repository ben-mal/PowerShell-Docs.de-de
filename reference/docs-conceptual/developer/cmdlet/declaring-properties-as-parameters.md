---
ms.date: 09/13/2016
ms.topic: reference
title: Deklarieren von Eigenschaften als Parameter
description: Deklarieren von Eigenschaften als Parameter
ms.openlocfilehash: ade7928e2ca277da8bbd1a5e04997bd1d05f1e5d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653160"
---
# <a name="declaring-properties-as-parameters"></a><span data-ttu-id="993a8-103">Deklarieren von Eigenschaften als Parameter</span><span class="sxs-lookup"><span data-stu-id="993a8-103">Declaring Properties as Parameters</span></span>

<span data-ttu-id="993a8-104">Dieses Thema enthält grundlegende Informationen, die Sie kennen müssen, bevor Sie die Parameter eines Cmdlets deklarieren.</span><span class="sxs-lookup"><span data-stu-id="993a8-104">This topic provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="993a8-105">Um die Parameter eines Cmdlets in der Cmdlet-Klasse zu deklarieren, definieren Sie die öffentlichen Eigenschaften, die die einzelnen Parameter darstellen, und fügen Sie jeder Eigenschaft ein oder mehrere Parameter Attribute hinzu.</span><span class="sxs-lookup"><span data-stu-id="993a8-105">To declare the parameters of a cmdlet within your cmdlet class, define the public properties that represent each parameter, and then add one or more Parameter attributes to each property.</span></span> <span data-ttu-id="993a8-106">Die Windows PowerShell-Laufzeit verwendet die Parameter Attribute, um die Eigenschaft als Cmdlet-Parameter zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="993a8-106">The Windows PowerShell runtime uses the Parameter attributes to identify the property as a cmdlet parameter.</span></span> <span data-ttu-id="993a8-107">Die grundlegende Syntax zum Deklarieren des Parameter Attributs ist `[Parameter()]` .</span><span class="sxs-lookup"><span data-stu-id="993a8-107">The basic syntax for declaring the Parameter attribute is `[Parameter()]`.</span></span>

<span data-ttu-id="993a8-108">Im folgenden finden Sie ein Beispiel für eine Eigenschaft, die als erforderlicher Parameter definiert ist.</span><span class="sxs-lookup"><span data-stu-id="993a8-108">Here is an example of a property defined as a required parameter.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="993a8-109">Im folgenden finden Sie einige Dinge, die Sie über Parameter berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="993a8-109">Here are some things to remember about parameters.</span></span>

- <span data-ttu-id="993a8-110">Ein Parameter muss explizit als public gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="993a8-110">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="993a8-111">Parameter, die nicht als öffentlich gekennzeichnet sind, sind standardmäßig intern und werden von der Windows PowerShell-Laufzeit nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="993a8-111">Parameters that are not marked as public default to internal and will not be found by the Windows PowerShell runtime.</span></span>

- <span data-ttu-id="993a8-112">Parameter sollten als Microsoft .NET Frameworktypen definiert werden, um eine bessere Parameter Validierung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="993a8-112">Parameters should be defined as Microsoft .NET Framework types to provide better parameter validation.</span></span> <span data-ttu-id="993a8-113">Beispielsweise sollten Parameter, die auf einen Wert aus einer Menge von Werten beschränkt sind, als Enumerationstyp definiert werden.</span><span class="sxs-lookup"><span data-stu-id="993a8-113">For example, parameters that are restricted to one value out of a set of values should be defined as an enumeration type.</span></span> <span data-ttu-id="993a8-114">Parameter, die einen Uniform Resource Identifier-Wert (URI) annehmen, müssen den Typ " [System. Uri](/dotnet/api/System.Uri)" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="993a8-114">Parameters that take a Uniform Resource Identifier (URI) value should be of type [System.Uri](/dotnet/api/System.Uri).</span></span>

- <span data-ttu-id="993a8-115">Vermeiden Sie grundlegende Zeichen folgen Parameter für alle außer frei Form Texteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="993a8-115">Avoid basic string parameters for all but free-form text properties.</span></span>

- <span data-ttu-id="993a8-116">Sie können einem Parameter eine beliebige Anzahl von Parametersätzen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="993a8-116">You can add a parameter to any number of parameter sets.</span></span> <span data-ttu-id="993a8-117">Weitere Informationen zu Parametersätzen finden Sie unter [Cmdlet-Parametersätze](./cmdlet-parameter-sets.md).</span><span class="sxs-lookup"><span data-stu-id="993a8-117">For more information about parameter sets, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

<span data-ttu-id="993a8-118">Windows PowerShell bietet auch eine Reihe allgemeiner Parameter, die für jedes Cmdlet automatisch verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="993a8-118">Windows PowerShell also provides a set of common parameters that are automatically available to every cmdlet.</span></span> <span data-ttu-id="993a8-119">Weitere Informationen zu diesen Parametern und ihren Aliasen finden [Sie unter Allgemeine Cmdlet-Parameter](./common-parameter-names.md).</span><span class="sxs-lookup"><span data-stu-id="993a8-119">For more information about these parameters and their aliases, see [Cmdlet Common Parameters](./common-parameter-names.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="993a8-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="993a8-120">See Also</span></span>

[<span data-ttu-id="993a8-121">Allgemeine Cmdlet-Parameter</span><span class="sxs-lookup"><span data-stu-id="993a8-121">Cmdlet Common Parameters</span></span>](./common-parameter-names.md)

[<span data-ttu-id="993a8-122">Typen von Cmdlet-Parametern</span><span class="sxs-lookup"><span data-stu-id="993a8-122">Types of Cmdlet Parameter</span></span>](./types-of-cmdlet-parameters.md)

[<span data-ttu-id="993a8-123">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="993a8-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
