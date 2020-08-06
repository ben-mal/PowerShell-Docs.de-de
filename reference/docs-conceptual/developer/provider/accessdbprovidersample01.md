---
title: AccessDBProviderSample01 | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 50ec218e8d0fe6b2be5c8ac00956f72c6723f84a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786916"
---
# <a name="accessdbprovidersample01"></a><span data-ttu-id="f096e-102">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="f096e-102">AccessDBProviderSample01</span></span>

<span data-ttu-id="f096e-103">Dieses Beispiel zeigt, wie Sie eine Anbieter Klasse deklarieren, die direkt von der [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="f096e-103">This sample shows how to declare a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span> <span data-ttu-id="f096e-104">Wird hier nur aus Gründen der Vollständigkeit aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f096e-104">It is included here only for completeness.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="f096e-105">Zeigt</span><span class="sxs-lookup"><span data-stu-id="f096e-105">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f096e-106">Ihre Anbieter Klasse wird wahrscheinlich von einer der folgenden Klassen abgeleitet und kann möglicherweise andere Anbieter Schnittstellen implementieren:</span><span class="sxs-lookup"><span data-stu-id="f096e-106">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="f096e-107">[System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="f096e-107">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="f096e-108">Siehe [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="f096e-108">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="f096e-109">[System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="f096e-109">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="f096e-110">Siehe [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="f096e-110">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="f096e-111">[System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="f096e-111">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span> <span data-ttu-id="f096e-112">Siehe [AccessDBProviderSample05](./accessdbprovidersample05.md).</span><span class="sxs-lookup"><span data-stu-id="f096e-112">See [AccessDBProviderSample05](./accessdbprovidersample05.md).</span></span>
>
> <span data-ttu-id="f096e-113">Weitere Informationen zum Auswählen der Anbieter Klasse, von der basierend auf den Anbieter Features abgeleitet werden soll, finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="f096e-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="f096e-114">Dieses Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f096e-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="f096e-115">Deklarieren des `CmdletProvider` Attributs.</span><span class="sxs-lookup"><span data-stu-id="f096e-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="f096e-116">Definieren einer Anbieter Klasse, die direkt von der [System. Management. Automation. Provider. cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="f096e-116">Defining a provider class that derives directly from the [System.Management.Automation.Provider.Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) class.</span></span>

## <a name="example"></a><span data-ttu-id="f096e-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f096e-117">Example</span></span>

<span data-ttu-id="f096e-118">Dieses Beispiel zeigt, wie Sie eine Anbieter Klasse definieren und das Attribut deklarieren `CmdletProvider` .</span><span class="sxs-lookup"><span data-stu-id="f096e-118">This sample shows how to define a provider class and how to declare the `CmdletProvider` attribute.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="f096e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f096e-119">See Also</span></span>

[<span data-ttu-id="f096e-120">System. Management. Automation. Provider. itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="f096e-120">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="f096e-121">System. Management. Automation. Provider. containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="f096e-121">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="f096e-122">System. Management. Automation. Provider. navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="f096e-122">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="f096e-123">Entwerfen eines Windows PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="f096e-123">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
