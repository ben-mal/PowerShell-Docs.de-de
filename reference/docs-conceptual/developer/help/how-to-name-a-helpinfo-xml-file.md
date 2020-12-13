---
ms.date: 09/12/2016
ms.topic: reference
title: Benennen einer XML-Datei HelpInfo
description: Benennen einer XML-Datei HelpInfo
ms.openlocfilehash: 55bc2ef9530fc457e4d9ddf18e79e7226c991663
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659031"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="01c28-103">Benennen einer XML-Datei HelpInfo</span><span class="sxs-lookup"><span data-stu-id="01c28-103">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="01c28-104">In diesem Thema wird das erforderliche Namensformat für die aktualisierbaren Hilfe Informationsdateien erläutert, die häufig als helpinfo-XML-Dateien bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="01c28-104">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="01c28-105">Benennen einer XML-Datei HelpInfo</span><span class="sxs-lookup"><span data-stu-id="01c28-105">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="01c28-106">Eine helpinfo-XML-Datei muss einen Namen haben, der das folgende Format hat.</span><span class="sxs-lookup"><span data-stu-id="01c28-106">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="01c28-107">Die Elemente des Namens lauten wie folgt.</span><span class="sxs-lookup"><span data-stu-id="01c28-107">The elements of the name are as follows.</span></span>

- <span data-ttu-id="01c28-108">`<ModuleName>` : Der Wert der **Name** -Eigenschaft des **ModuleInfo** -Objekts, das vom [Get-Module-](/powershell/module/Microsoft.PowerShell.Core/Get-Module) Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="01c28-108">`<ModuleName>` - The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

- <span data-ttu-id="01c28-109">`<ModuleGUID>` : Der Wert des **GUID** -Schlüssels im Modul Manifest.</span><span class="sxs-lookup"><span data-stu-id="01c28-109">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="01c28-110">Wenn der Modulname beispielsweise "Testmodule" und die Modul-GUID 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 ist, lautet der Name der helpinfo-XML-Datei für das Modul wie folgt:</span><span class="sxs-lookup"><span data-stu-id="01c28-110">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
