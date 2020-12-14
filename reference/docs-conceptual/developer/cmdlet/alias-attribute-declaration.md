---
ms.date: 09/13/2016
ms.topic: reference
title: 'Attributdeklaration: Alias'
description: 'Attributdeklaration: Alias'
ms.openlocfilehash: f2fe49578da2c795643b1f80fa44deefe1dbff09
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668302"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="b2929-103">Attributdeklaration: Alias</span><span class="sxs-lookup"><span data-stu-id="b2929-103">Alias Attribute Declaration</span></span>

<span data-ttu-id="b2929-104">Das Alias-Attribut ermöglicht es dem Benutzer, unterschiedliche Namen für einen Cmdlet-Parameter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b2929-104">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="b2929-105">Aliase können verwendet werden, um Verknüpfungen für einen Parameternamen bereitzustellen, oder Sie können unterschiedliche Namen bereitstellen, die für unterschiedliche Szenarien geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="b2929-105">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2929-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2929-106">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="b2929-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2929-107">Parameters</span></span>

<span data-ttu-id="b2929-108">`aliasName` (Zeichenfolge []) Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b2929-108">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="b2929-109">Gibt eine Reihe von durch Trennzeichen getrennten Aliasnamen für den Cmdlet-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b2929-109">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2929-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b2929-110">Remarks</span></span>

- <span data-ttu-id="b2929-111">Das Alias-Attribut wird mit dem Parameter-Attribut verwendet, wenn Sie einen Cmdlet-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="b2929-111">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="b2929-112">Weitere Informationen zum Deklarieren dieser Attribute finden Sie unter [Deklarieren von Cmdlet-Parametern](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b2929-112">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="b2929-113">Jeder Aliasname muss innerhalb eines Cmdlets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="b2929-113">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="b2929-114">Windows PowerShell prüft nicht, ob doppelte Aliasnamen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b2929-114">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="b2929-115">Das Alias-Attribut wird für jeden Parameter in einem Cmdlet einmal verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2929-115">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="b2929-116">Das Alias-Attribut wird von der [System. Management. Automation. Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="b2929-116">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2929-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2929-117">See Also</span></span>

[<span data-ttu-id="b2929-118">Parameteraliase</span><span class="sxs-lookup"><span data-stu-id="b2929-118">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="b2929-119">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b2929-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
