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
# <a name="displaying-error-information"></a><span data-ttu-id="79d86-103">Anzeigen von Fehlerinformationen</span><span class="sxs-lookup"><span data-stu-id="79d86-103">Displaying Error Information</span></span>

<span data-ttu-id="79d86-104">In diesem Thema wird erläutert, wie Benutzerfehler Informationen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="79d86-104">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="79d86-105">Wenn das Cmdlet auf einen Fehler stößt, wird die Darstellung der Fehlerinformationen standardmäßig der folgenden Fehlerausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="79d86-105">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="79d86-106">Allerdings können Benutzerfehler nach Kategorie anzeigen, indem Sie die- `$ErrorView` Variable auf festlegen `"CategoryView"` .</span><span class="sxs-lookup"><span data-stu-id="79d86-106">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="79d86-107">In der Kategorieansicht werden bestimmte Informationen aus dem Fehler Daten Satz und nicht eine frei Textbeschreibung des Fehlers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79d86-107">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="79d86-108">Diese Ansicht kann nützlich sein, wenn Sie über eine lange Liste der zu überprüfenden Fehler verfügen.</span><span class="sxs-lookup"><span data-stu-id="79d86-108">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="79d86-109">In der Kategorieansicht wird die vorherige Fehlermeldung wie folgt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79d86-109">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="79d86-110">Weitere Informationen zu Fehlerkategorien finden Sie unter [Windows PowerShell-Fehler Datensätze](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="79d86-110">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79d86-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79d86-111">See Also</span></span>

[<span data-ttu-id="79d86-112">Windows PowerShell-Fehlerdatensätze</span><span class="sxs-lookup"><span data-stu-id="79d86-112">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="79d86-113">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="79d86-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
