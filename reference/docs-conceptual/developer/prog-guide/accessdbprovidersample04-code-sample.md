---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDbProviderSample04-Codebeispiel
description: AccessDbProviderSample04-Codebeispiel
ms.openlocfilehash: bb70ce9f1b1c94349c354a8771fedf7fcb1bb320
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647569"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="eba60-103">AccessDbProviderSample04-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="eba60-103">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="eba60-104">Der folgende Code zeigt die Implementierung des Windows PowerShell-Anbieters, der unter [Erstellen eines Windows PowerShell-Container Anbieters](./creating-a-windows-powershell-container-provider.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="eba60-104">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="eba60-105">Dieser Anbieter funktioniert in Daten speichern mit mehreren Ebenen.</span><span class="sxs-lookup"><span data-stu-id="eba60-105">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="eba60-106">Bei dieser Art von Datenspeicher enthält die oberste Ebene des Stores die Stamm Elemente, und jede nachfolgende Ebene wird als Knoten untergeordneter Elemente bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="eba60-106">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="eba60-107">Da der Benutzer an diesen untergeordneten Knoten arbeiten kann, kann er hierarchisch über den Datenspeicher interagieren.</span><span class="sxs-lookup"><span data-stu-id="eba60-107">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="eba60-108">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="eba60-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="eba60-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eba60-109">See Also</span></span>

[<span data-ttu-id="eba60-110">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="eba60-110">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
