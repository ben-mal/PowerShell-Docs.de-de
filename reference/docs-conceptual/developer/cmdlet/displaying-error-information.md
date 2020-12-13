---
ms.date: 09/13/2016
ms.topic: reference
title: Anzeigen von Fehlerinformationen
description: Anzeigen von Fehlerinformationen
ms.openlocfilehash: 37a3adb91d0e616a5c7f27bcab866f8da139f969
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653058"
---
# <a name="displaying-error-information"></a>Anzeigen von Fehlerinformationen

In diesem Thema wird erläutert, wie Benutzerfehler Informationen anzeigen können.

Wenn das Cmdlet auf einen Fehler stößt, wird die Darstellung der Fehlerinformationen standardmäßig der folgenden Fehlerausgabe ähneln.

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

Allerdings können Benutzerfehler nach Kategorie anzeigen, indem Sie die- `$ErrorView` Variable auf festlegen `"CategoryView"` . In der Kategorieansicht werden bestimmte Informationen aus dem Fehler Daten Satz und nicht eine frei Textbeschreibung des Fehlers angezeigt. Diese Ansicht kann nützlich sein, wenn Sie über eine lange Liste der zu überprüfenden Fehler verfügen. In der Kategorieansicht wird die vorherige Fehlermeldung wie folgt angezeigt.

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

Weitere Informationen zu Fehlerkategorien finden Sie unter [Windows PowerShell-Fehler Datensätze](./windows-powershell-error-records.md).

## <a name="see-also"></a>Weitere Informationen

[Windows PowerShell-Fehlerdatensätze](./windows-powershell-error-records.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
