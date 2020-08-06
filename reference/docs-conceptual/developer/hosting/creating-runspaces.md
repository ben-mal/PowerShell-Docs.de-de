---
title: Erstellen von Runspaces | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0c27e2bf54e16a3bdc93c4b91629893bb1cc1e3e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779572"
---
# <a name="creating-runspaces"></a><span data-ttu-id="c5839-102">Erstellen von Runspaces</span><span class="sxs-lookup"><span data-stu-id="c5839-102">Creating Runspaces</span></span>

<span data-ttu-id="c5839-103">Ein Runspace ist die Betriebsumgebung für die Befehle, die von einer Host Anwendung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c5839-103">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="c5839-104">Diese Umgebung umfasst die derzeit vorhandenen Befehle und Daten sowie alle derzeit geltenden Spracheinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="c5839-104">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="c5839-105">Host Anwendungen können den von Windows PowerShell bereitgestellten standardrunspace verwenden, der alle verfügbaren Kern Befehle enthält, oder einen benutzerdefinierten Runspace erstellen, der nur eine Teilmenge der verfügbaren Befehle enthält.</span><span class="sxs-lookup"><span data-stu-id="c5839-105">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="c5839-106">Um einen benutzerdefinierten Runspace zu erstellen, erstellen Sie ein [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt, und weisen Sie es Ihrem Runspace zu.</span><span class="sxs-lookup"><span data-stu-id="c5839-106">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="c5839-107">Runspace-Tasks</span><span class="sxs-lookup"><span data-stu-id="c5839-107">Runspace tasks</span></span>

1. [<span data-ttu-id="c5839-108">Erstellen von InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="c5839-108">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="c5839-109">Erstellen eines eingeschränkten Runspaces</span><span class="sxs-lookup"><span data-stu-id="c5839-109">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="c5839-110">Erstellen von mehreren Runspaces</span><span class="sxs-lookup"><span data-stu-id="c5839-110">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="c5839-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5839-111">See Also</span></span>
