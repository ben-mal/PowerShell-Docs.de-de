---
title: AccessDBProviderSample05 | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 67a10d9192350b339da1b82d9eb367ee4af6ef86
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786848"
---
# <a name="accessdbprovidersample05"></a><span data-ttu-id="c46d1-102">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="c46d1-102">AccessDBProviderSample05</span></span>

<span data-ttu-id="c46d1-103">Dieses Beispiel zeigt, wie Sie Container Methoden überschreiben, um Aufrufe der `Move-Item` -und- `Join-Path` Cmdlets zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c46d1-103">This sample shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span> <span data-ttu-id="c46d1-104">Diese Methoden sollten implementiert werden, wenn der Benutzer Elemente innerhalb eines Containers verschieben muss, und wenn der Datenspeicher geschachtelte Container enthält.</span><span class="sxs-lookup"><span data-stu-id="c46d1-104">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span> <span data-ttu-id="c46d1-105">Die Anbieter Klasse in diesem Beispiel wird von der [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c46d1-105">The provider class in this sample derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="c46d1-106">Zeigt</span><span class="sxs-lookup"><span data-stu-id="c46d1-106">Demonstrates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c46d1-107">Ihre Anbieter Klasse wird wahrscheinlich von einer der folgenden Klassen abgeleitet und kann möglicherweise andere Anbieter Schnittstellen implementieren:</span><span class="sxs-lookup"><span data-stu-id="c46d1-107">Your provider class will most likely derive from one of the following classes and possibly implement other provider interfaces:</span></span>
>
> - <span data-ttu-id="c46d1-108">[System. Management. Automation. Provider. itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="c46d1-108">[System.Management.Automation.Provider.Itemcmdletprovider](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider) class.</span></span> <span data-ttu-id="c46d1-109">Siehe [AccessDBProviderSample03](./accessdbprovidersample03.md).</span><span class="sxs-lookup"><span data-stu-id="c46d1-109">See [AccessDBProviderSample03](./accessdbprovidersample03.md).</span></span>
> - <span data-ttu-id="c46d1-110">[System. Management. Automation. Provider. containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="c46d1-110">[System.Management.Automation.Provider.Containercmdletprovider](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider) class.</span></span> <span data-ttu-id="c46d1-111">Siehe [AccessDBProviderSample04](./accessdbprovidersample04.md).</span><span class="sxs-lookup"><span data-stu-id="c46d1-111">See [AccessDBProviderSample04](./accessdbprovidersample04.md).</span></span>
> - <span data-ttu-id="c46d1-112">[System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse.</span><span class="sxs-lookup"><span data-stu-id="c46d1-112">[System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>
>
> <span data-ttu-id="c46d1-113">Weitere Informationen zum Auswählen der Anbieter Klasse, von der basierend auf den Anbieter Features abgeleitet werden soll, finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./provider-types.md).</span><span class="sxs-lookup"><span data-stu-id="c46d1-113">For more information about choosing which provider class to derive from based on provider features, see [Designing Your Windows PowerShell Provider](./provider-types.md).</span></span>

<span data-ttu-id="c46d1-114">Dieses Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c46d1-114">This sample demonstrates the following:</span></span>

- <span data-ttu-id="c46d1-115">Deklarieren des `CmdletProvider` Attributs.</span><span class="sxs-lookup"><span data-stu-id="c46d1-115">Declaring the `CmdletProvider` attribute.</span></span>

- <span data-ttu-id="c46d1-116">Definieren einer Anbieter Klasse, die von der [System. Management. Automation. Provider. navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c46d1-116">Defining a provider class that derives from the [System.Management.Automation.Provider.Navigationcmdletprovider](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider) class.</span></span>

- <span data-ttu-id="c46d1-117">Überschreiben der [System. Management. Automation. Provider. navigationcmdletprovider. MoveItem \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) -Methode, um das Verhalten des `Move-Item` Cmdlets zu ändern, sodass der Benutzer Elemente von einem Speicherort zu einem anderen verschieben kann.</span><span class="sxs-lookup"><span data-stu-id="c46d1-117">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Moveitem\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) method to change the behavior of the `Move-Item` cmdlet, allowing the user to move items from one location to another.</span></span> <span data-ttu-id="c46d1-118">(Dieses Beispiel zeigt nicht, wie dem Cmdlet dynamische Parameter hinzugefügt werden `Move-Item` .)</span><span class="sxs-lookup"><span data-stu-id="c46d1-118">(This sample does not show how to add dynamic parameters to the `Move-Item` cmdlet.)</span></span>

- <span data-ttu-id="c46d1-119">Überschreiben der [System. Management. Automation. Provider. navigationcmdletprovider. makepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) -Methode, um das Verhalten des `Join-Path` Cmdlets zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c46d1-119">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Makepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) method to change the behavior of the `Join-Path` cmdlet.</span></span>

- <span data-ttu-id="c46d1-120">Überschreiben der [System. Management. Automation. Provider. navigationcmdletprovider. isitemcontainer \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) -Methode.</span><span class="sxs-lookup"><span data-stu-id="c46d1-120">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Isitemcontainer\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.IsItemContainer) method.</span></span>

- <span data-ttu-id="c46d1-121">Überschreiben der [System. Management. Automation. Provider. navigationcmdletprovider. getchildname \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) -Methode.</span><span class="sxs-lookup"><span data-stu-id="c46d1-121">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getchildname\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetChildName) method.</span></span>

- <span data-ttu-id="c46d1-122">Überschreiben der [System. Management. Automation. Provider. navigationcmdletprovider. getparameentpath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) -Methode.</span><span class="sxs-lookup"><span data-stu-id="c46d1-122">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Getparentpath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.GetParentPath) method.</span></span>

- <span data-ttu-id="c46d1-123">Überschreiben der [System. Management. Automation. Provider. navigationcmdletprovider. normalizerelativepath \*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) -Methode.</span><span class="sxs-lookup"><span data-stu-id="c46d1-123">Overwriting the [System.Management.Automation.Provider.Navigationcmdletprovider.Normalizerelativepath\*](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.NormalizeRelativePath) method.</span></span>

## <a name="example"></a><span data-ttu-id="c46d1-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c46d1-124">Example</span></span>

<span data-ttu-id="c46d1-125">Dieses Beispiel zeigt, wie Sie die Methoden überschreiben, die zum Verschieben von Elementen in einer Microsoft Access-Datenbasis erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c46d1-125">This sample shows how to overwrite the methods needed to move items in a Microsoft Access data base.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample05/AccessDBProviderSample05.cs" range="11-1960":::

## <a name="see-also"></a><span data-ttu-id="c46d1-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c46d1-126">See Also</span></span>

[<span data-ttu-id="c46d1-127">System. Management. Automation. Provider. itemcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="c46d1-127">System.Management.Automation.Provider.Itemcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider)

[<span data-ttu-id="c46d1-128">System. Management. Automation. Provider. containercmdletprovider</span><span class="sxs-lookup"><span data-stu-id="c46d1-128">System.Management.Automation.Provider.Containercmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider)

[<span data-ttu-id="c46d1-129">System. Management. Automation. Provider. navigationcmdletprovider</span><span class="sxs-lookup"><span data-stu-id="c46d1-129">System.Management.Automation.Provider.Navigationcmdletprovider</span></span>](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider)

[<span data-ttu-id="c46d1-130">Entwerfen eines Windows PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="c46d1-130">Designing Your Windows PowerShell Provider</span></span>](./provider-types.md)
