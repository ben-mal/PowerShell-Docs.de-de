---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen einer Argumentanzahl
description: Überprüfen einer Argumentanzahl
ms.openlocfilehash: 46a32d61138fb50bceea98171f76749c9d96734d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666942"
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
