---
description: Beschreibt die Syntax Diagramme, die in PowerShell verwendet werden.
Locale: en-US
ms.date: 06/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Syntax
ms.openlocfilehash: 05677d5633c56efd4b7c44c16f9c4e34a222e8b0
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195192"
---
# <a name="about-command-syntax"></a>Informationen zur Befehls Syntax

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt die Syntax Diagramme, die in PowerShell verwendet werden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Die Cmdlets " [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) " und " [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) " zeigen Syntax Diagramme an, die Ihnen helfen, Befehle korrekt zu erstellen. In diesem Thema wird erläutert, wie die Syntax Diagramme interpretiert werden.

## <a name="syntax-diagrams"></a>Syntax Diagramme

Jeder Absatz eines Befehlssyntax Diagramms stellt ein gültiges Formular des Befehls dar.

Um einen Befehl zu erstellen, befolgen Sie das Syntax Diagramm von links nach rechts. Wählen Sie unter den optionalen Parametern aus, und geben Sie Werte für die Platzhalter an.

PowerShell verwendet die folgende Notation für Syntax Diagramme.

```powershell
<command-name> -<Required Parameter Name> <Required Parameter Value>
[-<Optional Parameter Name> <Optional Parameter Value>]
[-<Optional Switch Parameters>]
[-<Optional Parameter Name>] <Required Parameter Value>
```

Im folgenden finden Sie die Syntax für das Cmdlet [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) .

```powershell
New-Alias [-Name] <string> [-Value] <string> [-Description <string>]
[-Force] [-Option {None | ReadOnly | Constant | Private | AllScope}]
[-PassThru] [-Scope <string>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

Die Syntax wird zur besseren Lesbarkeit groß geschrieben, aber bei PowerShell wird die Groß-/Kleinschreibung nicht beachtet.

Das Syntax Diagramm enthält die folgenden Elemente:

## <a name="command-name"></a>Befehlsname

Befehle beginnen immer mit einem Befehlsnamen, z `New-Alias` . b.. Geben Sie den Befehlsnamen oder seinen Alias ein, z. b. "GCM" für `Get-Command` .

## <a name="parameters"></a>Parameter

Die Parameter eines Befehls sind Optionen, mit denen bestimmt wird, was der Befehl bewirkt.
Einige Parameter akzeptieren einen "Wert", bei dem es sich um eine Benutzereingabe für den Befehl handelt.

Der- `Get-Help` Befehl verfügt z. b. über einen **Name** -Parameter, mit dem Sie den Namen des Themas angeben können, für das die Hilfe angezeigt wird. Der Themenname ist der Wert des **Name** -Parameters.

In einem PowerShell-Befehl beginnen Parameternamen immer mit einem Bindestrich.
Der Bindestrich weist PowerShell an, dass das Element im Befehl ein Parameter Name ist.

Wenn Sie z. b. den Name-Parameter von verwenden möchten `New-Alias` , geben Sie Folgendes ein:

```powershell
-Name
```

Parameter können obligatorisch oder optional sein. In einem Syntax Diagramm werden optionale Elemente in eckige Klammern eingeschlossen `[ ]` .

Weitere Informationen zu Parametern finden Sie unter [about_Parameters](about_Parameters.md).

## <a name="parameter-values"></a>Parameterwerte

Ein Parameterwert ist die Eingabe, die der-Parameter annimmt. Da Windows PowerShell auf dem Microsoft .NET Framework basiert, werden Parameterwerte im Syntax Diagramm durch ihren .NET-Typ dargestellt.

Beispielsweise übernimmt der Name-Parameter von den `Get-Help` Wert "String", bei dem es sich um eine Text Zeichenfolge handelt, z. b. ein einzelnes Wort oder mehrere Wörter, die in Anführungszeichen eingeschlossen sind.

```powershell
[-Name] <string>
```

Der .NET-Typ eines Parameter Werts wird in spitzen Klammern eingeschlossen `< >` , um anzugeben, dass es sich um einen Platzhalter für einen Wert handelt, nicht um ein Literalzeichen, das Sie in einen Befehl eingeben.

Um den-Parameter zu verwenden, ersetzen Sie den .net-Typplatzhalter durch ein-Objekt, das über den angegebenen .NET-Typ verfügt.

Wenn Sie z. b. den **Name** -Parameter verwenden möchten, geben Sie "-Name" gefolgt von einer Zeichenfolge ein, z. b. Folgendes:

```powershell
-Name MyAlias
```

## <a name="parameters-with-no-values"></a>Parameter ohne Werte

Einige Parameter akzeptieren keine Eingaben, sodass Sie nicht über einen Parameterwert verfügen.
Parameter ohne Werte werden als "Switch-Parameter" bezeichnet, da Sie wie on/off-Switches funktionieren. Sie fügen Sie ein (on), oder Sie können Sie (aus) über einen Befehl weglassen.

Um einen Switch-Parameter zu verwenden, geben Sie einfach den Parameternamen ein, dem ein Bindestrich vorangestellt ist.

Wenn Sie z. b. den **WhatIf** -Parameter des `New-Alias` Cmdlets verwenden möchten, geben Sie Folgendes ein:

```powershell
-WhatIf
```

## <a name="parameter-sets"></a>Parameter Sätze

Die Parameter eines Befehls werden in Parametersätzen aufgeführt. Parameter Sätze sehen wie die Absätze eines Syntax Diagramms aus.

Für das `New-Alias` Cmdlet ist ein Parametersatz festgelegt, aber viele Cmdlets verfügen über mehrere Parametersätze. Einige der Cmdlet-Parameter sind für einen Parametersatz eindeutig, und andere sind in mehreren Parametersätzen enthalten. Jeder Parametersatz stellt das Format eines gültigen Befehls dar. Ein Parametersatz enthält nur Parameter, die in einem Befehl verwendet werden können. Wenn Parameter nicht im selben Befehl verwendet werden können, werden Sie in separaten Parametersätzen angezeigt.

Beispielsweise verfügt das [Get-Random-](xref:Microsoft.PowerShell.Utility.Get-Random) Cmdlet über die folgenden Parametersätze:

```powershell
Get-Random [[-Maximum] <Object>] [-Minimum <Object>] [-SetSeed <int>]
[<CommonParameters>]

