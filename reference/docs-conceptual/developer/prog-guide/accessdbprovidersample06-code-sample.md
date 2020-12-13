---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDbProviderSample06-Codebeispiel
description: AccessDbProviderSample06-Codebeispiel
ms.openlocfilehash: 401aca7fab86cfbf3fa8d671eab17412dd162a88
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647493"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="f0d67-103">AccessDbProviderSample06-Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="f0d67-103">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="f0d67-104">Der folgende Code zeigt die Implementierung des Windows PowerShell-Inhalts Anbieters, der unter [Erstellen eines Windows PowerShell-Inhalts Anbieters](./creating-a-windows-powershell-content-provider.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f0d67-104">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span>
<span data-ttu-id="f0d67-105">Dieser Anbieter ermöglicht dem Benutzer, den Inhalt der Elemente in einem Datenspeicher zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f0d67-105">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="f0d67-106">Sie können die c#-Quelldatei (AccessDBSampleProvider06.cs) für diesen Anbieter herunterladen, indem Sie die Laufzeitkomponenten Microsoft Windows Software Development Kit für Windows Vista und Microsoft .NET Framework 3,0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0d67-106">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="f0d67-107">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="f0d67-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="f0d67-108">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f0d67-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="f0d67-109">Weitere Informationen zu anderen Windows PowerShell-Anbieter Implementierungen finden [Sie unter Entwerfen des Windows PowerShell-Anbieters](./designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f0d67-109">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="f0d67-110">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="f0d67-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a><span data-ttu-id="f0d67-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0d67-111">See Also</span></span>

[<span data-ttu-id="f0d67-112">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="f0d67-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="f0d67-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f0d67-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
