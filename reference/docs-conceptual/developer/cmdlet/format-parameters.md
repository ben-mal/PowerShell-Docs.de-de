---
ms.date: 09/13/2016
ms.topic: reference
title: Formatparameter
description: Formatparameter
ms.openlocfilehash: 5f970683fedc71b208ff6becad761d94611a91a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652809"
---
# <a name="format-parameters"></a>Formatparameter

In der folgenden Tabelle sind die empfohlenen Namen und Funktionen für Parameter aufgeführt, die zum Formatieren von oder zum Generieren von Daten verwendet werden.

|Parameter|Funktionalität|
|---|---|
|**Möglichst**<br>Datentyp: Schlüsselwort|Implementieren Sie diesen Parameter, um das Cmdlet-Ausgabeformat anzugeben. Mögliche Werte sind z. b. Text oder Skripts.|
|**Binär (Binary)**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, um anzugeben, dass das Cmdlet binäre Werte verarbeitet.|
|**Codieren**<br>Datentyp: Schlüsselwort|Implementieren Sie diesen Parameter, um den Codierungstyp anzugeben, der unterstützt wird. Mögliche Werte sind z. b. ASCII, UTF8, Unicode, UTF7, BigEndianUnicode, Byte und String.|
|**Zeilenumbruch**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, sodass die Zeilen Umleitungs Zeichen unterstützt werden, wenn der-Parameter angegeben wird.|
|**ShortName**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, damit Kurznamen unterstützt werden, wenn der-Parameter angegeben wird.|
|**Width**<br>Datentyp: Int32|Implementieren Sie diesen Parameter, sodass der Benutzer die Breite des Ausgabegeräts angeben kann.|
|**Umschließen**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, sodass Text Wrapping unterstützt wird, wenn der-Parameter angegeben wird.|
## <a name="see-also"></a>Weitere Informationen

[Cmdlet-Parameter](./cmdlet-parameters.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
