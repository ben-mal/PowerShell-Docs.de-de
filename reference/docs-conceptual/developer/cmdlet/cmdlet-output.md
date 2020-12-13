---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet-Ausgabe
description: Cmdlet-Ausgabe
ms.openlocfilehash: 37606e57d9dff3ed9fa25b2b99eb07efa0147127
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653264"
---
# <a name="cmdlet-output"></a><span data-ttu-id="f14cd-103">Cmdlet-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="f14cd-103">Cmdlet Output</span></span>

<span data-ttu-id="f14cd-104">In diesem Abschnitt werden die Typen der Cmdlet-Ausgabe und die Methoden erläutert, die Cmdlets zum Generieren von Ausgaben (z. b. Fehlermeldungen und Objekte) abrufen können.</span><span class="sxs-lookup"><span data-stu-id="f14cd-104">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="f14cd-105">In diesem Abschnitt wird auch beschrieben, wie Sie die .NET Framework Typen definieren, die von den Cmdlets zurückgegeben werden, und wie diese Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f14cd-105">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f14cd-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f14cd-106">In This Section</span></span>

<span data-ttu-id="f14cd-107">[Cmdlet-Ausgabetypen](./types-of-cmdlet-output.md) Beschreibt die Typen und die Ausgabe, die Cmdlets generieren können, und die Methoden, die Cmdlets zum Generieren der Ausgabe aufruft.</span><span class="sxs-lookup"><span data-stu-id="f14cd-107">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="f14cd-108">[Cmdlet-Fehlerberichterstattung](./cmdlet-error-reporting.md) Erläutert die Cmdlet-Fehlerberichterstattung, eine Teilmenge der Cmdlet-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="f14cd-108">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="f14cd-109">[Erweitern von Ausgabe Objekten](./extending-output-objects.md) Erläutert, wie die Typen Dateien (. ps1xml) verwendet werden, um die .NET Framework Objekte zu erweitern, die von Cmdlets, Funktionen und Skripts zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f14cd-109">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="f14cd-110">[PowerShell-Formatierungs Dateien](../format/powershell-formatting-files.md) Beschreibt die Formatierungs Dateien (.format.ps1XML), die die Standard Anzeige für eine bestimmte Gruppe von .NET Framework Objekten in Windows PowerShell definieren.</span><span class="sxs-lookup"><span data-stu-id="f14cd-110">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="f14cd-111">[Benutzerdefinierte Formatierungs Dateien](./custom-formatting-files.md) Beschreibt, wie Sie eigene benutzerdefinierte Formatierungs Dateien erstellen, um die Standard Anzeige Formate zu überschreiben oder die Anzeige von Objekten zu definieren, die von ihren eigenen Befehlen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f14cd-111">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="f14cd-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f14cd-112">See Also</span></span>

[<span data-ttu-id="f14cd-113">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f14cd-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
