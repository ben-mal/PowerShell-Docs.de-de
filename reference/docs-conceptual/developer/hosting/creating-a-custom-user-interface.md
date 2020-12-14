---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen einer benutzerdefinierten Benutzeroberfläche
description: Erstellen einer benutzerdefinierten Benutzeroberfläche
ms.openlocfilehash: 411165f868cd524c0cef0ba9cce3188c60a7dbdf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645403"
---
# <a name="creating-a-custom-user-interface"></a><span data-ttu-id="2349c-103">Erstellen einer benutzerdefinierten Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="2349c-103">Creating a custom user interface</span></span>

<span data-ttu-id="2349c-104">Windows PowerShell bietet abstrakte Klassen und Schnittstellen, mit denen Sie eine benutzerdefinierte interaktive Benutzeroberfläche erstellen können, auf der die Windows PowerShell-Engine gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2349c-104">Windows PowerShell provides abstract classes and interfaces that allow you to create a custom interactive UI that hosts the Windows PowerShell engine.</span></span> <span data-ttu-id="2349c-105">Um eine benutzerdefinierte Benutzeroberfläche zu erstellen, müssen Sie die [System. Management. Automation. Host. pshost](/dotnet/api/System.Management.Automation.Host.PSHost) -Klasse implementieren.</span><span class="sxs-lookup"><span data-stu-id="2349c-105">To create a custom UI, you must implement the [System.Management.Automation.Host.PSHost](/dotnet/api/System.Management.Automation.Host.PSHost) class.</span></span> <span data-ttu-id="2349c-106">Optional: Sie können auch die Klassen " [System. Management. Automation. Host. pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)" und " [System. Management. Automation. Host. pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) " sowie die Schnittstellen " [System. Management. Automation. Host. ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) " und " [System. Management. Automation. Host](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection)</span><span class="sxs-lookup"><span data-stu-id="2349c-106">Optionally, you can also implement the [System.Management.Automation.Host.Pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)and [System.Management.Automation.Host.Pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) classes, and the [System.Management.Automation.Host.Ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) and [System.Management.Automation.Host.Ihostuisupportsmultiplechoiceselection](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection) interfaces.</span></span>
