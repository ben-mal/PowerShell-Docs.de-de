---
title: Anzeigen von Fehlerinformationen | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e542110e9c35a74c5d4c112b0a831f7f8ad9242e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774574"
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
