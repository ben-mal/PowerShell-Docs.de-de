---
ms.date: 07/29/2020
title: Neue Sprachfeatures in PowerShell 5.0
description: PowerShell 5.0 hat die Möglichkeit zum Definieren von Klassen und anderen benutzerdefinierten Typen mithilfe formaler Syntax und Semantik hinzugefügt, die mit anderen objektorientierten Programmiersprachen vergleichbar sind.
ms.openlocfilehash: 31ff54ba6f2800a0680c1a2db3832ca97246973d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663302"
---
# <a name="new-language-features-in-powershell-50"></a>Neue Sprachfeatures in PowerShell 5.0

PowerShell 5.0 hat die Möglichkeit zum Definieren von Klassen und anderen benutzerdefinierten Typen mithilfe formaler Syntax und Semantik hinzugefügt, die mit anderen objektorientierten Programmiersprachen vergleichbar sind. Ziel ist es, Entwickler und IT-Experten zu ermöglichen, PowerShell für eine größere Anzahl von Anwendungsfällen zu nutzen, die Entwicklung von PowerShell-Elementen (z. B. DSC-Ressourcen) zu vereinfachen und die Abdeckung weiterer Verwaltungsschnittstellen zu beschleunigen.

PowerShell 5.0 führt die folgenden neuen Sprachelemente in PowerShell ein:

### <a name="class-keyword"></a>Schlüsselwort „Class“

Das Schlüsselwort `class` definiert eine neue Klasse. Es handelt sich um einen echten .NET Framework-Typ. Klassenmember sind öffentlich, jedoch nur innerhalb des Geltungsbereichs des Moduls. Sie können auf den Typnamen nicht mittels einer Zeichenfolge verweisen (`New-Object` funktioniert z. B. nicht). In dieser Version können Sie zudem keinen Literaltyp (z. B. `[MyClass]`) außerhalb der Skript- oder Moduldatei verwenden, in der die Klasse definiert ist.

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a>Schlüsselwort „enum“ und Enumerationen

Das Schlüsselwort `enum` wurde hinzugefügt, welches das Zeilenumbruchzeichen als Trennzeichen verwendet. Zurzeit können Sie einen Enumerator nicht hinsichtlich sich selbst definieren. Sie können aber, wie im folgenden Beispiel gezeigt, eine Enumeration hinsichtlich einer anderen Enumeration initialisieren. Darüber hinaus kann der Basistyp nicht angegeben werden. Er ist stets `[int]`.

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

Ein Enumeratorwert muss eine Konstante zur Analysezeit sein. Sie können ihn nicht auf das Ergebnis eines aufgerufenen Befehls festlegen.

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

Enumerationen unterstützen arithmetische Operationen, wie im folgenden Beispiel dargestellt.

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a>Import-DscResource

`Import-DscResource` ist jetzt ein tatsächlich dynamisches Schlüsselwort. PowerShell analysiert das Stammmodul des angegebenen Moduls und sucht Klassen, die das **DscResource** -Attribut enthalten.

### <a name="implementingassembly"></a>ImplementingAssembly

Eine neue Feld **ImplementingAssembly** wurde zu **ModuleInfo** hinzugefügt. Es ist auf die dynamische Assembly, die für ein Skriptmodul erstellt wird, wenn das Skript Klassen definiert, oder die geladene Assembly für binäre Module festgelegt. Falls **ModuleType** = **Manifest** , wird es nicht festgelegt.

Über eine Reflexion auf das Feld **ImplementingAssembly** werden Ressourcen in einem Modul ermittelt. Dies bedeutet, dass Sie Ressourcen ermitteln können, die in PowerShell oder anderen verwalteten Sprachen geschrieben wurden.

## <a name="further-reading"></a>Weiterführende Themen

- [about_Classes](/powershell/module/microsoft.powershell.core/about/about_classes)
- [about_Enum](/powershell/module/microsoft.powershell.core/about/about_enum)
- [about_Classes_and_DSC](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)
