---
title: AccessDbProviderSample06-Code Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: f650648320a0a31324af1bd1a112f01bdfc6c599
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787239"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="799fe-102">AccessDbProviderSample06-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="799fe-102">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="799fe-103">Der folgende Code zeigt die Implementierung des Windows PowerShell-Inhalts Anbieters, der unter [Erstellen eines Windows PowerShell-Inhalts Anbieters](./creating-a-windows-powershell-content-provider.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="799fe-103">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span>
<span data-ttu-id="799fe-104">Dieser Anbieter ermöglicht dem Benutzer, den Inhalt der Elemente in einem Datenspeicher zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="799fe-104">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="799fe-105">Sie können die c#-Quelldatei (AccessDBSampleProvider06.cs) für diesen Anbieter herunterladen, indem Sie die Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="799fe-105">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="799fe-106">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="799fe-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="799fe-107">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="799fe-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="799fe-108">Weitere Informationen zu anderen Windows PowerShell-Anbieter Implementierungen finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="799fe-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="799fe-109">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="799fe-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a><span data-ttu-id="799fe-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="799fe-110">See Also</span></span>

[<span data-ttu-id="799fe-111">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="799fe-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="799fe-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="799fe-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
