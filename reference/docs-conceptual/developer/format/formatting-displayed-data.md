---
ms.date: 09/12/2016
ms.topic: reference
title: Formatieren von angezeigten Daten
description: Formatieren von angezeigten Daten
ms.openlocfilehash: 40f6b3b4fa36062ee0bad3f197ad159f571445c8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667860"
---
# <a name="formatting-displayed-data"></a>Formatieren von angezeigten Daten

Sie können angeben, wie die einzelnen Datenpunkte in der Listen-, Tabellen-oder breiten Ansicht angezeigt werden. Sie können das- `FormatString` Element verwenden, wenn Sie die Elemente der Ansicht definieren, oder Sie können das- `ScriptBlock` Element verwenden, um die- `FormatString` Methode für die Daten aufzurufen.

## <a name="using-the-formatstring-element"></a>Verwenden des FormatString-Elements

Im folgenden Beispiel wird der Wert der- `TotalProcessorTime` Eigenschaft des [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekts mit dem FormatString-Element formatiert. die- `TotalProcessorTime` Eigenschaft

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
