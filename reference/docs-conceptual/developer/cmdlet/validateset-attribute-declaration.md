---
ms.date: 09/13/2016
ms.topic: reference
title: 'Attributdeklaration: ValidateSet'
description: 'Attributdeklaration: ValidateSet'
ms.openlocfilehash: 7894d00561366ada492911e8147acbd8d3454a55
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660462"
---
# <a name="validateset-attribute-declaration"></a>Attributdeklaration: ValidateSet

Das validatesetattribute-Attribut gibt einen Satz möglicher Werte für ein Cmdlet-Parameter Argument an. Dieses Attribut kann auch von Windows PowerShell-Funktionen verwendet werden.

Wenn dieses Attribut angegeben wird, bestimmt die Windows PowerShell-Laufzeit, ob das angegebene Argument für den Cmdlet-Parameter mit einem Element im angegebenen Element Satz übereinstimmt. Das-Cmdlet wird nur ausgeführt, wenn das Parameter Argument mit einem Element im Satz übereinstimmt. Wenn keine Entsprechung gefunden wird, wird von der Windows PowerShell-Laufzeit ein Fehler ausgelöst.

## <a name="syntax"></a>Syntax

```csharp
[ValidateSetAttribute(params string[] validValues)]
[ValidateSetAttribute(params string[] validValues, Named Parameters)]
```

#### <a name="parameters"></a>Parameter

`ValidValues` ([System. String](/dotnet/api/System.String)) erforderlich. Gibt die gültigen Parameter Element Werte an. Im folgenden Beispiel wird gezeigt, wie ein-Element oder mehrere-Elemente angegeben werden.

```csharp
[ValidateSetAttribute("Steve")]
[ValidateSetAttribute("Steve","Mary")]
```

`IgnoreCase` ([System. Boolean](/dotnet/api/System.Boolean)) optionaler benannter Parameter. Der Standardwert `true` gibt an, dass der Fall ignoriert wird. Bei einem Wert von `false` wird beim Cmdlet die Groß-/Kleinschreibung beachtet.

## <a name="remarks"></a>Bemerkungen

- Dieses Attribut kann nur einmal pro Parameter verwendet werden.

- Wenn der Parameterwert ein Array ist, muss jedes Element des Arrays mit einem Element des Attribut Satzes identisch sein.

- Das validatesetattribute-Attribut wird von der [System. Management. Automation. validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute) -Klasse definiert.

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
