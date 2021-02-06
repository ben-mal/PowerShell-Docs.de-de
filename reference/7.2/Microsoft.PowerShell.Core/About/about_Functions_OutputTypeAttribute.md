---
description: Beschreibt ein Attribut, das den Typ des Objekts angibt, welches die Funktion zurückgibt.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_OutputTypeAttribute
ms.openlocfilehash: 82f1615c4a2fe2a24f104d8e5637103dea6e5a0a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600903"
---
# <a name="about-functions-outputtypeattribute"></a>Informationen zu Funktionen outputtypeer Attribute

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt ein Attribut, das den Typ des Objekts angibt, welches die Funktion zurückgibt.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Das OutputType-Attribut listet die .NET-Objekttypen auf, die von den Funktionen zurückgegeben werden. Sie können den optionalen parametersetname-Parameter verwenden, um unterschiedliche Ausgabetypen für jeden Parametersatz aufzulisten.

Das OutputType-Attribut wird für einfache und erweiterte Funktionen unterstützt. Es ist unabhängig vom cmdletbinding-Attribut.

Das OutputType-Attribut stellt den Wert der OutputType-Eigenschaft des **System. Management. Automation. functioninfo** -Objekts bereit, das vom `Get-Command` Cmdlet zurückgegeben wird.

Der Wert des Attributs OutputType ist nur ein Dokumentationshinweis. Sie wird nicht vom Funktionscode abgeleitet oder mit der tatsächlichen funktionsausgabe verglichen. Daher ist der Wert möglicherweise ungenau.

## <a name="syntax"></a>SYNTAX

Das OutputType-Attribut von Functions weist die folgende Syntax auf:

```
[OutputType([<TypeLiteral>], ParameterSetName="<Name>")]
[OutputType("<TypeNameString>", ParameterSetName="<Name>")]
```

Der **parametersetname** -Parameter ist optional.

Sie können mehrere Typen im OutputType-Attribut auflisten.

```
[OutputType([<Type1>],[<Type2>],[<Type3>])]
```

Mithilfe des Parameters **parametersetname** können Sie angeben, dass unterschiedliche Parametersätze verschiedene Typen zurückgeben.

```
[OutputType([<Type1>], ParameterSetName=("<Set1>","<Set2>"))]
[OutputType([<Type2>], ParameterSetName="<Set3>")]
```

Platzieren Sie die OutputType-Attribut Anweisungen in der Attribut Liste, die der-Anweisung vorangestellt ist `Param` .

Im folgenden Beispiel wird die Platzierung des OutputType-Attributs in einer einfachen Funktion veranschaulicht.

```powershell
function SimpleFunction2
{
  [OutputType([<Type>])]
  Param ($Parameter1)

  <function body>
}
```

Das folgende Beispiel zeigt die Platzierung des OutputType-Attributs in Advanced functions.

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

## <a name="examples"></a>BEISPIELE

### <a name="example-1-create-a-function-that-has-the-outputtype-of-string"></a>Beispiel 1: Erstellen einer Funktion, die den OutputType der Zeichenfolge aufweist

```powershell
function Send-Greeting
{
  [OutputType([String])]
  Param ($Name)

  "Hello, $Name"
}
```

Verwenden Sie das-Cmdlet, um die resultierende Ausgabetyp Eigenschaft anzuzeigen `Get-Command` .

```powershell
(Get-Command Send-Greeting).OutputType
```

```Output
Name                                               Type
----                                               ----
System.String                                      System.String
```

### <a name="example-2-use-the-output-attribute-to-indicate-dynamic-output-types"></a>Beispiel 2: Verwenden des Output-Attributs, um dynamische Ausgabetypen anzugeben

Die folgende erweiterte Funktion verwendet das OutputType-Attribut, um anzugeben, dass die Funktion abhängig von dem im Funktionsbefehl verwendeten Parametersatz verschiedene Typen zurückgibt.

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

### <a name="example-3-shows-when-an-actual-output-differs-from-the-outputtype"></a>Beispiel 3: zeigt an, wenn eine tatsächliche Ausgabe vom OutputType abweicht.

Im folgenden Beispiel wird veranschaulicht, dass der Wert des Output Type-Eigenschafts Werts den Wert des OutputType-Attributs anzeigt, auch wenn er ungenau ist.

Die- `Get-Time` Funktion gibt eine Zeichenfolge zurück, die die Kurzform der Uhrzeit in einem beliebigen DateTime-Objekt enthält. Das OutputType-Attribut meldet jedoch, dass ein **System. DateTime** -Objekt zurückgegeben wird.

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

Die- `GetType()` Methode bestätigt, dass die-Funktion eine Zeichenfolge zurückgibt.

```powershell
(Get-Time -DateTime (Get-Date)).GetType().FullName
```

```Output
System.String
```

Die OutputType-Eigenschaft, die ihren Wert aus dem OutputType-Attribut abruft, meldet jedoch, dass die Funktion ein **DateTime** -Objekt zurückgibt.

```powershell
(Get-Command Get-Time).OutputType
```

```Output
Name                                      Type
----                                      ----
System.DateTime                           System.DateTime
```

### <a name="example-4-a-function--that-shouldnt-have-output"></a>Beispiel 4: eine Funktion, die keine Ausgabe haben sollte

Das folgende Beispiel zeigt eine benutzerdefinierte Funktion, die eine Aktion ausführen und diese ausführen, aber nichts zurückgeben soll.

```powershell
function Invoke-Notepad
{
  [OutputType([System.Void])]
  Param ()
  & notepad.exe | Out-Null
}
```

## <a name="notes"></a>HINWEISE

Der Wert der OutputType-Eigenschaft eines **functioninfo** -Objekts ist ein Array von **System. Management. Automation. pstypename** -Objekten, die jeweils über die Eigenschaften "Name" und "Type" verfügen.

Um nur den Namen der einzelnen Ausgabetypen zu erhalten, verwenden Sie einen Befehl mit dem folgenden Format.

```powershell
(Get-Command Get-Time).OutputType | ForEach {$_.Name}
```

Der Wert der OutputType-Eigenschaft kann NULL sein. Verwenden Sie einen NULL-Wert, wenn es sich bei der Ausgabe nicht um einen .NET-Typ handelt, z. b. ein **WMI** -Objekt oder eine formatierte Ansicht eines Objekts.

## <a name="see-also"></a>SIEHE AUCH

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

