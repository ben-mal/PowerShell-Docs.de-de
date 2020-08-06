---
title: Validieren eines Argument Satzes | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateSet attribute, example
ms.openlocfilehash: 6173f1380583f5b27e2b188990a5ea041f447c57
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782003"
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
