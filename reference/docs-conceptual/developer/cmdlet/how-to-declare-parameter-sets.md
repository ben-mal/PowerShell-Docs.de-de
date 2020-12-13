---
ms.date: 09/13/2016
ms.topic: reference
title: Deklarieren von Parametersätzen
description: Deklarieren von Parametersätzen
ms.openlocfilehash: bd4d504a9fe6c7f7626901c49bc08851244f0995
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667061"
---
# <a name="how-to-declare-parameter-sets"></a>Deklarieren von Parametersätzen

In diesem Beispiel wird gezeigt, wie zwei Parametersätze definiert werden, wenn Sie die Parameter für ein Cmdlet deklarieren. Jeder Parametersatz verfügt sowohl über einen eindeutigen Parameter als auch über einen freigegebenen Parameter, der von beiden Parametersätzen verwendet wird. Weitere Informationen zu Parametersätzen, einschließlich der Angabe des Standardparameter Satzes, finden Sie unter [Cmdlet-Parametersätze](./cmdlet-parameter-sets.md).

> [!IMPORTANT]
> Definieren Sie nach Möglichkeit den eindeutigen Parameter eines Parameter Satzes als erforderlichen Parameter. Wenn Sie jedoch möchten, dass das Cmdlet ohne Angabe von Parametern ausgeführt wird, kann der Unique-Parameter ein optionaler Parameter sein. Beispielsweise ist der Unique-Parameter des `Get-Command` Cmdlets optional.

## <a name="how-to-define-two-parameter-sets"></a>Definieren von zwei Parameter Sätzen

1. Fügen Sie dem `ParameterSet` Parameter-Attribut für den Unique-Parameter des ersten Parameter Satzes das-Schlüsselwort hinzu.

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test01")]
   public string UserName
   {
     get { return userName; }
     set { userName = value; }
   }
   private string userName;
   ```

2. Fügen Sie das- `ParameterSet` Schlüsselwort zum Parameter-Attribut für den eindeutigen Parameter des zweiten Parameter Satzes hinzu.

   ```csharp
   [Parameter(Position = 0, Mandatory = true,
              ParameterSetName = "Test02")]
   public string ComputerName
   {
     get { return computerName; }
     set { computerName = value; }
   }
   private string computerName;
   ```

3. Fügen Sie für den Parameter, der zu beiden Parametersätzen gehört, ein Parameter Attribut für jeden Parametersatz hinzu, und fügen Sie dann `ParameterSet` jedem Satz das Schlüsselwort hinzu. In jedem Parameter Attribut können Sie angeben, wie dieser Parameter definiert wird. Ein Parameter kann in einem Satz optional sein und in einem anderen obligatorisch sein.

   ```csharp
   [Parameter(Mandatory= true, ParameterSetName = "Test01")]
   [Parameter(ParameterSetName = "Test02")]
   public string SharedParam
   {
       get { return sharedParam; }
       set { sharedParam = value; }
   }
   private string sharedParam;
   ```

## <a name="see-also"></a>Weitere Informationen

[Cmdlet-Parametersätze](./cmdlet-parameter-sets.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
