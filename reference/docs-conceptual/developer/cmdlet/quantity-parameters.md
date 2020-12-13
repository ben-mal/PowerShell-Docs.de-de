---
ms.date: 09/13/2016
ms.topic: reference
title: Mengenparameter
description: Mengenparameter
ms.openlocfilehash: 3f7c23eec34a709b1f2d59f611c93909b20f4124
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650298"
---
# <a name="quantity-parameters"></a>Mengenparameter

In der folgenden Tabelle werden die empfohlenen Namen und Funktionen für die Anzahl von Parametern aufgelistet.

|Parameter|Funktionalität|
|---|---|
|**Alle**<br>Datentyp: Boolescher Wert|Implementieren Sie diesen Parameter, damit `true` angibt, dass alle Ressourcen anstelle einer Standard Teilmenge von Ressourcen bearbeitet werden sollten. Implementieren Sie diesen Parameter, sodass `false` eine Teilmenge der Ressourcen angibt.|
|**Speicherbelegung**<br>Datentyp: Int32|Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl der zuzuordnenden Elemente angeben kann.|
|**Blockcount**<br>Datentyp: Int64|Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl der Blöcke angeben kann.|
|**Count**<br>Datentyp: Int64|Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl angeben kann.|
|**Bereich**<br>Datentyp: Schlüsselwort|Implementieren Sie diesen Parameter, sodass der Benutzer den Bereich angeben kann, der verarbeitet werden soll.|

## <a name="see-also"></a>Weitere Informationen

[Cmdlet-Parameter](./cmdlet-parameters.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
