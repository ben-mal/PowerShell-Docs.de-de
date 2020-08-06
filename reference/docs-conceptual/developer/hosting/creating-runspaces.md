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
# <a name="creating-runspaces"></a>Erstellen von Runspaces

Ein Runspace ist die Betriebsumgebung für die Befehle, die von einer Host Anwendung aufgerufen werden. Diese Umgebung umfasst die derzeit vorhandenen Befehle und Daten sowie alle derzeit geltenden Spracheinschränkungen.

 Host Anwendungen können den von Windows PowerShell bereitgestellten standardrunspace verwenden, der alle verfügbaren Kern Befehle enthält, oder einen benutzerdefinierten Runspace erstellen, der nur eine Teilmenge der verfügbaren Befehle enthält. Um einen benutzerdefinierten Runspace zu erstellen, erstellen Sie ein [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt, und weisen Sie es Ihrem Runspace zu.

## <a name="runspace-tasks"></a>Runspace-Tasks

1. [Erstellen von InitialSessionState](./creating-an-initialsessionstate.md)

2. [Erstellen eines eingeschränkten Runspaces](./creating-a-constrained-runspace.md)

3. [Erstellen von mehreren Runspaces](./creating-multiple-runspaces.md)

## <a name="see-also"></a>Weitere Informationen
