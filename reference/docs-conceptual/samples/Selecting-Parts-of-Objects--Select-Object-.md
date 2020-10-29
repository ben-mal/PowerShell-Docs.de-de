---
ms.date: 12/23/2019
keywords: powershell,cmdlet
title: Auswählen von Objektteilen – Select-Object
description: Sie können das Cmdlet `Select-Object` verwenden, um neue, angepasste PowerShell-Objekte zu erstellen, die ausgewählte Eigenschaften der Objekte in der Pipeline enthalten.
ms.openlocfilehash: 92635ac54ea1469739bcb228c5e9a0a8dbfc648b
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501030"
---
# <a name="selecting-parts-of-objects-select-object"></a><span data-ttu-id="3cf09-104">Auswählen von Objektteilen (Select-Object)</span><span class="sxs-lookup"><span data-stu-id="3cf09-104">Selecting Parts of Objects (Select-Object)</span></span>

<span data-ttu-id="3cf09-105">Sie können das Cmdlet `Select-Object` verwenden, um neue, angepasste Windows PowerShell-Objekte zu erstellen, die ausgewählte Eigenschaften der zum Erstellen verwendeten Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="3cf09-105">You can use the `Select-Object` cmdlet to create new, custom PowerShell objects that contain properties selected from the objects you use to create them.</span></span> <span data-ttu-id="3cf09-106">Geben Sie den folgenden Befehl ein, um ein neues Objekt zu erstellen, das nur die Eigenschaften **Name** und **FreeSpace** der WMI-Klasse **Win32_LogicalDisk** enthält:</span><span class="sxs-lookup"><span data-stu-id="3cf09-106">Type the following command to create a new object that includes only the **Name** and **FreeSpace** properties of the **Win32_LogicalDisk** WMI class:</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

<span data-ttu-id="3cf09-107">Mit `Select-Object` können Sie berechnete Eigenschaften erstellen.</span><span class="sxs-lookup"><span data-stu-id="3cf09-107">With `Select-Object` you can create calculated properties.</span></span> <span data-ttu-id="3cf09-108">Beispielsweise können Sie **FreeSpace** in Gigabyte statt in Byte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3cf09-108">So you can display **FreeSpace** in gigabytes rather than bytes.</span></span>

```powershell
Get-CimInstance -Class Win32_LogicalDisk |
  Select-Object -Property Name, @{
    label='FreeSpace'
    expression={($_.FreeSpace/1GB).ToString('F2')}
  }
```

```Output
Name    FreeSpace
----    ---------
C:      47.18
```
