---
title: Validieren eines Argument Musters | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- ValidatePattern attribute, example
ms.openlocfilehash: 35104e786d4b809a711d97fea52ae0e348dd5ca3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782088"
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
