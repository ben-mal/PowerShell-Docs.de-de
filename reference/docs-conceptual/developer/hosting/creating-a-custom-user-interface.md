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
# <a name="creating-a-custom-user-interface"></a>Erstellen einer benutzerdefinierten Benutzeroberfläche

Windows PowerShell bietet abstrakte Klassen und Schnittstellen, mit denen Sie eine benutzerdefinierte interaktive Benutzeroberfläche erstellen können, auf der die Windows PowerShell-Engine gehostet wird. Um eine benutzerdefinierte Benutzeroberfläche zu erstellen, müssen Sie die [System. Management. Automation. Host. pshost](/dotnet/api/System.Management.Automation.Host.PSHost) -Klasse implementieren. Optional: Sie können auch die Klassen " [System. Management. Automation. Host. pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)" und " [System. Management. Automation. Host. pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) " sowie die Schnittstellen " [System. Management. Automation. Host. ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) " und " [System. Management. Automation. Host](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection)
