---
title: AccessDbProviderSample04-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 05509c5b36475bcd3f91c9ab7413974994d668d6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787273"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="d8a34-102">AccessDbProviderSample04-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="d8a34-102">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="d8a34-103">Der folgende Code zeigt die Implementierung des Windows PowerShell-Anbieters, der unter [Erstellen eines Windows PowerShell-Container Anbieters](./creating-a-windows-powershell-container-provider.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d8a34-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="d8a34-104">Dieser Anbieter funktioniert in Daten speichern mit mehreren Ebenen.</span><span class="sxs-lookup"><span data-stu-id="d8a34-104">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="d8a34-105">Bei dieser Art von Datenspeicher enthält die oberste Ebene des Stores die Stamm Elemente, und jede nachfolgende Ebene wird als Knoten untergeordneter Elemente bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d8a34-105">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="d8a34-106">Da der Benutzer an diesen untergeordneten Knoten arbeiten kann, kann er hierarchisch über den Datenspeicher interagieren.</span><span class="sxs-lookup"><span data-stu-id="d8a34-106">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="d8a34-107">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="d8a34-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="d8a34-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8a34-108">See Also</span></span>

[<span data-ttu-id="d8a34-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="d8a34-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
