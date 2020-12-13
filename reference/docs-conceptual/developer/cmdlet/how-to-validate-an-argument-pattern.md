---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen eines Argumentmusters
description: Überprüfen eines Argumentmusters
ms.openlocfilehash: ab5777c918a53c0a3900f87c52e7f14f9cb9b726
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666908"
---
# <a name="how-to-validate-an-argument-pattern"></a>Überprüfen eines Argumentmusters

In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit das Zeichen Muster des Parameter Arguments vor dem Ausführen des Cmdlets überprüfen kann. Diese Validierungs Regel legen Sie fest, indem Sie das validatepattern-Attribut deklarieren.

> [!NOTE]
> Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).

## <a name="to-validate-an-argument-pattern"></a>So validieren Sie ein Argument Muster

- Fügen Sie das Validate-Attribut hinzu, wie im folgenden Code gezeigt. In diesem Beispiel wird ein Muster von vier Ziffern angegeben, wobei jede Ziffer den Wert 0 bis 9 hat.

    ```csharp
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }

    private int inputData;
    ```

Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validatepattern-Attribut Deklaration](./validatepattern-attribute-declaration.md).

## <a name="see-also"></a>Weitere Informationen

[Attributdeklaration: ValidatePattern](./validatepattern-attribute-declaration.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
