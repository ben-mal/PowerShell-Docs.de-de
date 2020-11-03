---
description: Beschreibt ein Attribut, das den Typ des Objekts angibt, welches die Funktion zurückgibt.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_OutputTypeAttribute
ms.openlocfilehash: 7cd7f04941077d823bb15d0fa393ca241f38ae3b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220468"
---
# <a name="about-functions-outputtypeattribute"></a><span data-ttu-id="fae5b-104">Informationen zu Funktionen outputtypeer Attribute</span><span class="sxs-lookup"><span data-stu-id="fae5b-104">About Functions OutputTypeAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="fae5b-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fae5b-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="fae5b-106">Beschreibt ein Attribut, das den Typ des Objekts angibt, welches die Funktion zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fae5b-106">Describes an attribute that reports the type of object that the function returns.</span></span>

## <a name="long-description"></a><span data-ttu-id="fae5b-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fae5b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="fae5b-108">Das OutputType-Attribut listet die .NET-Objekttypen auf, die von den Funktionen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fae5b-108">The OutputType attribute lists the .NET types of objects that the functions returns.</span></span> <span data-ttu-id="fae5b-109">Sie können den optionalen parametersetname-Parameter verwenden, um unterschiedliche Ausgabetypen für jeden Parametersatz aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="fae5b-109">You can use its optional ParameterSetName parameter to list different output types for each parameter set.</span></span>

<span data-ttu-id="fae5b-110">Das OutputType-Attribut wird für einfache und erweiterte Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fae5b-110">The OutputType attribute is supported on simple and advanced functions.</span></span> <span data-ttu-id="fae5b-111">Es ist unabhängig vom cmdletbinding-Attribut.</span><span class="sxs-lookup"><span data-stu-id="fae5b-111">It is independent of the CmdletBinding attribute.</span></span>

<span data-ttu-id="fae5b-112">Das OutputType-Attribut stellt den Wert der OutputType-Eigenschaft des **System. Management. Automation. functioninfo** -Objekts bereit, das vom `Get-Command` Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fae5b-112">The OutputType attribute provides the value of the OutputType property of the **System.Management.Automation.FunctionInfo** object that the `Get-Command` cmdlet returns.</span></span>

<span data-ttu-id="fae5b-113">Der Wert des Attributs OutputType ist nur ein Dokumentationshinweis.</span><span class="sxs-lookup"><span data-stu-id="fae5b-113">The OutputType attribute value is only a documentation note.</span></span> <span data-ttu-id="fae5b-114">Sie wird nicht vom Funktionscode abgeleitet oder mit der tatsächlichen funktionsausgabe verglichen.</span><span class="sxs-lookup"><span data-stu-id="fae5b-114">It is not derived from the function code or compared to the actual function output.</span></span> <span data-ttu-id="fae5b-115">Daher ist der Wert möglicherweise ungenau.</span><span class="sxs-lookup"><span data-stu-id="fae5b-115">As such, the value might be inaccurate.</span></span>

## <a name="syntax"></a><span data-ttu-id="fae5b-116">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fae5b-116">SYNTAX</span></span>

<span data-ttu-id="fae5b-117">Das OutputType-Attribut von Functions weist die folgende Syntax auf:</span><span class="sxs-lookup"><span data-stu-id="fae5b-117">The OutputType attribute of functions has the following syntax:</span></span>

```
[OutputType([<TypeLiteral>], ParameterSetName="<Name>")]
[OutputType("<TypeNameString>", ParameterSetName="<Name>")]
```

<span data-ttu-id="fae5b-118">Der **parametersetname** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="fae5b-118">The **ParameterSetName** parameter is optional.</span></span>

<span data-ttu-id="fae5b-119">Sie können mehrere Typen im OutputType-Attribut auflisten.</span><span class="sxs-lookup"><span data-stu-id="fae5b-119">You can list multiple types in the OutputType attribute.</span></span>

```
[OutputType([<Type1>],[<Type2>],[<Type3>])]
```

<span data-ttu-id="fae5b-120">Mithilfe des Parameters **parametersetname** können Sie angeben, dass unterschiedliche Parametersätze verschiedene Typen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="fae5b-120">You can use the **ParameterSetName** parameter to indicate that different parameter sets return different types.</span></span>

