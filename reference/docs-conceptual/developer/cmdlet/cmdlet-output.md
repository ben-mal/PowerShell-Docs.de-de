---
title: Cmdlet-Ausgabe | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 7697db01c8c4d1c831202c07256559bf638aeaef
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784434"
---
# <a name="cmdlet-output"></a><span data-ttu-id="d02ce-102">Cmdlet-Ausgabe</span><span class="sxs-lookup"><span data-stu-id="d02ce-102">Cmdlet Output</span></span>

<span data-ttu-id="d02ce-103">In diesem Abschnitt werden die Typen der Cmdlet-Ausgabe und die Methoden erläutert, die Cmdlets zum Generieren von Ausgaben (z. b. Fehlermeldungen und Objekte) abrufen können.</span><span class="sxs-lookup"><span data-stu-id="d02ce-103">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="d02ce-104">In diesem Abschnitt wird auch beschrieben, wie Sie die .NET Framework Typen definieren, die von den Cmdlets zurückgegeben werden, und wie diese Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d02ce-104">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d02ce-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d02ce-105">In This Section</span></span>

<span data-ttu-id="d02ce-106">[Cmdlet-Ausgabetypen](./types-of-cmdlet-output.md) Beschreibt die Typen und die Ausgabe, die Cmdlets generieren können, und die Methoden, die Cmdlets zum Generieren der Ausgabe aufruft.</span><span class="sxs-lookup"><span data-stu-id="d02ce-106">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="d02ce-107">[Cmdlet-Fehlerberichterstattung](./cmdlet-error-reporting.md) Erläutert die Cmdlet-Fehlerberichterstattung, eine Teilmenge der Cmdlet-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d02ce-107">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="d02ce-108">[Erweitern von Ausgabe Objekten](./extending-output-objects.md) Erläutert, wie die Typen Dateien (. ps1xml) verwendet werden, um die .NET Framework Objekte zu erweitern, die von Cmdlets, Funktionen und Skripts zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d02ce-108">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="d02ce-109">[PowerShell-Formatierungs Dateien](../format/powershell-formatting-files.md) Beschreibt die Formatierungs Dateien (.format.ps1XML), die die Standard Anzeige für eine bestimmte Gruppe von .NET Framework Objekten in Windows PowerShell definieren.</span><span class="sxs-lookup"><span data-stu-id="d02ce-109">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="d02ce-110">[Benutzerdefinierte Formatierungs Dateien](./custom-formatting-files.md) Beschreibt, wie Sie eigene benutzerdefinierte Formatierungs Dateien erstellen, um die Standard Anzeige Formate zu überschreiben oder die Anzeige von Objekten zu definieren, die von ihren eigenen Befehlen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d02ce-110">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="d02ce-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d02ce-111">See Also</span></span>

[<span data-ttu-id="d02ce-112">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d02ce-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
