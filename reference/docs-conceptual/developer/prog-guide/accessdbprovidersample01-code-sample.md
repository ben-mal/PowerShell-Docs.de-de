---
title: AccessDbProviderSample01-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 2e9f81b3011ea1b27bafd9e02ea7e0faf7903a62
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784825"
---
# <a name="accessdbprovidersample01-code-sample"></a><span data-ttu-id="06158-102">AccessDbProviderSample01-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="06158-102">AccessDbProviderSample01 Code Sample</span></span>

<span data-ttu-id="06158-103">Der folgende Code zeigt die Implementierung des Windows PowerShell-Anbieters, der unter [Erstellen eines einfachen Windows PowerShell-Anbieters](./creating-a-basic-windows-powershell-provider.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="06158-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span>
<span data-ttu-id="06158-104">Diese Implementierung stellt Methoden zum Starten und Beenden des Anbieters bereit und stellt zwar keine Mittel für den Zugriff auf einen Datenspeicher oder zum Abrufen oder Festlegen der Daten im Datenspeicher bereit, bietet jedoch die Grundfunktionen, die von allen Anbietern benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="06158-104">This implementation provides methods for starting and stopping the provider, and although it does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

> [!NOTE]
> <span data-ttu-id="06158-105">Sie können die c#-Quelldatei (AccessDBSampleProvider01.cs) für diesen Anbieter herunterladen, indem Sie das Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0-Laufzeitkomponenten verwenden.</span><span class="sxs-lookup"><span data-stu-id="06158-105">You can download the C# source file (AccessDBSampleProvider01.cs) for this provider by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="06158-106">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="06158-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="06158-107">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06158-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="06158-108">Weitere Informationen zu anderen Windows PowerShell-Anbieter Implementierungen finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="06158-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="06158-109">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="06158-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a><span data-ttu-id="06158-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06158-110">See Also</span></span>

[<span data-ttu-id="06158-111">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="06158-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="06158-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="06158-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
