---
title: GetProc04-Code Beispiele | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: b90b7e96c1454e57df93863b526758f25d9be690
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771956"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="27926-102">GetProc04-Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="27926-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="27926-103">Im folgenden finden Sie die Codebeispiele für das Cmdlet "GetProc04 Sample".</span><span class="sxs-lookup"><span data-stu-id="27926-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="27926-104">Dies ist das `Get-Process` Cmdlet-Beispiel, das unter [Hinzufügen von Fehlern bei der nicht abschließenden Fehlerberichterstattung zum Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="27926-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="27926-105">Dieses `Get-Process` Cmdlet ruft die [System. Management. Automation. Cmdlet. Write error](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) -Methode auf, wenn beim Abrufen der Prozessinformationen eine Ausnahme vom Typ "Ungültiger Vorgang" ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="27926-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="27926-106">Sie können die c#-Quelldatei (getprov04.cs) für dieses Get-proc-Cmdlet mit dem Microsoft Windows Software Development Kit für Windows Vista und .NET Framework 3,0-Laufzeitkomponenten herunterladen.</span><span class="sxs-lookup"><span data-stu-id="27926-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="27926-107">Anweisungen zum Herunterladen finden Sie unter [Installieren von Windows PowerShell und Herunterladen des Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span><span class="sxs-lookup"><span data-stu-id="27926-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="27926-108">Die heruntergeladenen Quelldateien sind im **\<PowerShell Samples>** Verzeichnis verfügbar.</span><span class="sxs-lookup"><span data-stu-id="27926-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="27926-109">Einen umfassenden Beispielcode finden Sie in den folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="27926-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="27926-110">Sprache</span><span class="sxs-lookup"><span data-stu-id="27926-110">Language</span></span>|<span data-ttu-id="27926-111">Thema</span><span class="sxs-lookup"><span data-stu-id="27926-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="27926-112">C#</span><span class="sxs-lookup"><span data-stu-id="27926-112">C#</span></span>|[<span data-ttu-id="27926-113">GetProc04-Codebeispiel (C#)</span><span class="sxs-lookup"><span data-stu-id="27926-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="27926-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="27926-114">VB.NET</span></span>|[<span data-ttu-id="27926-115">GetProc04-Codebeispiel (VB.NET)</span><span class="sxs-lookup"><span data-stu-id="27926-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="27926-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27926-116">See Also</span></span>

[<span data-ttu-id="27926-117">Windows PowerShell-Programmiererhandbuch</span><span class="sxs-lookup"><span data-stu-id="27926-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="27926-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="27926-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