```
[OutputType([<Type1>], ParameterSetName=("<Set1>","<Set2>"))]
[OutputType([<Type2>], ParameterSetName="<Set3>")]
```

<span data-ttu-id="fae5b-121">Platzieren Sie die OutputType-Attribut Anweisungen in der Attribut Liste, die der-Anweisung vorangestellt ist `Param` .</span><span class="sxs-lookup"><span data-stu-id="fae5b-121">Place the OutputType attribute statements in the attributes list that precedes the `Param` statement.</span></span>

<span data-ttu-id="fae5b-122">Im folgenden Beispiel wird die Platzierung des OutputType-Attributs in einer einfachen Funktion veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="fae5b-122">The following example shows the placement of the OutputType attribute in a simple function.</span></span>

```powershell
function SimpleFunction2
{
  [OutputType([<Type>])]
  Param ($Parameter1)

  <function body>
}
```

<span data-ttu-id="fae5b-123">Das folgende Beispiel zeigt die Platzierung des OutputType-Attributs in Advanced functions.</span><span class="sxs-lookup"><span data-stu-id="fae5b-123">The following example shows the placement of the OutputType attribute in advanced functions.</span></span>

```powershell
function AdvancedFunction1
{
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}

function AdvancedFunction2
{
  [CmdletBinding(SupportsShouldProcess=<Boolean>)]
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}
```

## <a name="examples"></a><span data-ttu-id="fae5b-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fae5b-124">EXAMPLES</span></span>

### <a name="example-1-create-a-function-that-has-the-outputtype-of-string"></a><span data-ttu-id="fae5b-125">Beispiel 1: Erstellen einer Funktion, die den OutputType der Zeichenfolge aufweist</span><span class="sxs-lookup"><span data-stu-id="fae5b-125">Example 1: Create a function that has the OutputType of String</span></span>

```powershell
function Send-Greeting
{
  [OutputType([String])]
  Param ($Name)

  "Hello, $Name"
}
```

