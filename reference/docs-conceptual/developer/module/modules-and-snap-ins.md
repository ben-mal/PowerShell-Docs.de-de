---
ms.date: 09/13/2016
ms.topic: reference
title: Module und Snap-Ins
description: Module und Snap-Ins
ms.openlocfilehash: de4ff1de9a29b78d7783fe7ed0265f5516db1fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658674"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="da87d-103">Module und Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="da87d-103">Modules and Snap-ins</span></span>

<span data-ttu-id="da87d-104">Cmdlets können einer Sitzung mithilfe von Modulen (eingeführt von Windows PowerShell 2,0) oder Snap-Ins hinzugefügt werden. Nachdem das Cmdlet der Sitzung hinzugefügt wurde, kann es Programm gesteuert von einer Host Anwendung oder interaktiv in der Befehlszeile ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="da87d-104">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="da87d-105">Es wird empfohlen, Module als Übermittlungs Methode zum Hinzufügen von Cmdlets zu einer Sitzung aus den folgenden Gründen zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="da87d-105">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="da87d-106">Mit Modulen können Sie Cmdlets hinzufügen, indem Sie die Assembly laden, in der das Cmdlet definiert ist.</span><span class="sxs-lookup"><span data-stu-id="da87d-106">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="da87d-107">Es ist nicht erforderlich, eine Snap-in-Klasse zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="da87d-107">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="da87d-108">Mit Modulen können Sie weitere Ressourcen hinzufügen, z. b. Variablen, Funktionen, Skripts, Typen und Formatierungs Dateien.</span><span class="sxs-lookup"><span data-stu-id="da87d-108">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="da87d-109">Snap-Ins können nur zum Hinzufügen von Cmdlets und Anbietern zur Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da87d-109">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="da87d-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da87d-110">See Also</span></span>

[<span data-ttu-id="da87d-111">Schreiben eines Windows PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="da87d-111">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

[<span data-ttu-id="da87d-112">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="da87d-112">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
