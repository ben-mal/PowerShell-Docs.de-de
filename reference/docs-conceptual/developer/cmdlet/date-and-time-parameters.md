---
ms.date: 09/13/2016
ms.topic: reference
title: Datums- und Zeitparameter
description: Datums- und Zeitparameter
ms.openlocfilehash: 2f73d16ca8261ebc4ca8d2c18aff4176d7d7314c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653188"
---
# <a name="date-and-time-parameters"></a>Datums- und Zeitparameter

In der folgenden Tabelle werden die empfohlenen Namen und Funktionen für Parameter aufgelistet, die Datums-und Uhrzeit Informationen verarbeiten. Datums-und Uhrzeit Parameter werden normalerweise verwendet, um aufzuzeichnen, wann etwas erstellt oder auf das zugegriffen wird.

|Parameter|Funktionalität|
|---|---|
|**Auf**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, sodass das Cmdlet bei Angabe des-Cmdlets mit den Ressourcen arbeiten kann, auf die basierend auf dem von den Parametern **before** und **after** angegebenen Datum und der angegebenen Uhrzeit zugegriffen wurde. Wenn dieser Parameter angegeben wird, dürfen die **erstellten** und **geänderten** Parameter nicht angegeben werden.|
|**Nachher**<br>Datentyp: DateTime|Implementieren Sie diesen Parameter, um das Datum und die Uhrzeit anzugeben, nach der das Cmdlet verwendet wurde. Damit der **after** -Parameter funktioniert, muss das Cmdlet auch über einen Parameter verfügen, auf den **zugegriffen**, **erstellt** oder **geändert** wurde. Und dieser Parameter muss auf **true** festgelegt werden, wenn das Cmdlet aufgerufen wird.|
|**Vorher**<br>Datentyp: DateTime|Implementieren Sie diesen Parameter, um das Datum und die Uhrzeit anzugeben, zu der das Cmdlet verwendet wurde. Damit der **before** -Parameter funktioniert, muss das Cmdlet auch über einen **Zugriffs**-, **Erstellungs** **-oder Änderungs** Parameter verfügen. Und dieser Parameter muss auf **true** festgelegt werden, wenn das Cmdlet aufgerufen wird.|
|**Erstellt**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, sodass das Cmdlet bei Angabe des-Cmdlets mit den Ressourcen arbeitet, die basierend auf dem von den Parametern **before** und **after** angegebenen Datum und der angegebenen Uhrzeit erstellt wurden. Wenn dieser Parameter angegeben wird, dürfen **die Parameter,** auf die **zugegriffen** wird, nicht angegeben werden.|
|**Exact**<br>Datentyp: Switchparameter|Implementieren Sie diesen Parameter, sodass der Ressourcen Begriff bei der Angabe genau mit dem Ressourcennamen übereinstimmen muss. Wenn der-Parameter nicht angegeben wird, müssen der Ressourcen Begriff und der Name nicht exakt übereinstimmen.|
|**Geändert**<br>Datentyp: DateTime|Implementieren Sie diesen Parameter, sodass das Cmdlet bei Angabe des Datums und der Uhrzeit, die durch die Parameter **before** und **after** festgelegt wurden, auf Ressourcen angewendet wird, die geändert wurden. Wenn dieser Parameter angegeben wird, dürfen **die Parameter,** auf die **zugegriffen** wird, nicht angegeben werden.|
## <a name="see-also"></a>Weitere Informationen

[Cmdlet-Parameter](./cmdlet-parameters.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
