---
title: Mengen Parameter | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 7ff6562380bb6336b08879b31d8d9fed47bfb6a7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781816"
---
# <a name="quantity-parameters"></a>Mengenparameter

In der folgenden Tabelle werden die empfohlenen Namen und Funktionen für die Anzahl von Parametern aufgelistet.

|Parameter|Funktionalität|
|---|---|
|**Alle**<br>Datentyp: Boolescher Wert|Implementieren Sie diesen Parameter, damit `true` angibt, dass alle Ressourcen anstelle einer Standard Teilmenge von Ressourcen bearbeitet werden sollten. Implementieren Sie diesen Parameter, sodass `false` eine Teilmenge der Ressourcen angibt.|
|**Speicherbelegung**<br>Datentyp: Int32|Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl der zuzuordnenden Elemente angeben kann.|
|**Blockcount**<br>Datentyp: Int64|Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl der Blöcke angeben kann.|
|**Count**<br>Datentyp: Int64|Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl angeben kann.|
|**Umfang**<br>Datentyp: Schlüsselwort|Implementieren Sie diesen Parameter, sodass der Benutzer den Bereich angeben kann, der verarbeitet werden soll.|

## <a name="see-also"></a>Weitere Informationen

[Cmdlet-Parameter](./cmdlet-parameters.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
