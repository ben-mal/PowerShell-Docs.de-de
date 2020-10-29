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
# <a name="selecting-parts-of-objects-select-object"></a>Auswählen von Objektteilen (Select-Object)

Sie können das Cmdlet `Select-Object` verwenden, um neue, angepasste Windows PowerShell-Objekte zu erstellen, die ausgewählte Eigenschaften der zum Erstellen verwendeten Objekte enthalten. Geben Sie den folgenden Befehl ein, um ein neues Objekt zu erstellen, das nur die Eigenschaften **Name** und **FreeSpace** der WMI-Klasse **Win32_LogicalDisk** enthält:

```powershell
Get-CimInstance -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace
```

```Output
Name      FreeSpace
----      ---------
C:      50664845312
```

Mit `Select-Object` können Sie berechnete Eigenschaften erstellen. Beispielsweise können Sie **FreeSpace** in Gigabyte statt in Byte anzeigen.

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
