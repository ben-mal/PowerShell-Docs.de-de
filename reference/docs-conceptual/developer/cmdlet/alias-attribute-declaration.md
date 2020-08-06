---
title: Alias Attribut Deklaration | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- Alias attribute
- attributes, Alias
- Alias attribute, described
ms.openlocfilehash: 4c1ff34a244611173ca919a44d6598189b19dc98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782411"
---
# <a name="alias-attribute-declaration"></a><span data-ttu-id="03656-102">Attributdeklaration: Alias</span><span class="sxs-lookup"><span data-stu-id="03656-102">Alias Attribute Declaration</span></span>

<span data-ttu-id="03656-103">Das Alias-Attribut ermöglicht es dem Benutzer, unterschiedliche Namen für einen Cmdlet-Parameter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03656-103">The Alias attribute allows the user to specify different names for a cmdlet parameter.</span></span> <span data-ttu-id="03656-104">Aliase können verwendet werden, um Verknüpfungen für einen Parameternamen bereitzustellen, oder Sie können unterschiedliche Namen bereitstellen, die für unterschiedliche Szenarien geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="03656-104">Aliases can be used to provide shortcuts for a parameter name, or they can provide different names that are appropriate for different scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="03656-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="03656-105">Syntax</span></span>

```csharp
[Alias(aliasNames)]
```

#### <a name="parameters"></a><span data-ttu-id="03656-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="03656-106">Parameters</span></span>

<span data-ttu-id="03656-107">`aliasName`(Zeichenfolge []) Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03656-107">`aliasName` (String[]) Required.</span></span> <span data-ttu-id="03656-108">Gibt eine Reihe von durch Trennzeichen getrennten Aliasnamen für den Cmdlet-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="03656-108">Specifies a set of comma-separated alias names for the cmdlet parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="03656-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="03656-109">Remarks</span></span>

- <span data-ttu-id="03656-110">Das Alias-Attribut wird mit dem Parameter-Attribut verwendet, wenn Sie einen Cmdlet-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="03656-110">The Alias attribute is used with the Parameter attribute when you specify a cmdlet parameter.</span></span> <span data-ttu-id="03656-111">Weitere Informationen zum Deklarieren dieser Attribute finden Sie unter [Deklarieren von Cmdlet-Parametern](./how-to-declare-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="03656-111">For more information about how to declare these attributes, see [How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md).</span></span>

- <span data-ttu-id="03656-112">Jeder Aliasname muss innerhalb eines Cmdlets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="03656-112">Each alias name must be unique within a cmdlet.</span></span> <span data-ttu-id="03656-113">Windows PowerShell prüft nicht, ob doppelte Aliasnamen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="03656-113">Windows PowerShell does not check for duplicate alias names.</span></span>

- <span data-ttu-id="03656-114">Das Alias-Attribut wird für jeden Parameter in einem Cmdlet einmal verwendet.</span><span class="sxs-lookup"><span data-stu-id="03656-114">The Alias attribute is used once for each parameter in a cmdlet.</span></span>

- <span data-ttu-id="03656-115">Das Alias-Attribut wird von der [System. Management. Automation. Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="03656-115">The Alias attribute is defined by the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="03656-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03656-116">See Also</span></span>

[<span data-ttu-id="03656-117">Parameteraliase</span><span class="sxs-lookup"><span data-stu-id="03656-117">Parameter Aliases</span></span>](./parameter-aliases.md)

[<span data-ttu-id="03656-118">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="03656-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
