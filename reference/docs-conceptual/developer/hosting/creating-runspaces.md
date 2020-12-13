---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen von Runspaces
description: Erstellen von Runspaces
ms.openlocfilehash: c6b2c577e435ec88364b189a0c3d065f54f02525
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649337"
---
# <a name="creating-runspaces"></a><span data-ttu-id="3f362-103">Erstellen von Runspaces</span><span class="sxs-lookup"><span data-stu-id="3f362-103">Creating Runspaces</span></span>

<span data-ttu-id="3f362-104">Ein Runspace ist die Betriebsumgebung für die Befehle, die von einer Host Anwendung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3f362-104">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="3f362-105">Diese Umgebung umfasst die derzeit vorhandenen Befehle und Daten sowie alle derzeit geltenden Spracheinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="3f362-105">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="3f362-106">Host Anwendungen können den von Windows PowerShell bereitgestellten standardrunspace verwenden, der alle verfügbaren Kern Befehle enthält, oder einen benutzerdefinierten Runspace erstellen, der nur eine Teilmenge der verfügbaren Befehle enthält.</span><span class="sxs-lookup"><span data-stu-id="3f362-106">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="3f362-107">Um einen benutzerdefinierten Runspace zu erstellen, erstellen Sie ein [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt, und weisen Sie es Ihrem Runspace zu.</span><span class="sxs-lookup"><span data-stu-id="3f362-107">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="3f362-108">Runspace-Tasks</span><span class="sxs-lookup"><span data-stu-id="3f362-108">Runspace tasks</span></span>

1. [<span data-ttu-id="3f362-109">Erstellen von InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="3f362-109">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="3f362-110">Erstellen eines eingeschränkten Runspaces</span><span class="sxs-lookup"><span data-stu-id="3f362-110">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="3f362-111">Erstellen von mehreren Runspaces</span><span class="sxs-lookup"><span data-stu-id="3f362-111">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="3f362-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f362-112">See Also</span></span>
