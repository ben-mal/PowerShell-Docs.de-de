---
title: Validieren einer Argument Anzahl | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateCount attribute, example
ms.openlocfilehash: e7c0eb364a6975cec089b984c2100d476631a12d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782122"
---
# <a name="how-to-validate-an-argument-count"></a>Überprüfen einer Argumentanzahl

In diesem Beispiel wird gezeigt, wie eine Validierungs Regel angegeben wird, mit der die Windows PowerShell-Laufzeit die Anzahl der Argumente (die Anzahl) überprüfen kann, die ein Parameter annimmt, bevor das Cmdlet ausgeführt wird. Diese Validierungs Regel legen Sie fest, indem Sie das validatecount-Attribut deklarieren.

> [!NOTE]
> Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatezähltattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).

## <a name="to-validate-an-argument-count"></a>So überprüfen Sie eine Argument Anzahl

- Fügen Sie das Validate-Attribut hinzu, wie im folgenden Code gezeigt. In diesem Beispiel wird angegeben, dass der-Parameter ein Argument oder bis zu drei Argumente akzeptiert.

    ```csharp
    [ValidateCount(1, 3)]
    [Parameter(Position = 0, Mandatory = true)]
    public string[] UserNames
    {
      get { return userNames; }
      set { userNames = value; }
    }

    private string[] userNames;
    ```

Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validatecount-Attribut Deklaration](./validatecount-attribute-declaration.md).

## <a name="see-also"></a>Weitere Informationen

[Attributdeklaration: ValidateCount](./validatecount-attribute-declaration.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