Get-Random [-InputObject] <Object[]> [-Count <int>] [-SetSeed <int>]
[<CommonParameters>]
```

Der erste Parametersatz, der eine Zufallszahl zurückgibt, hat den **minimalen** und den **maximalen** Parameter. Der zweite Parametersatz, der ein zufällig ausgewähltes Objekt aus einem Satz von Objekten zurückgibt, enthält die Parameter **Inputobject** und **count** . Beide Parametersätze verfügen über den **setseed** -Parameter und die allgemeinen Parameter.

Diese Parametersätze geben an, dass Sie die **Inputobject** -und **count** -Parameter im gleichen Befehl verwenden können, aber Sie können die Parameter " **Maximum** " und " **count** " nicht im selben Befehl verwenden.

Sie geben den Parametersatz an, den Sie verwenden möchten, indem Sie die Parameter in diesem Parametersatz verwenden.

Allerdings verfügt jedes Cmdlet auch über einen Standardparameter Satz. Der Standardparameter Satz wird verwendet, wenn Sie keine Parameter angeben, die für einen Parametersatz eindeutig sind. Wenn Sie z. b. `Get-Random` ohne Parameter verwenden, geht Windows PowerShell davon aus, dass Sie den **Number** -Parametersatz verwenden und eine Zufallszahl zurückgibt.

In jedem Parametersatz werden die Parameter in der Positions Reihenfolge angezeigt. Die Reihenfolge von Parametern in einem Befehl ist nur wichtig, wenn Sie die optionalen Parameternamen weglassen. Wenn Parameternamen ausgelassen werden, werden den Parametern von PowerShell Werte nach Position und Typ zugewiesen. Weitere Informationen zur Parameter Position finden Sie unter `about_Parameters` .

## <a name="symbols-in-syntax-diagrams"></a>Symbole in Syntax Diagrammen

Das Syntax Diagramm listet den Befehlsnamen, die Befehlsparameter und die Parameterwerte auf. Außerdem werden Symbole verwendet, um anzuzeigen, wie ein gültiger Befehl erstellt wird.

In den Syntax Diagrammen werden die folgenden Symbole verwendet:

- Ein Bindestrich `-` gibt einen Parameternamen an. Geben Sie in einem Befehl den Bindestrich direkt vor dem Parameternamen ohne dazwischenliegende Leerzeichen ein, wie im Syntax Diagramm dargestellt.

  Wenn Sie beispielsweise den **Name** -Parameter von verwenden möchten, geben Sie Folgendes ein `New-Alias` :

  ```powershell
  -Name
  ```

- Spitze Klammern `<>` geben Platzhalter Text an. Sie dürfen nicht die spitzen Klammern oder den Platzhalter Text in einem Befehl eingeben. Stattdessen wird Sie durch das Element ersetzt, das beschrieben wird.

  Mithilfe von spitzen Klammern wird der .NET-Typ des Werts identifiziert, der von einem Parameter verwendet wird. Wenn Sie z. b. den **Name** -Parameter des `New-Alias` Cmdlets verwenden möchten, ersetzen Sie den `<string>` durch eine Zeichenfolge, bei der es sich um ein einzelnes Wort oder eine Gruppe von Wörtern handelt, die in Anführungszeichen eingeschlossen sind.

- Eckige Klammern `[ ]` zeigen optionale Elemente an. Ein Parameter und sein Wert können optional sein, oder der Name eines erforderlichen Parameters kann optional sein.

  Beispielsweise werden der **Description** -Parameter von `New-Alias` und sein Wert in eckige Klammern eingeschlossen, da Sie beide optional sind.

  ```powershell
  [-Description <string>]
  ```

  Die Klammern geben auch an, dass der Name-Parameterwert `<string>` erforderlich ist, aber der Parameter Name "Name" ist optional.

  ```powershell
  [-Name] <string>
  ```

- Eine `[]` an einen .NET-Typ angefügte Rechte und linke eckige Klammer gibt an, dass der Parameter einen oder mehrere Werte dieses Typs annehmen kann. Geben Sie die Werte in eine durch Kommas getrennte Liste ein.

  Der **Name** -Parameter des `New-Alias` Cmdlets nimmt z. b. nur eine Zeichenfolge an, aber der **Name** -Parameter von [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) kann eine oder mehrere Zeichen folgen annehmen.

  ```powershell
  New-Alias [-Name] <string>

  New-Alias -Name MyAlias
  ```

  ```powershell
  Get-Process [-Name] <string[]>

  Get-Process -Name Explorer, Winlogon, Services
  ```

- Geschweifte Klammern `{}` geben eine "Enumeration" an, bei der es sich um einen Satz gültiger Werte für einen Parameter handelt.

  Die Werte in geschweiften Klammern werden durch vertikale Balken voneinander getrennt `|` . Diese Balken weisen auf eine "exklusive oder"-Auswahl hin. Dies bedeutet, dass Sie nur einen Wert aus dem Satz von Werten auswählen können, die in den geschweiften Klammern aufgeführt sind.

  Die Syntax für das `New-Alias` Cmdlet enthält z. b. die folgende Wertenumeration für den Parameter **Option** :

  ```powershell
  -Option {None | ReadOnly | Constant | Private | AllScope}
  ```

  Die geschweiften Klammern und senkrechten Balken zeigen an, dass Sie einen der aufgelisteten Werte für den **options** Parameter, z. b. "schreibgeschützt" oder "allscope", auswählen können.

  ```powershell
  -Option ReadOnly
  ```

## <a name="optional-items"></a>Optionale Elemente

Eckige Klammern `[]` umschließen optionale Elemente. Beispielsweise `New-Alias` ist der **Scope** -Parameter in der Beschreibung der Cmdlet-Syntax optional. Dies wird in der Syntax durch die Klammern um den Parameternamen und den Typ angegeben:

```powershell
[-Scope <string>]
```

Beide folgenden Beispiele sind die richtige Verwendung des `New-Alias` Cmdlets:

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd -Value Update-TypeData -Scope Global
```

