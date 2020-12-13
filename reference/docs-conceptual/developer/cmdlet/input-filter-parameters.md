---
ms.date: 09/13/2016
ms.topic: reference
title: Eingabe von Filterparametern
description: Eingabe von Filterparametern
ms.openlocfilehash: 419ffea2afb4aa534a3e19ecdfce6d6af1da46a6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648525"
---
# <a name="input-filter-parameters"></a>Eingabe von Filterparametern

Ein Cmdlet kann `Filter` -, `Include` -und-Parameter definieren, die `Exclude` den Satz von Eingabe Objekten filtern, auf die sich das Cmdlet auswirkt.

In der Regel wird der Satz von Eingabe Objekten durch einen- `InputObject` ,-oder-Parameter angegeben `Path` `Name` . Ein Cmdlet kann z. b. über einen Parameter verfügen, der `Path` mehrere Pfade mithilfe von Platzhalter Zeichen annimmt, und jeder Pfad verweist auf ein Eingabe Objekt. `Filter` `Include` Mit den Parametern, und werden `Exclude` die Pfade, die das Cmdlet bei jedem Aufruf verwendet, weiter qualifiziert.

## <a name="include-and-exclude-parameters"></a>Einschließen und Ausschließen von Parametern

Der `Include` -Parameter und der- `Exclude` Parameter identifizieren die Objekte, die in den Satz der an das Cmdlet weiter gegebenen Eingabe Objekte eingeschlossen oder ausgeschlossen werden. Verwenden Sie diese Parameter, wenn der Filter in der standardmäßigen Platzhalter Sprache ausgedrückt werden kann. (Weitere Informationen zu Platzhalter Zeichen finden Sie [unter unterstützen von Platzhaltern in Cmdlet-Parametern](./supporting-wildcard-characters-in-cmdlet-parameters.md).) Der- `Include` Parameter enthält alle-Objekte, deren Namen dem Inklusions Filter entsprechen. Der- `Exclude` Parameter schließt alle Objekte aus, deren Namen dem Filter entsprechen.

## <a name="filter-parameter"></a>Filter Parameter

Der- `Filter` Parameter gibt einen Filter an, der nicht in der standardmäßigen Platzhalter Sprache ausgedrückt wird. Beispielsweise können Active Directory Service Interfaces (ADSI) oder SQL-Filter über den Parameter an das Cmdlet übergeben werden `Filter` . In den Cmdlets, die von Windows PowerShell bereitgestellt werden, werden diese Filter von den Windows PowerShell-Anbietern angegeben, die das Cmdlet für den Zugriff auf einen Datenspeicher verwenden. Jeder Anbieter definiert in der Regel seinen eigenen Filter.

## <a name="filtering-if-no-set-of-input-objects-is-specified"></a>Filterung, wenn kein Satz von Eingabe Objekten angegeben ist

Wenn kein Satz von Eingabe Objekten angegeben ist, bedeutet dies normalerweise, dass alle Objekte gefiltert werden. Weitere Informationen finden Sie unter[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process).

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
