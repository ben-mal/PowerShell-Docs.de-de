---
ms.date: 09/13/2016
ms.topic: reference
title: Überprüfen eines Argumentsatzes
description: Überprüfen eines Argumentsatzes
ms.openlocfilehash: 50ec0a48277893584d896e14ad6aa843682a28cc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650361"
---
# <a name="how-to-validate-an-argument-set"></a>Überprüfen eines Argumentsatzes

Dieses Beispiel zeigt, wie Sie eine Validierungs Regel angeben, mit der die Windows PowerShell-Laufzeit das Parameter Argument vor dem Ausführen des Cmdlets überprüfen kann. Diese Validierungs Regel stellt einen Satz gültiger Werte für das Parameter Argument bereit.

> [!NOTE]
> Weitere Informationen zu der Klasse, die dieses Attribut definiert, finden Sie unter [System. Management. Automation. validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).

## <a name="to-validate-an-argument-set"></a>So validieren Sie einen Argument Satz

- Fügen Sie das validateset-Attribut hinzu, wie im folgenden Code gezeigt. In diesem Beispiel wird ein Satz von drei möglichen Werten für den- `UserName` Parameter angegeben.

    ```csharp
    [ValidateSet("Steve", "Mary", "Carl", IgnoreCase = true)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }

    private string userName;
    ```

Weitere Informationen zum Deklarieren dieses Attributs finden Sie unter [validateset-Attribut Deklaration](./validateset-attribute-declaration.md).

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[Attributdeklaration: ValidateSet](./validateset-attribute-declaration.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
