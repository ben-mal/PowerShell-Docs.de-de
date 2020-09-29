---
ms.date: 07/29/2020
title: Neue Sprachfeatures in PowerShell 5.0
ms.openlocfilehash: dada39c4121a810c7ce87a642f232934152104e5
ms.sourcegitcommit: 339e5fc8a4cc18b4ff6956fe5180343588e40e30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87410171"
---
# <a name="new-language-features-in-powershell-50"></a><span data-ttu-id="83db1-102">Neue Sprachfeatures in PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="83db1-102">New language features in PowerShell 5.0</span></span>

<span data-ttu-id="83db1-103">PowerShell 5.0 hat die Möglichkeit zum Definieren von Klassen und anderen benutzerdefinierten Typen mithilfe formaler Syntax und Semantik hinzugefügt, die mit anderen objektorientierten Programmiersprachen vergleichbar sind.</span><span class="sxs-lookup"><span data-stu-id="83db1-103">PowerShell 5.0 added the ability to define classes and other user-defined types using formal syntax and semantics like other object-oriented programming languages.</span></span> <span data-ttu-id="83db1-104">Ziel ist es, Entwickler und IT-Experten zu ermöglichen, PowerShell für eine größere Anzahl von Anwendungsfällen zu nutzen, die Entwicklung von PowerShell-Elementen (z. B. DSC-Ressourcen) zu vereinfachen und die Abdeckung weiterer Verwaltungsschnittstellen zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="83db1-104">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

<span data-ttu-id="83db1-105">PowerShell 5.0 führt die folgenden neuen Sprachelemente in PowerShell ein:</span><span class="sxs-lookup"><span data-stu-id="83db1-105">PowerShell 5.0 introduces the following new language elements in PowerShell:</span></span>

### <a name="class-keyword"></a><span data-ttu-id="83db1-106">Schlüsselwort „Class“</span><span class="sxs-lookup"><span data-stu-id="83db1-106">Class keyword</span></span>

<span data-ttu-id="83db1-107">Das Schlüsselwort `class` definiert eine neue Klasse.</span><span class="sxs-lookup"><span data-stu-id="83db1-107">The `class` keyword defines a new class.</span></span> <span data-ttu-id="83db1-108">Es handelt sich um einen echten .NET Framework-Typ.</span><span class="sxs-lookup"><span data-stu-id="83db1-108">This is a true .NET Framework type.</span></span> <span data-ttu-id="83db1-109">Klassenmember sind öffentlich, jedoch nur innerhalb des Geltungsbereichs des Moduls.</span><span class="sxs-lookup"><span data-stu-id="83db1-109">Class members are public, but only public within the module scope.</span></span> <span data-ttu-id="83db1-110">Sie können auf den Typnamen nicht mittels einer Zeichenfolge verweisen (`New-Object` funktioniert z. B. nicht). In dieser Version können Sie zudem keinen Literaltyp (z. B. `[MyClass]`) außerhalb der Skript- oder Moduldatei verwenden, in der die Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="83db1-110">You can't refer to the type name as a string (for example, `New-Object` doesn't work), and in this release, you can't use a type literal (for example, `[MyClass]`) outside the script or module file in which the class is defined.</span></span>

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="83db1-111">Schlüsselwort „enum“ und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="83db1-111">Enum keyword and enumerations</span></span>

