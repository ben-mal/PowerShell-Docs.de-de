---
ms.date: 09/13/2016
ms.topic: reference
title: Deklarieren von Cmdlet-Parametern
description: Deklarieren von Cmdlet-Parametern
ms.openlocfilehash: ed53f9788c9afb142b137e08966dff33551b9d0f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667095"
---
# <a name="how-to-declare-cmdlet-parameters"></a>Deklarieren von Cmdlet-Parametern

In diesen Beispielen wird gezeigt, wie benannte, positionelle, erforderliche, optionale und Switch-Parameter deklariert werden. Diese Beispiele zeigen auch, wie ein parameteralias definiert wird.

## <a name="how-to-declare-a-named-parameter"></a>Deklarieren eines benannten Parameters

- Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt. Wenn Sie das Parameter Attribut hinzufügen, lassen Sie das- `Position` Schlüsselwort aus dem-Attribut Weg.

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-positional-parameter"></a>Deklarieren eines Positions Parameters

- Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt. Wenn Sie das Parameter-Attribut hinzufügen, legen Sie das- `Position` Schlüsselwort auf die Argument Position fest. Der Wert 0 gibt die erste Position an.

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-mandatory-parameter"></a>Deklarieren eines obligatorischen Parameters

- Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt. Wenn Sie das Parameter-Attribut hinzufügen, legen Sie das- `Mandatory` Schlüsselwort auf fest `true` .

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).

## <a name="how-to-declare-an-optional-parameter"></a>So deklarieren Sie einen optionalen Parameter

- Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt. Wenn Sie das Parameter Attribut hinzufügen, lassen Sie das `Mandatory` Schlüsselwort aus.

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a>Deklarieren eines Switch-Parameters

- Definieren Sie eine öffentliche Eigenschaft als Typ " [System. Management. Automation. Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter)", und deklarieren Sie dann das Parameter Attribut.

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

Weitere Informationen zum Parameter Attribut finden Sie unter [Parameter Attribut Deklaration](./parameter-attribute-declaration.md).

## <a name="how-to-declare-a-parameter-with-aliases"></a>Deklarieren eines Parameters mit Aliasen

- Definieren Sie eine öffentliche Eigenschaft, wie im folgenden Code gezeigt. Fügen Sie ein Alias Attribut hinzu, das die Aliase für den Parameter auflistet. In diesem Beispiel werden drei Aliase für denselben Parameter definiert. Der erste Alias stellt eine Verknüpfung bereit. Die zweite und dritte Aliase stellen Namen bereit, die Sie für verschiedene Szenarien verwenden können.

    ```csharp
    [Alias("UN","Writer","Editor")]
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Weitere Informationen zum Alias Attribut finden Sie unter [Alias Attribut Deklaration](./alias-attribute-declaration.md).

## <a name="see-also"></a>Weitere Informationen

[System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)

[Attributdeklaration: Parameter](./parameter-attribute-declaration.md)

[Attributdeklaration: Alias](./alias-attribute-declaration.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
