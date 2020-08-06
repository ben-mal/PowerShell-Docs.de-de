---
title: AccessDbProviderSample02-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: ca7674ba5cff601394af4df20f0dda8794c14d22
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784808"
---
# <a name="accessdbprovidersample02-code-sample"></a><span data-ttu-id="68125-102">AccessDbProviderSample02-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="68125-102">AccessDbProviderSample02 Code Sample</span></span>

<span data-ttu-id="68125-103">Der folgende Code zeigt die Implementierung des Windows PowerShell-Anbieters, der unter [Erstellen eines Windows PowerShell-Laufwerks Anbieters](./creating-a-windows-powershell-drive-provider.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="68125-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Drive Provider](./creating-a-windows-powershell-drive-provider.md).</span></span>
<span data-ttu-id="68125-104">Diese Implementierung erstellt einen Pfad, stellt eine Verbindung mit einer Access-Datenbank her und entfernt dann das Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="68125-104">This implementation creates a path, makes a connection to an Access database, and then removes the drive.</span></span>

> [!NOTE]
> <span data-ttu-id="68125-105">Sie können die c#-Quelldatei (AccessDBSampleProvider02.cs) für diesen Anbieter mithilfe der Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 herunterladen.</span><span class="sxs-lookup"><span data-stu-id="68125-105">You can download the C# source file (AccessDBSampleProvider02.cs) for this provider using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="68125-106">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="68125-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="68125-107">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="68125-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="68125-108">Weitere Informationen zu anderen Windows PowerShell-Anbieter Implementierungen finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="68125-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="68125-109">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="68125-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs" range="11-154":::

## <a name="see-also"></a><span data-ttu-id="68125-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68125-110">See Also</span></span>

[<span data-ttu-id="68125-111">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="68125-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="68125-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="68125-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
