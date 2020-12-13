---
ms.date: 09/13/2016
ms.topic: reference
title: Eigenschaftenparameter
description: Eigenschaftenparameter
ms.openlocfilehash: eff51fcd395e5f9570193ea91684f9e70030bc7d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652594"
---
# <a name="property-parameters"></a>Eigenschaftenparameter

In der folgenden Tabelle sind die empfohlenen Namen und Funktionen für Eigenschafts Parameter aufgeführt.

|Parameter|Funktionalität|
|---|---|
|**Count**<br>Datentyp: Int32|Implementieren Sie diesen Parameter, sodass der Benutzer die Anzahl der zu verarbeitenden Objekte angeben kann.|
|**Beschreibung**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine Beschreibung für eine Ressource angeben kann.|
|**From**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer das Verweis Objekt angeben kann, aus dem Informationen abgeleitet werden sollen.|
|**Id**<br>Datentyp: Ressourcen abhängig|Implementieren Sie diesen Parameter, sodass der Benutzer den Bezeichner einer Ressource angeben kann.|
|**Eingabe**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer die Eingabedatei Spezifikation angeben kann.|
|**Location**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Speicherort der Ressource angeben kann.|
|**LogName**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Namen der Protokolldatei angeben kann, die verarbeitet oder verwendet werden soll.|
|**Name**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Namen der Ressource angeben kann.|
|**Ausgabe**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer die Ausgabedatei angeben kann.|
|**Besitzer**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Namen des Besitzers der Ressource angeben kann.|
|**Eigenschaft**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Namen oder die Namen der zu verwendenden Eigenschaften angeben kann.|
|**`Reason`**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer angeben kann, warum dieses Cmdlet aufgerufen wird.|
|**Regex**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, sodass reguläre Ausdrücke verwendet werden, wenn der-Parameter angegeben wird. Wenn dieser Parameter angegeben wird, werden Platzhalter Zeichen nicht aufgelöst.|
|**Geschwindigkeit**<br>Datentyp: Int32|Implementieren Sie diesen Parameter, sodass der Benutzer die Baudrate angeben kann. Der Benutzer legt diesen Parameter auf die Geschwindigkeit der Ressource fest.|
|**Zustand**<br>Datentyp: Schlüsselwort Array|Implementieren Sie diesen Parameter, sodass der Benutzer die Namen von Zuständen angeben kann, z. b. KeyDown.|
|**Wert**<br>Datentyp: Object|Implementieren Sie diesen Parameter, sodass der Benutzer einen Wert angeben kann, der für das Cmdlet bereitgestellt werden soll.|
|**Version**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer die Version der Eigenschaft angeben kann.|

## <a name="see-also"></a>Weitere Informationen

[Cmdlet-Parameter](./cmdlet-parameters.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