<span data-ttu-id="fae5b-126">Verwenden Sie das-Cmdlet, um die resultierende Ausgabetyp Eigenschaft anzuzeigen `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="fae5b-126">To see the resulting output type property, use the `Get-Command` cmdlet.</span></span>

```powershell
(Get-Command Send-Greeting).OutputType
```

```Output
Name                                               Type
----                                               ----
System.String                                      System.String
```

### <a name="example-2-use-the-output-attribute-to-indicate-dynamic-output-types"></a><span data-ttu-id="fae5b-127">Beispiel 2: Verwenden des Output-Attributs, um dynamische Ausgabetypen anzugeben</span><span class="sxs-lookup"><span data-stu-id="fae5b-127">Example 2: Use the Output attribute to indicate dynamic output types</span></span>

<span data-ttu-id="fae5b-128">Die folgende erweiterte Funktion verwendet das OutputType-Attribut, um anzugeben, dass die Funktion abhängig von dem im Funktionsbefehl verwendeten Parametersatz verschiedene Typen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fae5b-128">The following advanced function uses the OutputType attribute to indicate that the function returns different types depending on the parameter set used in the function command.</span></span>

```powershell
function Get-User
{
  [CmdletBinding(DefaultParameterSetName="ID")]

  [OutputType("System.Int32", ParameterSetName="ID")]
  [OutputType([String], ParameterSetName="Name")]

  Param (
    [parameter(Mandatory=$true, ParameterSetName="ID")]
    [Int[]]
    $UserID,

    [parameter(Mandatory=$true, ParameterSetName="Name")]
    [String[]]
    $UserName
  )

  <function body>
}
```

### <a name="example-3-shows-when-an-actual-output-differs-from-the-outputtype"></a><span data-ttu-id="fae5b-129">Beispiel 3: zeigt an, wenn eine tatsächliche Ausgabe vom OutputType abweicht.</span><span class="sxs-lookup"><span data-stu-id="fae5b-129">Example 3: Shows when an actual output differs from the OutputType</span></span>

<span data-ttu-id="fae5b-130">Im folgenden Beispiel wird veranschaulicht, dass der Wert des Output Type-Eigenschafts Werts den Wert des OutputType-Attributs anzeigt, auch wenn er ungenau ist.</span><span class="sxs-lookup"><span data-stu-id="fae5b-130">The following example demonstrates that the output type property value displays the value of the OutputType attribute, even when it is inaccurate.</span></span>

<span data-ttu-id="fae5b-131">Die- `Get-Time` Funktion gibt eine Zeichenfolge zurück, die die Kurzform der Uhrzeit in einem beliebigen DateTime-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="fae5b-131">The `Get-Time` function returns a string that contains the short form of the time in any DateTime object.</span></span> <span data-ttu-id="fae5b-132">Das OutputType-Attribut meldet jedoch, dass ein **System. DateTime** -Objekt zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fae5b-132">However, the OutputType attribute reports that it returns a **System.DateTime** object.</span></span>

```powershell
function Get-Time
{
  [OutputType([DateTime])]
  Param (
    [parameter(Mandatory=$true)]
    [Datetime]$DateTime
  )

  $DateTime.ToShortTimeString()
}
```

<span data-ttu-id="fae5b-133">Die- `GetType()` Methode bestätigt, dass die-Funktion eine Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fae5b-133">The `GetType()` method confirms that the function returns a string.</span></span>

```powershell
(Get-Time -DateTime (Get-Date)).GetType().FullName
```

```Output
System.String
```

<span data-ttu-id="fae5b-134">Die OutputType-Eigenschaft, die ihren Wert aus dem OutputType-Attribut abruft, meldet jedoch, dass die Funktion ein **DateTime** -Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fae5b-134">However, the OutputType property, which gets its value from the OutputType attribute, reports that the function returns a **DateTime** object.</span></span>

```powershell
(Get-Command Get-Time).OutputType
```

```Output
Name                                      Type
----                                      ----
System.DateTime                           System.DateTime
```

### <a name="example-4-a-function--that-shouldnt-have-output"></a><span data-ttu-id="fae5b-135">Beispiel 4: eine Funktion, die keine Ausgabe haben sollte</span><span class="sxs-lookup"><span data-stu-id="fae5b-135">Example 4: A function  that shouldn't have output</span></span>

<span data-ttu-id="fae5b-136">Das folgende Beispiel zeigt eine benutzerdefinierte Funktion, die eine Aktion ausführen und diese ausführen, aber nichts zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="fae5b-136">The following example shows a custom function that should perform and action but not return anything.</span></span>

```powershell
function Invoke-Notepad
{
  [OutputType([System.Void])]
  Param ()
  & notepad.exe | Out-Null
}
```

## <a name="notes"></a><span data-ttu-id="fae5b-137">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fae5b-137">NOTES</span></span>

<span data-ttu-id="fae5b-138">Der Wert der OutputType-Eigenschaft eines **functioninfo** -Objekts ist ein Array von **System. Management. Automation. pstypename** -Objekten, die jeweils über die Eigenschaften "Name" und "Type" verfügen.</span><span class="sxs-lookup"><span data-stu-id="fae5b-138">The value of the OutputType property of a **FunctionInfo** object is an array of **System.Management.Automation.PSTypeName** objects, each of which have Name and Type properties.</span></span>

<span data-ttu-id="fae5b-139">Um nur den Namen der einzelnen Ausgabetypen zu erhalten, verwenden Sie einen Befehl mit dem folgenden Format.</span><span class="sxs-lookup"><span data-stu-id="fae5b-139">To get only the name of each output type, use a command with the following format.</span></span>

```powershell
(Get-Command Get-Time).OutputType | ForEach {$_.Name}
```

<span data-ttu-id="fae5b-140">Der Wert der OutputType-Eigenschaft kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="fae5b-140">The value of the OutputType property can be null.</span></span> <span data-ttu-id="fae5b-141">Verwenden Sie einen NULL-Wert, wenn es sich bei der Ausgabe nicht um einen .NET-Typ handelt, z. b. ein **WMI** -Objekt oder eine formatierte Ansicht eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="fae5b-141">Use a null value when the output is a not a .NET type, such as a **WMI** object or a formatted view of an object.</span></span>

## <a name="see-also"></a><span data-ttu-id="fae5b-142">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="fae5b-142">SEE ALSO</span></span>

[<span data-ttu-id="fae5b-143">about_Functions</span><span class="sxs-lookup"><span data-stu-id="fae5b-143">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="fae5b-144">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="fae5b-144">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="fae5b-145">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="fae5b-145">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="fae5b-146">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="fae5b-146">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="fae5b-147">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="fae5b-147">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

