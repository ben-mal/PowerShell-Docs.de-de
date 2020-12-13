---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen eines Argumentbereichs
description: Überprüfen eines Argumentbereichs
ms.openlocfilehash: 1c1c53d43350a38beb2193200de3bd6b689366a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666925"
---
# <a name="how-to-validate-an-argument-range"></a>Überprüfen eines Argumentbereichs

In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit den minimalen und maximalen Wert des Parameter Arguments vor dem Ausführen des Cmdlets überprüfen kann. Diese Validierungs Regel legen Sie fest, indem Sie das validaterange-Attribut deklarieren.

> [!NOTE]
> Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).

### <a name="to-validate-an-argument-range"></a>So validieren Sie einen Argument Bereich

- Fügen Sie das validaterange-Attribut hinzu, wie im folgenden Code gezeigt. In diesem Beispiel wird ein Bereich von 0 bis 5 für den- `InputData` Parameter angegeben.

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validaterange-Attribut Deklaration](./validaterange-attribute-declaration.md).

## <a name="see-also"></a>Weitere Informationen

[Attributdeklaration: ValidateRange](./validaterange-attribute-declaration.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
