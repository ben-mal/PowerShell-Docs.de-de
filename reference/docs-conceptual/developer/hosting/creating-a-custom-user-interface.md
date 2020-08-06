---
title: Erstellen einer benutzerdefinierten Benutzeroberfläche | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: ebbaba4231b54d42cdcdef07a3ff665bd207d696
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779776"
---
# <a name="creating-a-custom-user-interface"></a>Erstellen einer benutzerdefinierten Benutzeroberfläche

Windows PowerShell bietet abstrakte Klassen und Schnittstellen, mit denen Sie eine benutzerdefinierte interaktive Benutzeroberfläche erstellen können, auf der die Windows PowerShell-Engine gehostet wird. Um eine benutzerdefinierte Benutzeroberfläche zu erstellen, müssen Sie die [System. Management. Automation. Host. pshost](/dotnet/api/System.Management.Automation.Host.PSHost) -Klasse implementieren. Optional: Sie können auch die Klassen " [System. Management. Automation. Host. pshostrawuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostRawUserInterface)" und " [System. Management. Automation. Host. pshostuserinterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface) " sowie die Schnittstellen " [System. Management. Automation. Host. ihostsupportsinteractivesession](/dotnet/api/System.Management.Automation.Host.IHostSupportsInteractiveSession) " und " [System. Management. Automation. Host](/dotnet/api/System.Management.Automation.Host.IHostUISupportsMultipleChoiceSelection)