Ein Parameter Name kann optional sein, auch wenn der Wert für diesen Parameter erforderlich ist. Dies wird in der Syntax durch die Klammern um den Parameternamen, aber nicht durch den Parametertyp angegeben, wie in diesem Beispiel aus dem `New-Alias` Cmdlet:

```powershell
[-Name] <string> [-Value] <string>
```

Die folgenden Befehle verwenden das `New-Alias` Cmdlet ordnungsgemäß. Die Befehle führen zu demselben Ergebnis.

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd Update-TypeData
New-Alias utd -Value Update-TypeData
New-Alias utd Update-TypeData
```

Wenn der Parameter Name nicht in der Anweisung als typisiert enthalten ist, versucht Windows PowerShell, die Position der Argumente zu verwenden, um die Werte den Parametern zuzuweisen.

Das folgende Beispiel ist nicht fertiggestellt:

```powershell
New-Alias utd
```

Dieses Cmdlet erfordert Werte für den **Name** -Parameter und den **value** -Parameter.

In Syntax Beispielen werden auch eckige Klammern zum Benennen und umwandeln in .NET Framework Typen verwendet. In diesem Kontext geben eckige Klammern nicht an, dass ein Element optional ist.

## <a name="see-also"></a>SIEHE AUCH

- [about_Parameters](about_Parameters.md)
- [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)
- [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