<span data-ttu-id="83db1-112">Das Schlüsselwort `enum` wurde hinzugefügt, welches das Zeilenumbruchzeichen als Trennzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="83db1-112">Support for the `enum` keyword has been added, which uses newline as the delimiter.</span></span> <span data-ttu-id="83db1-113">Zurzeit können Sie einen Enumerator nicht hinsichtlich sich selbst definieren.</span><span class="sxs-lookup"><span data-stu-id="83db1-113">Currently, you cannot define an enumerator in terms of itself.</span></span> <span data-ttu-id="83db1-114">Sie können aber, wie im folgenden Beispiel gezeigt, eine Enumeration hinsichtlich einer anderen Enumeration initialisieren.</span><span class="sxs-lookup"><span data-stu-id="83db1-114">However, you can initialize an enum in terms of another enum, as shown in the following example.</span></span> <span data-ttu-id="83db1-115">Darüber hinaus kann der Basistyp nicht angegeben werden. Er ist stets `[int]`.</span><span class="sxs-lookup"><span data-stu-id="83db1-115">Also, the base type cannot be specified; it is always `[int]`.</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="83db1-116">Ein Enumeratorwert muss eine Konstante zur Analysezeit sein.</span><span class="sxs-lookup"><span data-stu-id="83db1-116">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="83db1-117">Sie können ihn nicht auf das Ergebnis eines aufgerufenen Befehls festlegen.</span><span class="sxs-lookup"><span data-stu-id="83db1-117">You cannot set it to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="83db1-118">Enumerationen unterstützen arithmetische Operationen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="83db1-118">Enums support arithmetic operations, as shown in the following example.</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a><span data-ttu-id="83db1-119">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="83db1-119">Import-DscResource</span></span>

<span data-ttu-id="83db1-120">`Import-DscResource` ist jetzt ein tatsächlich dynamisches Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="83db1-120">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="83db1-121">PowerShell analysiert das Stammmodul des angegebenen Moduls und sucht Klassen, die das **DscResource**-Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="83db1-121">PowerShell parses the specified module's root module, searching for classes that contain the **DscResource** attribute.</span></span>

### <a name="implementingassembly"></a><span data-ttu-id="83db1-122">ImplementingAssembly</span><span class="sxs-lookup"><span data-stu-id="83db1-122">ImplementingAssembly</span></span>

<span data-ttu-id="83db1-123">Eine neue Feld **ImplementingAssembly** wurde zu **ModuleInfo** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="83db1-123">A new field, **ImplementingAssembly**, has been added to **ModuleInfo**.</span></span> <span data-ttu-id="83db1-124">Es ist auf die dynamische Assembly, die für ein Skriptmodul erstellt wird, wenn das Skript Klassen definiert, oder die geladene Assembly für binäre Module festgelegt.</span><span class="sxs-lookup"><span data-stu-id="83db1-124">It is set to the dynamic assembly created for a script module if the script defines classes, or the loaded assembly for binary modules.</span></span> <span data-ttu-id="83db1-125">Falls **ModuleType** = **Manifest**, wird es nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="83db1-125">It is not set when **ModuleType** is **Manifest**.</span></span>

<span data-ttu-id="83db1-126">Über eine Reflexion auf das Feld **ImplementingAssembly** werden Ressourcen in einem Modul ermittelt.</span><span class="sxs-lookup"><span data-stu-id="83db1-126">Reflection on the **ImplementingAssembly** field discovers resources in a module.</span></span> <span data-ttu-id="83db1-127">Dies bedeutet, dass Sie Ressourcen ermitteln können, die in PowerShell oder anderen verwalteten Sprachen geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="83db1-127">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

## <a name="further-reading"></a><span data-ttu-id="83db1-128">Weiterführende Themen</span><span class="sxs-lookup"><span data-stu-id="83db1-128">Further reading</span></span>

- [<span data-ttu-id="83db1-129">about_Classes</span><span class="sxs-lookup"><span data-stu-id="83db1-129">about_Classes</span></span>](/powershell/module/microsoft.powershell.core/about/about_classes)
- [<span data-ttu-id="83db1-130">about_Enum</span><span class="sxs-lookup"><span data-stu-id="83db1-130">about_Enum</span></span>](/powershell/module/microsoft.powershell.core/about/about_enum)
- [<span data-ttu-id="83db1-131">about_Classes_and_DSC</span><span class="sxs-lookup"><span data-stu-id="83db1-131">about_Classes_and_DSC</span></span>](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)
