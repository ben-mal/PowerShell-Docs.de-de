---
title: Beispiele für die Windows PowerShell-API | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: d7232bb16851f1d568cbdfc4374e287d0875adc8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780167"
---
# <a name="windows-powershell-api-samples"></a><span data-ttu-id="0874b-102">Beispiele für Windows PowerShell-APIs</span><span class="sxs-lookup"><span data-stu-id="0874b-102">Windows PowerShell API Samples</span></span>

<span data-ttu-id="0874b-103">Dieser Abschnitt enthält Beispielcode, der zeigt, wie Sie Runspaces erstellen, die die Funktionalität einschränken, und wie Sie Befehle asynchron ausführen, indem Sie einen Runspace-Pool verwenden, um die Runspaces bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0874b-103">This section includes sample code that shows how to create runspaces that restrict functionality, and how to asynchronously run commands by using a runspace pool to supply the runspaces.</span></span> <span data-ttu-id="0874b-104">Mit Microsoft Visual Studio können Sie eine Konsolenanwendung erstellen und dann den Code aus den Themen in diesem Abschnitt in die Host Anwendung kopieren.</span><span class="sxs-lookup"><span data-stu-id="0874b-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0874b-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0874b-105">In This Section</span></span>

<span data-ttu-id="0874b-106">[PowerShell01-Beispiel](./windows-powershell01-sample.md) In diesem Beispiel wird gezeigt, wie ein [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt verwendet wird, um die Funktionalität eines Runspace einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="0874b-106">[PowerShell01 Sample](./windows-powershell01-sample.md) This sample shows how to use an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to limit the functionality of a runspace.</span></span> <span data-ttu-id="0874b-107">In der Ausgabe dieses Beispiels wird veranschaulicht, wie der Sprachmodus des Runspace eingeschränkt wird, wie ein Cmdlet als privat markiert wird, wie Cmdlets und Anbieter hinzugefügt und entfernt werden, wie ein Proxy Befehl hinzugefügt wird und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="0874b-107">The output of this sample demonstrates how to restrict the language mode of the runspace, how to mark a cmdlet as private, how to add and remove cmdlets and providers, how to add a proxy command, and more.</span></span>

<span data-ttu-id="0874b-108">[PowerShell02-Beispiel](./windows-powershell02-sample.md) In diesem Beispiel wird gezeigt, wie Befehle asynchron mit den Runspaces eines Runspace-Pools ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0874b-108">[PowerShell02 Sample](./windows-powershell02-sample.md) This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="0874b-109">Das Beispiel generiert eine Liste mit Befehlen und führt diese Befehle aus, während die Windows PowerShell-Engine einen Runspace aus dem Pool öffnet, wenn Sie benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="0874b-109">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>
