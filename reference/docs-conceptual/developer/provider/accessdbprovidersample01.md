---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDBProviderSample01
description: AccessDBProviderSample01
ms.openlocfilehash: 8bdfa3ad492935a22ce06846294c02961cab2c65
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653758"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="b48aa-103">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="b48aa-103">AccessDBProviderSample01</span></span>

<span data-ttu-id="b48aa-104">Dieses Beispiel zeigt, wie Sie eine Anbieter Klasse deklarieren, die direkt von der [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b48aa-104">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="b48aa-105">Wird hier nur aus Gründen der Vollständigkeit aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b48aa-105">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="b48aa-106">Zeigt</span><span class="sxs-lookup"><span data-stu-id="b48aa-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b48aa-107">Ihre Anbieter Klasse wird wahrscheinlich von einer der folgenden Klassen abgeleitet und kann möglicherweise andere Anbieter Schnittstellen implementieren:</span><span class="sxs-lookup"><span data-stu-id="b48aa-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="b48aa-108">[System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="b48aa-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="b48aa-109">Siehe [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="b48aa-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="b48aa-110">[System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="b48aa-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="b48aa-111">Siehe [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="b48aa-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="b48aa-112">[System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="b48aa-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="b48aa-113">Siehe [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="b48aa-113">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="b48aa-114">Weitere Informationen zum Auswählen der Anbieter Klasse, von der basierend auf den Anbieter Features abgeleitet werden soll, finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="b48aa-114">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="b48aa-115">Dieses Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b48aa-115">This sample demonstrates the following:</span></span>

- <span data-ttu-id="b48aa-116">Deklarieren des `CmdletProvider` Attributs.</span><span class="sxs-lookup"><span data-stu-id="b48aa-116">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="b48aa-117">Definieren einer Anbieter Klasse, die direkt von der [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b48aa-117">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="b48aa-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b48aa-118">Example</span></span>

<span data-ttu-id="b48aa-119">Dieses Beispiel zeigt, wie Sie eine Anbieter Klasse definieren und das Attribut deklarieren `CmdletProvider` .</span><span class="sxs-lookup"><span data-stu-id="b48aa-119">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="b48aa-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b48aa-120">See Also</span></span>

[<span data-ttu-id="b48aa-121">System. Management. Automation. Provider. itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="b48aa-121">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="b48aa-122">System. Management. Automation. Provider. containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="b48aa-122">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="b48aa-123">System. Management. Automation. Provider. navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="b48aa-123">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="b48aa-124">Entwerfen eines Windows PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="b48aa-124">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
