---
title: Module und Snap-Ins | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 07cdc55fd6d1462130f1a81deb30056623a525e6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787307"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="bf53b-102">Module und Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="bf53b-102">Modules and Snap-ins</span></span>

<span data-ttu-id="bf53b-103">Cmdlets können einer Sitzung mithilfe von Modulen (eingeführt von Windows PowerShell 2,0) oder Snap-Ins hinzugefügt werden. Nachdem das Cmdlet der Sitzung hinzugefügt wurde, kann es Programm gesteuert von einer Host Anwendung oder interaktiv in der Befehlszeile ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf53b-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="bf53b-104">Es wird empfohlen, Module als Übermittlungs Methode zum Hinzufügen von Cmdlets zu einer Sitzung aus den folgenden Gründen zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="bf53b-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="bf53b-105">Mit Modulen können Sie Cmdlets hinzufügen, indem Sie die Assembly laden, in der das Cmdlet definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bf53b-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="bf53b-106">Es ist nicht erforderlich, eine Snap-in-Klasse zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="bf53b-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="bf53b-107">Mit Modulen können Sie weitere Ressourcen hinzufügen, z. b. Variablen, Funktionen, Skripts, Typen und Formatierungs Dateien.</span><span class="sxs-lookup"><span data-stu-id="bf53b-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="bf53b-108">Snap-Ins können nur zum Hinzufügen von Cmdlets und Anbietern zur Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bf53b-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf53b-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf53b-109">See Also</span></span>

[<span data-ttu-id="bf53b-110">Schreiben eines Windows PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="bf53b-110">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

[<span data-ttu-id="bf53b-111">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="bf53b-111">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
