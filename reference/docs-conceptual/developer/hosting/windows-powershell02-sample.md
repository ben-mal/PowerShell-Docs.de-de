---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell02-Beispiel
description: Windows PowerShell02-Beispiel
ms.openlocfilehash: 61dedd72d93d4000edf9a12f12bbb49fbaeb9f3c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657360"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="4b1ec-103">Windows PowerShell02-Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b1ec-103">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="4b1ec-104">Dieses Beispiel zeigt, wie Befehle asynchron mit den Runspaces eines Runspace-Pools ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4b1ec-104">This sample shows how to run commands asynchronously using the runspaces of a runspace pool.</span></span> <span data-ttu-id="4b1ec-105">Das Beispiel generiert eine Liste mit Befehlen und führt diese Befehle aus, während die Windows PowerShell-Engine einen Runspace aus dem Pool öffnet, wenn Sie benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="4b1ec-105">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="4b1ec-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b1ec-106">Requirements</span></span>

- <span data-ttu-id="4b1ec-107">Dieses Beispiel erfordert Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="4b1ec-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="4b1ec-108">Zeigt</span><span class="sxs-lookup"><span data-stu-id="4b1ec-108">Demonstrates</span></span>

<span data-ttu-id="4b1ec-109">Dieses Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4b1ec-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="4b1ec-110">Das Erstellen eines runspacepool-Objekts mit einer minimalen und maximalen Anzahl von Runspaces, die gleichzeitig geöffnet sein dürfen.</span><span class="sxs-lookup"><span data-stu-id="4b1ec-110">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>
- <span data-ttu-id="4b1ec-111">Erstellen einer Liste von Befehlen.</span><span class="sxs-lookup"><span data-stu-id="4b1ec-111">Creating a list of commands.</span></span>
- <span data-ttu-id="4b1ec-112">Asynchrones Ausführen der Befehle.</span><span class="sxs-lookup"><span data-stu-id="4b1ec-112">Running the commands asynchronously.</span></span>
- <span data-ttu-id="4b1ec-113">Aufrufen der [System. Management. Automation. Runspaces. runspacepool. getavailablerunspaces \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) -Methode, um zu sehen, wie viele Runspaces kostenlos sind.</span><span class="sxs-lookup"><span data-stu-id="4b1ec-113">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>
- <span data-ttu-id="4b1ec-114">Erfassen der Befehlsausgabe mit der [System. Management. Automation. PowerShell. EndInvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) -Methode.</span><span class="sxs-lookup"><span data-stu-id="4b1ec-114">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="4b1ec-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b1ec-115">Example</span></span>

<span data-ttu-id="4b1ec-116">Dieses Beispiel zeigt, wie Sie die Runspaces eines Runspace-Pools öffnen und Befehle in diesen Runspaces asynchron ausführen.</span><span class="sxs-lookup"><span data-stu-id="4b1ec-116">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a><span data-ttu-id="4b1ec-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b1ec-117">See Also</span></span>

[<span data-ttu-id="4b1ec-118">Schreiben einer Windows PowerShell-Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="4b1ec-118">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
