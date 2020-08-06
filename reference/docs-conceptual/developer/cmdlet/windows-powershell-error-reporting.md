---
title: Windows PowerShell-Fehlerberichterstattung | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 7f7afcf5186732734976304c8e58e4d940156e1e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783958"
---
# <a name="windows-powershell-error-reporting"></a><span data-ttu-id="3f6fb-102">Windows PowerShell-Fehlerberichterstattung</span><span class="sxs-lookup"><span data-stu-id="3f6fb-102">Windows PowerShell Error Reporting</span></span>

<span data-ttu-id="3f6fb-103">In den Themen in diesem Abschnitt wird erläutert, wie-Cmdlets Fehler melden.</span><span class="sxs-lookup"><span data-stu-id="3f6fb-103">The topics in this section discuss how cmdlets report errors.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3f6fb-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3f6fb-104">In This Section</span></span>

<span data-ttu-id="3f6fb-105">[Konzepte für die Fehlerberichterstattung](./error-reporting-concepts.md) Beschreibt die beiden Mechanismen, die Cmdlets zum Melden von Fehlern verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3f6fb-105">[Error Reporting Concepts](./error-reporting-concepts.md) Describes the two mechanisms that cmdlets can use to report errors.</span></span>

<span data-ttu-id="3f6fb-106">[Fehler beim Beenden](./terminating-errors.md) Beschreibt die Methode, die zum Melden von Beendigungs Fehlern verwendet wird, wobei diese Methode innerhalb des Cmdlets aufgerufen werden kann, und Ausnahmen, die von der Windows PowerShell-Laufzeit zurückgegeben werden können, wenn die-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3f6fb-106">[Terminating Errors](./terminating-errors.md) Describes the method used to report terminating errors, where that method can be called from within the cmdlet, and exceptions that can be returned by the Windows PowerShell runtime when the method is called.</span></span>

<span data-ttu-id="3f6fb-107">[Fehler ohne](./non-terminating-errors.md) Abbruch Beschreibt die Methode, die verwendet wird, um Fehler ohne Abbruch zu melden, und wo diese Methode innerhalb des Cmdlets aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f6fb-107">[Non-Terminating Errors](./non-terminating-errors.md) Describes the method used to report non-terminating errors and where that method can be called from within the cmdlet.</span></span>

<span data-ttu-id="3f6fb-108">[Anzeigen von Fehlerinformationen nach Kategorie](./displaying-error-information.md) Erläutert die Möglichkeiten, wie Benutzerfehler anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="3f6fb-108">[Displaying Error Information by Category](./displaying-error-information.md) Discusses the ways that users can display error.</span></span>

<span data-ttu-id="3f6fb-109">[Windows PowerShell-Fehler Datensätze](./windows-powershell-error-records.md) Beschreibt die Komponenten eines Fehler Datensatzes.</span><span class="sxs-lookup"><span data-stu-id="3f6fb-109">[Windows PowerShell Error Records](./windows-powershell-error-records.md) Describes the components of an error record.</span></span>

<span data-ttu-id="3f6fb-110">[Interpretieren von ErrorRecord-Objekten](./interpreting-errorrecord-objects.md) Erläutert, wie ErrorRecord-Objekte interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f6fb-110">[Interpreting ErrorRecord Objects](./interpreting-errorrecord-objects.md) Discusses how ErrorRecord objects are interpreted.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f6fb-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f6fb-111">See Also</span></span>

[<span data-ttu-id="3f6fb-112">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3f6fb-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
