---
ms.date: 06/12/2017
title: Deinstallieren von WMF 5.0
description: In diesem Artikel wird erläutert, wie WMF aus älteren Versionen von Windows deinstalliert wird.
ms.openlocfilehash: d8078ea918db2c1cf9a7ddd6ea8d1413b593c0ff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660799"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="78008-103">Deinstallationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="78008-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="78008-104">Verwenden der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="78008-104">Using Command Prompt</span></span>

1. <span data-ttu-id="78008-105">Öffnen Sie die **Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="78008-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="78008-106">Führen Sie das [eigenständige Windows Update-Startprogramm](https://support.microsoft.com/kb/934307) wie unten dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="78008-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/kb/934307) as shown below:</span></span>

<span data-ttu-id="78008-107">Unter Windows Server 2012 R2 und Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="78008-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="78008-108">Unter Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="78008-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="78008-109">Unter Windows Server 2008 R2 SP1 und Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="78008-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="78008-110">Über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="78008-110">Using Control Panel</span></span>

1. <span data-ttu-id="78008-111">Öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="78008-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="78008-112">Öffnen Sie **Programme** und dann **Programm deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="78008-112">Open **Programs** , then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="78008-113">Klicken Sie auf **Installierte Updates anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="78008-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="78008-114">Wählen Sie in der Liste der installierten Updates **Windows Management Framework 5.0** aus.</span><span class="sxs-lookup"><span data-stu-id="78008-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="78008-115">Dies entspricht *KB3134758* , *KB3134759* oder *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="78008-115">This corresponds to *KB3134758* , *KB3134759* , or *KB3134760*.</span></span> <span data-ttu-id="78008-116">Klicken Sie auf **Deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="78008-116">Click **Uninstall.**</span></span>
