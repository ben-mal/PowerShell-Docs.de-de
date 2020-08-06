---
title: Ressourcen Parameter | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e618951d57ff1cf303b38f0278858144df31afaf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786525"
---
# <a name="resource-parameters"></a>Ressourcenparameter

In der folgenden Tabelle sind die empfohlenen Namen und Funktionen für Ressourcen Parameter aufgeführt. Bei diesen Parametern kann es sich bei den Ressourcen um die Assembly handeln, die die Cmdlet-Klasse enthält, oder um die Host Anwendung, die das Cmdlet ausgeführt hat.

|Parameter|Funktionalität|
|---|---|
|**Anwendung**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine Anwendung angeben kann.|
|**Assembly**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine Assembly angeben kann.|
|**Attribut**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer ein Attribut angeben kann.|
|**Klasse**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine Microsoft .NET Framework-Klasse angeben kann.|
|**Cluster**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer einen Cluster angeben kann.|
|**Kultur**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer die Kultur angeben kann, in der das Cmdlet ausgeführt werden soll.|
|**Domäne**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Domänen Namen angeben kann.|
|**Laufwerk**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer einen Laufwerks Namen angeben kann.|
|**Event**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer einen Ereignis Namen angeben kann.|
|**Interface**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer einen Netzwerkschnittstellen Namen angeben kann.|
|**IpAddress**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine IP-Adresse angeben kann.|
|**Job**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer einen Auftrag angeben kann.|
|**LiteralPath**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Pfad zu einer Ressource angeben kann, wenn Platzhalter Zeichen nicht unterstützt werden. (Verwenden Sie den **path** -Parameter, wenn Platzhalter Zeichen unterstützt werden.)|
|**Mac**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer eine Mac-Adresse (Media Access Controller) angeben kann.|
|**ParentID**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den übergeordneten Bezeichner angeben kann.|
|**Pfad**<br>Datentyp: String, String []|Implementieren Sie diesen Parameter, sodass der Benutzer die Pfade zu einer Ressource angeben kann, wenn Platzhalter Zeichen unterstützt werden. (Verwenden Sie den **literalpath** -Parameter, wenn Platzhalter Zeichen nicht unterstützt werden.) Es wird empfohlen, diesen Parameter zu entwickeln, damit er die vollständige Syntax unterstützt, die `provider:path` von Anbietern verwendet wird. Außerdem wird empfohlen, dass Sie Sie so entwickeln, dass Sie mit so vielen Anbietern wie möglich funktioniert.|
|**Port**<br>Datentyp: Integer, String|Implementieren Sie diesen Parameter, sodass der Benutzer einen ganzzahligen Wert für das Netzwerk oder einen Zeichen folgen Wert, z. b. "BizTalk", für andere Port Typen angeben kann.|
|**Drucker**<br>Datentyp: Integer, String|Implementieren Sie diesen Parameter, sodass der Benutzer den Drucker angeben kann, den das Cmdlet verwenden soll.|
|**Größe**<br>Datentyp: Int32|Implementieren Sie diesen Parameter, sodass der Benutzer eine Größe angeben kann.|
|**Drüse**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer einen Transaktions Bezeichner (TID) für das Cmdlet angeben kann.|
|**Typ**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer den Typ der Ressource angeben kann, für die der Betrieb ausgeführt werden soll.|
|**URL**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer einen Uniform Resource Locator (URL) angeben kann.|
|**Benutzer**<br>Datentyp: Zeichenfolge|Implementieren Sie diesen Parameter, sodass der Benutzer seinen Namen oder den Namen eines anderen Benutzers angeben kann.|

## <a name="see-also"></a>Weitere Informationen

[Cmdlet-Parameter](./cmdlet-parameters.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
