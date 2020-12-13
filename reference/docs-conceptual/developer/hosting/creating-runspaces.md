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
# <a name="creating-runspaces"></a>Erstellen von Runspaces

Ein Runspace ist die Betriebsumgebung für die Befehle, die von einer Host Anwendung aufgerufen werden. Diese Umgebung umfasst die derzeit vorhandenen Befehle und Daten sowie alle derzeit geltenden Spracheinschränkungen.

 Host Anwendungen können den von Windows PowerShell bereitgestellten standardrunspace verwenden, der alle verfügbaren Kern Befehle enthält, oder einen benutzerdefinierten Runspace erstellen, der nur eine Teilmenge der verfügbaren Befehle enthält. Um einen benutzerdefinierten Runspace zu erstellen, erstellen Sie ein [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt, und weisen Sie es Ihrem Runspace zu.

## <a name="runspace-tasks"></a>Runspace-Tasks

1. [Erstellen von InitialSessionState](./creating-an-initialsessionstate.md)

2. [Erstellen eines eingeschränkten Runspaces](./creating-a-constrained-runspace.md)

3. [Erstellen von mehreren Runspaces](./creating-multiple-runspaces.md)

## <a name="see-also"></a>Siehe auch
