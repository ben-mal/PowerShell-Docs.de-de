---
title: Parameter Aliase | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e320eeb4d2ab91acf2116fdc817a50e93c82aead
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781986"
---
# <a name="parameter-aliases"></a>Parameteraliase

Cmdlet-Parameter können auch Aliase enthalten. Sie können die Aliase anstelle der Parameternamen verwenden, wenn Sie den-Parameter in einem-Befehl eingeben oder angeben.

## <a name="benefits-of-using-aliases"></a>Vorteile der Verwendung von Aliasen

Das Hinzufügen von Aliasen zu Parametern bietet die folgenden Vorteile.

- Sie können eine Verknüpfung bereitstellen, sodass der Benutzer nicht den kompletten Parameternamen verwenden muss, wenn das Cmdlet aufgerufen wird. Beispielsweise können Sie den Alias "CN" anstelle des Parameter namens "Computername" verwenden.

- Sie können mehrere Aliase definieren, wenn Sie unterschiedliche Namen für denselben Parameter angeben möchten. Möglicherweise möchten Sie mehrere Aliase definieren, wenn Sie mit mehreren Benutzergruppen arbeiten müssen, die auf unterschiedliche Weise auf dieselben Daten verweisen.

- Sie können die Abwärtskompatibilität für vorhandene Skripts bereitstellen, wenn sich der Name eines Parameters ändert.

- Mithilfe des Alias-Attributs und des valuefrompipelinebyname-Attributs können Sie einen Parameter definieren, mit dem das Cmdlet an verschiedene Objekttypen gebunden werden kann. Angenommen, Sie haben zwei Objekte verschiedener Typen, und das erste Objekt verfügte über eine Writer-Eigenschaft, und das zweite Objekt verfügte über eine Editor-Eigenschaft. Wenn das Cmdlet über einen Parameter verfügt, der über Writer-und Editor-Aliase verfügt und das Cmdlet Pipeline Eingaben auf der Grundlage von Eigenschaftsnamen akzeptiert hat, könnte das Cmdlet mithilfe der beiden Parameter Aliase eine Bindung an beide Objekte herstellen.

Weitere Informationen zu Aliasen, die mit bestimmten Parametern verwendet werden können, finden Sie unter [Allgemeine Parameternamen](./common-parameter-names.md).

## <a name="defining-parameter-aliases"></a>Definieren von Parameter Aliasen

Um einen Alias für einen Parameter zu definieren, deklarieren Sie das Alias Attribut, wie in der folgenden Parameter Deklaration gezeigt. In diesem Beispiel werden mehrere Aliase für denselben Parameter definiert. (Weitere Informationen finden Sie unter[Deklarieren von Cmdlet-Parametern](./how-to-declare-cmdlet-parameters.md).)

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

## <a name="see-also"></a>Weitere Informationen

[Allgemeine Parameternamen](./common-parameter-names.md)

[Deklarieren von Cmdlet-Parametern](./how-to-declare-cmdlet-parameters.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
