---
title: Validieren der Argument Länge | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, example
ms.openlocfilehash: aa0545def6d9628f6b41090a425f0c5af25f6ad7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784077"
---
# <a name="how-to-validate-the-argument-length"></a>Überprüfen einer Argumentlänge

In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit die Anzahl der Zeichen (die Länge) des Parameter Arguments vor dem Ausführen des Cmdlets überprüfen kann. Diese Validierungs Regel legen Sie fest, indem Sie das validateLength-Attribut deklarieren.

> [!NOTE]
> Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).

## <a name="to-validate-the-argument-length"></a>So überprüfen Sie die Argument Länge

- Fügen Sie das Validate-Attribut hinzu, wie im folgenden Code gezeigt. In diesem Beispiel wird angegeben, dass die Länge des Arguments eine Länge von 0 bis 10 Zeichen aufweisen soll.

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validateLength-Attribut Deklaration](./validatelength-attribute-declaration.md).

## <a name="see-also"></a>Weitere Informationen

[Attributdeklaration: ValidateLength](./validatelength-attribute-declaration.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
