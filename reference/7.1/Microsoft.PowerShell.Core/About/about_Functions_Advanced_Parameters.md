---
description: Erläutert das Hinzufügen von Parametern zu erweiterten Funktionen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Parameters
ms.openlocfilehash: 2a5b13475dd648a9f778d23b4089da00351b237c
ms.sourcegitcommit: 3b1779890f828130a9d73aebf17ebffae511728f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "93225247"
---
# <a name="about-functions-advanced-parameters"></a>Informationen zu erweiterten Functions-Parametern

## <a name="short-description"></a>Kurze Beschreibung

Erläutert das Hinzufügen von Parametern zu erweiterten Funktionen.

## <a name="long-description"></a>Lange Beschreibung

Sie können den erweiterten Funktionen, die Sie schreiben, Parameter hinzufügen und Parameter Attribute und-Argumente verwenden, um die Parameterwerte einzuschränken, die Benutzer mit dem-Parameter übermitteln.

Die Parameter, die Sie ihrer Funktion hinzufügen, stehen Benutzern zusätzlich zu den allgemeinen Parametern zur Verfügung, die von PowerShell automatisch zu allen Cmdlets und erweiterten Funktionen hinzugefügt werden. Weitere Informationen zu den allgemeinen PowerShell-Parametern finden Sie unter [about_CommonParameters](about_CommonParameters.md).

Ab PowerShell 3,0 können Sie Verteilung mit verwenden, `@Args` um die Parameter in einem Befehl darzustellen. Splatting ist in einfachen und erweiterten Funktionen gültig. Weitere Informationen finden Sie unter [about_Functions](about_Functions.md) und [about_Splatting](about_Splatting.md).

## <a name="type-conversion-of-parameter-values"></a>Typkonvertierung von Parameterwerten

Wenn Sie Zeichen folgen als Argumente für Parameter angeben, die einen anderen Typ erwarten, konvertiert PowerShell die Zeichen folgen implizit in den Zieltyp des Parameters.
Erweiterte Funktionen führen eine Kultur invariante Verarbeitung von Parameterwerten aus.

Im Gegensatz dazu wird bei der Parameter Bindung für kompilierte Cmdlets eine Kultur abhängige Konvertierung durchgeführt.

In diesem Beispiel erstellen wir ein Cmdlet und eine Skriptfunktion, die einen `[datetime]` Parameter annehmen. Die aktuelle Kultur wird so geändert, dass Sie die deutschen Einstellungen verwendet.
Ein deutsch formatiertes Datum wird an den-Parameter übergeben.

```powershell
# Create a cmdlet that accepts a [datetime] argument.
Add-Type @'
  using System;
  using System.Management.Automation;
  [Cmdlet("Get", "Date_Cmdlet")]
  public class GetFooCmdlet : Cmdlet {

    [Parameter(Position=0)]
    public DateTime Date { get; set; }

    protected override void ProcessRecord() {
      WriteObject(Date);
    }
  }
'@ -PassThru | % Assembly | Import-Module

[cultureinfo]::CurrentCulture = 'de-DE'
$dateStr = '19-06-2018'

Get-Date_Cmdlet $dateStr
```

```Output
Dienstag, 19. Juni 2018 00:00:00
```

Wie oben gezeigt, verwenden Cmdlets die Kultur abhängige Verarbeitung, um die Zeichenfolge zu konvertieren.

```powershell
# Define an equivalent function.
function Get-Date_Func {
  param(
    [DateTime] $Date
  )
  process {
    $Date
  }
}

[cultureinfo]::CurrentCulture = 'de-DE'

# This German-format date string doesn't work with the invariant culture.
# E.g., [datetime] '19-06-2018' breaks.
$dateStr = '19-06-2018'

Get-Date_Func $dateStr
```

Erweiterte Funktionen verwenden eine Kultur invariante Verarbeitung, die zu folgendem Fehler führt.

```Output
Get-Date_Func: Cannot process argument transformation on parameter 'Date'.
Cannot convert value "19-06-2018" to type "System.DateTime". Error: "String
'19-06-2018' was not recognized as a valid DateTime."
```

## <a name="static-parameters"></a>Statische Parameter

Statische Parameter sind Parameter, die in der Funktion immer verfügbar sind.
Die meisten Parameter in PowerShell-Cmdlets und-Skripts sind statische Parameter.

Das folgende Beispiel zeigt die Deklaration eines **Computername** -Parameters, der die folgenden Eigenschaften aufweist:

- Dies ist obligatorisch (erforderlich).
- Er nimmt Eingaben aus der Pipeline an.
- Es wird ein Array von Zeichen folgen als Eingabe benötigt.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

## <a name="attributes-of-parameters"></a>Attribute von Parametern

In diesem Abschnitt werden die Attribute beschrieben, die Sie Funktionsparametern hinzufügen können.

Alle Attribute sind optional. Wenn Sie jedoch das **cmdletbinding** -Attribut weglassen und als erweiterte Funktion erkannt werden, muss die Funktion das **Parameter** Attribut enthalten.

Sie können in jeder Parameter Deklaration ein oder mehrere Attribute hinzufügen. Es gibt keine Beschränkung für die Anzahl der Attribute, die Sie einer Parameter Deklaration hinzufügen können.

### <a name="parameter-attribute"></a>Parameterattribut

Das **Parameter** -Attribut wird verwendet, um die Attribute von Funktionsparametern zu deklarieren.

Das **Parameter** Attribut ist optional, und Sie können es weglassen, wenn keiner der Parameter ihrer Funktionen Attribute benötigt. Um jedoch als erweiterte Funktion und nicht als einfache Funktion erkannt zu werden, muss eine Funktion entweder das **cmdletbinding** -Attribut oder das **Parameter** -Attribut oder beides aufweisen.

Das **Parameter** Attribut verfügt über Argumente, die die Merkmale des Parameters definieren, z. b. ob der Parameter obligatorisch oder optional ist.

Verwenden Sie die folgende Syntax, um das **Parameter** Attribut, ein Argument und einen Argument Wert zu deklarieren. Die Klammern, die das Argument und seinen Wert einschließen, müssen **Parameter** ohne dazwischenliegende Leerzeichen folgen.

```powershell
Param(
    [Parameter(Argument=value)]
    $ParameterName
)
```

Verwenden Sie Kommas zum Trennen von Argumenten innerhalb der Klammern. Verwenden Sie die folgende Syntax, um zwei Argumente des **Parameter** -Attributs zu deklarieren.

```powershell
Param(
    [Parameter(Argument1=value1,
    Argument2=value2)]
)
```

Die booleschen Argument Typen des **Parameter** Attributs werden standardmäßig auf **false** zurückzuführen, wenn Sie im **Parameter** -Attribut ausgelassen werden. Legen Sie den Argument Wert auf fest, `$true` oder Listen Sie einfach das Argument nach Namen auf. Die folgenden **Parameter** Attribute sind z. b. äquivalent.

```powershell
Param(
    [Parameter(Mandatory=$true)]
)

# Boolean arguments can be defined using this shorthand syntax

Param(
    [Parameter(Mandatory)]
)
```

Wenn Sie das **Parameter** Attribut ohne Argumente als Alternative zur Verwendung des **cmdletbinding** -Attributs verwenden, sind die Klammern, die dem Attributnamen folgen, weiterhin erforderlich.

```powershell
Param(
    [Parameter()]
    $ParameterName
)
```

#### <a name="mandatory-argument"></a>Obligatorisches Argument

Das- `Mandatory` Argument gibt an, dass der-Parameter erforderlich ist. Wenn dieses Argument nicht angegeben wird, ist der Parameter optional.

Im folgenden Beispiel wird der **Computername** -Parameter deklariert. Er verwendet das- `Mandatory` Argument, um den-Parameter obligatorisch zu machen.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="position-argument"></a>Positions Argument

Das- `Position` Argument bestimmt, ob der Parameter Name erforderlich ist, wenn der-Parameter in einem Befehl verwendet wird. Wenn eine Parameter Deklaration das- `Position` Argument enthält, kann der Parameter Name ausgelassen werden, und PowerShell identifiziert den unbenannten Parameterwert anhand seiner Position oder Reihenfolge in der Liste unbenannter Parameterwerte im Befehl.

Wenn das- `Position` Argument nicht angegeben wird, muss der Parameter Name oder ein Parameter namens Alias oder eine Abkürzung dem Parameterwert vorangestellt werden, wenn der-Parameter in einem-Befehl verwendet wird.

Standardmäßig sind alle Funktionsparameter positiontional. PowerShell weist den Parametern in der Reihenfolge, in der die Parameter in der Funktion deklariert werden, Positionsnummern zu. Um diese Funktion zu deaktivieren, legen Sie den Wert des- `PositionalBinding` Arguments des **cmdletbinding** -Attributs auf fest `$False` . Das- `Position` Argument hat Vorrang vor dem Wert des- `PositionalBinding` Arguments des **cmdletbinding** -Attributs. Weitere Informationen finden Sie unter `PositionalBinding` in [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).

Der Wert des- `Position` Arguments wird als ganze Zahl angegeben. Ein Positionswert von **0** stellt die erste Position im Befehl dar, der Positionswert **1** stellt die zweite Position im Befehl dar usw.

Wenn eine Funktion keine Positions Parameter hat, weist PowerShell den einzelnen Parametern Positionen basierend auf der Reihenfolge zu, in der die Parameter deklariert werden.
Als bewährte Vorgehensweise sollten Sie sich jedoch nicht auf diese Zuweisung verlassen. Wenn Sie festlegen möchten, dass Parameter positionell sind, verwenden Sie das- `Position` Argument.

Im folgenden Beispiel wird der **Computername** -Parameter deklariert. Dabei wird das- `Position` Argument mit dem Wert **0** verwendet. Folglich muss, wenn `-ComputerName` im Befehl weggelassen wird, der Wert der erste oder einzige unbenannte Parameterwert im Befehl sein.

```powershell
Param(
    [Parameter(Position=0)]
    [String[]]
    $ComputerName
)
```

#### <a name="parametersetname-argument"></a>Parametersetname-Argument

Das- `ParameterSetName` Argument gibt den Parametersatz an, zu dem ein Parameter gehört. Wenn kein Parametersatz angegeben wird, gehört der Parameter zu allen von der Funktion definierten Parametersätzen. Daher muss jeder Parametersatz über mindestens einen Parameter verfügen, der kein Member eines anderen Parameter Satzes ist, damit er eindeutig ist.

> [!NOTE]
> Für ein Cmdlet oder eine Funktion gibt es ein Limit von 32-Parametersätzen.

Im folgenden Beispiel wird ein **Computername** -Parameter im `Computer` Parametersatz, ein **username** -Parameter im `User` Parametersatz und ein **Summary** -Parameter in beiden Parametersätzen deklariert.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false)]
    [Switch]
    $Summary
)
```

Sie können `ParameterSetName` in jedem Argument nur einen Wert und `ParameterSetName` in jedem **Parameter** Attribut nur ein Argument angeben. Fügen Sie zusätzliche **Parameter** Attribute hinzu, um anzugeben, dass ein Parameter in mehr als einem Parametersatz enthalten ist.

Im folgenden Beispiel wird der **Summary** -Parameter explizit dem `Computer` -Parameter und dem- `User` Parametersatz hinzugefügt. Der **Summary** -Parameter ist im `Computer` Parametersatz optional und im `User` Parametersatz obligatorisch.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ParameterSetName="Computer")]
    [String[]]
    $ComputerName,

    [Parameter(Mandatory=$true,
    ParameterSetName="User")]
    [String[]]
    $UserName,

    [Parameter(Mandatory=$false, ParameterSetName="Computer")]
    [Parameter(Mandatory=$true, ParameterSetName="User")]
    [Switch]
    $Summary
)
```

Weitere Informationen zu Parametersätzen finden Sie unter Informationen [zu Parametersätzen](about_parameter_sets.md).

#### <a name="valuefrompipeline-argument"></a>Valuefrompipeline-Argument

Das- `ValueFromPipeline` Argument gibt an, dass der-Parameter Eingaben von einem Pipeline Objekt akzeptiert. Geben Sie dieses Argument an, wenn die Funktion das gesamte Objekt akzeptiert, nicht nur eine Eigenschaft des Objekts.

Im folgenden Beispiel wird ein **Computername** -Parameter deklariert, der obligatorisch ist und ein-Objekt akzeptiert, das von der Pipeline an die Funktion übergeben wird.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="valuefrompipelinebypropertyname-argument"></a>Valuefrompipelinebypropertyname-Argument

Das- `ValueFromPipelineByPropertyName` Argument gibt an, dass der Parameter Eingaben aus einer Eigenschaft eines Pipeline Objekts akzeptiert. Die Object-Eigenschaft muss denselben Namen oder Alias wie der-Parameter aufweisen.

Wenn die Funktion z. b. über einen **Computername** -Parameter verfügt und das weitergeleitete Objekt über eine **Computername** -Eigenschaft verfügt, wird der Wert der **Computername** -Eigenschaft dem **Computername** -Parameter der Funktion zugewiesen.

Im folgenden Beispiel wird der erforderliche **Computername** -Parameter deklariert und Eingaben aus der **Computername** -Eigenschaft des Objekts akzeptiert, die über die Pipeline an die Funktion übergeben wird.

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipelineByPropertyName=$true)]
    [String[]]
    $ComputerName
)
```

> [!NOTE]
> Ein typisierter Parameter, der Pipeline Eingaben ( `by Value` ) oder () akzeptiert, `by PropertyName` ermöglicht die Verwendung von _verzögerten Bindungs_ Skript Blöcken für den Parameter.
>
> Der _Verzögerungs Bindungs_ Skriptblock wird automatisch während der **ParameterBinding** ausgeführt. Das Ergebnis wird an den-Parameter gebunden. Die verzögerte Bindung funktioniert nicht für Parameter, die als Typ oder definiert sind `ScriptBlock` `System.Object` . Der Skriptblock wird durchlaufen, _ohne_ aufgerufen zu werden.
>
> Informationen zu _verzögerten Bindungs_ Skript Blöcken finden Sie hier [about_Script_Blocks. MD](about_Script_Blocks.md).

#### <a name="valuefromremainingarguments-argument"></a>Valuefromremainingarguments-Argument

Das- `ValueFromRemainingArguments` Argument gibt an, dass der Parameter alle Werte des Parameters im Befehl akzeptiert, die anderen Parametern der Funktion nicht zugewiesen sind.

Im folgenden Beispiel wird ein **Wert** Parameter deklariert, der obligatorisch ist, und ein **verbleibender** Parameter, der alle verbleibenden Parameterwerte akzeptiert, die an die Funktion übermittelt werden.

```powershell
function Test-Remainder
{
     param(
         [string]
         [Parameter(Mandatory = $true, Position=0)]
         $Value,
         [string[]]
         [Parameter(Position=1, ValueFromRemainingArguments)]
         $Remaining)
     "Found $($Remaining.Count) elements"
     for ($i = 0; $i -lt $Remaining.Count; $i++)
     {
        "${i}: $($Remaining[$i])"
     }
}
Test-Remainder first one,two
```

```Output
Found 2 elements
0: one
1: two
```

> [!NOTE]
> Vor PowerShell 6,2 wurde die **valuefromrestingarguments** -Auflistung als einzelne Entität Unterindex **0** verknüpft.

#### <a name="helpmessage-argument"></a>Helpmessage-Argument

Das- `HelpMessage` Argument gibt eine Zeichenfolge an, die eine kurze Beschreibung des Parameters oder seines Werts enthält. PowerShell zeigt diese Meldung an der Eingabeaufforderung an, die angezeigt wird, wenn ein obligatorischer Parameterwert in einem Befehl fehlt. Dieses Argument hat keine Auswirkung auf optionale Parameter.

Das folgende Beispiel deklariert einen obligatorischen **Computername** -Parameter und eine Hilfe Meldung, in der der erwartete Parameterwert erläutert wird.

Wenn keine andere [Kommentar basierte Hilfe](./about_comment_based_help.md) Syntax für die Funktion vorliegt (z. b.), wird `.SYNOPSIS` Diese Meldung auch in der `Get-Help` Ausgabe angezeigt.

```powershell
Param(
    [Parameter(Mandatory=$true,
    HelpMessage="Enter one or more computer names separated by commas.")]
    [String[]]
    $ComputerName
)
```

### <a name="alias-attribute"></a>Alias-Attribut

Das **Alias** -Attribut richtet einen alternativen Namen für den Parameter ein.
Es gibt keine Beschränkung für die Anzahl der Aliase, die Sie einem Parameter zuweisen können.

Das folgende Beispiel zeigt eine Parameter Deklaration, die die Aliase " **CN** " und " **MachineName** " dem obligatorischen **Computername** -Parameter hinzufügt.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [Alias("CN","MachineName")]
    [String[]]
    $ComputerName
)
```

### <a name="supportswildcards-attribute"></a>Supportswildcards-Attribut

Das **supportswildcards** -Attribut wird verwendet, um anzugeben, dass der Parameter Platzhalter Werte annimmt. Das folgende Beispiel zeigt eine Parameter Deklaration für einen obligatorischen **path** -Parameter, der Platzhalter Werte unterstützt.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [SupportsWildcards()]
    [String[]]
    $Path
)
```

Durch die Verwendung dieses Attributs wird die Platzhalter Unterstützung nicht automatisch aktiviert. Der Cmdlet-Entwickler muss den Code implementieren, um die Platzhalter Eingabe zu verarbeiten. Welche Platzhalter unterstützt werden, hängt von der zugrunde liegenden API oder dem PowerShell-Anbieter ab. Weitere Informationen finden Sie unter [about_Wildcards](about_Wildcards.md).

### <a name="parameter-and-variable-validation-attributes"></a>Parameter-und Variablen Validierungs Attribute

Validierungs Attribute leiten PowerShell ein, um die Parameterwerte zu testen, die Benutzer beim Aufrufen der erweiterten Funktion senden. Wenn die Parameterwerte den Test nicht bestanden haben, wird ein Fehler generiert, und die Funktion wird nicht aufgerufen. Die Parameter Validierung wird nur auf die angegebene Eingabe angewendet, und alle anderen Werte wie Standardwerte werden nicht überprüft.

Sie können auch die Validierungs Attribute verwenden, um die Werte einzuschränken, die Benutzer für Variablen angeben können. Wenn Sie einen Typkonverter zusammen mit einem Validierungs Attribut verwenden, muss der Typkonverter vor dem-Attribut definiert werden.

```powershell
[int32][AllowNull()] $number = 7
```

### <a name="allownull-validation-attribute"></a>AllowNull-Validierungs Attribut

Das **AllowNull** -Attribut ermöglicht, dass der Wert eines obligatorischen Parameters ist `$null` . Im folgenden Beispiel wird ein Hash Table **ComputerInfo** -Parameter deklariert, der einen **null** -Wert aufweisen kann.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowNull()]
    [hashtable]
    $ComputerInfo
)
```

> [!NOTE]
> Das Attribut " **AllowNull** " funktioniert nicht, wenn der Typkonverter auf "String" festgelegt ist, da der Zeichen Folgentyp keinen NULL-Wert annimmt. Sie können das Attribut " **attribuwemptystring** " für dieses Szenario verwenden.

### <a name="allowemptystring-validation-attribute"></a>Attribut "zuder Zuordnung von zuder Zuweisung"

Das Attribut " **attribuwemptystring** " ermöglicht, dass der Wert eines obligatorischen Parameters eine leere Zeichenfolge ( `""` ) ist. Im folgenden Beispiel wird ein **Computername** -Parameter deklariert, der einen leeren Zeichen folgen Wert aufweisen kann.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyString()]
    [String]
    $ComputerName
)
```

### <a name="allowemptycollection-validation-attribute"></a>Zustellungs Attribut für Zustellungs Attribut

Das Attribut " **attribuwemptycollection** " ermöglicht, dass der Wert eines obligatorischen Parameters eine leere Auflistung ist `@()` . Im folgenden Beispiel wird ein **Computername** -Parameter deklariert, der einen leeren Sammlungs Wert aufweisen kann.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyCollection()]
    [String[]]
    $ComputerName
)
```

### <a name="validatecount-validation-attribute"></a>Validatecount-Validierungs Attribut

Das **validatecount** -Attribut gibt die minimale und maximale Anzahl von Parameterwerten an, die von einem Parameter akzeptiert werden. PowerShell generiert einen Fehler, wenn die Anzahl der Parameterwerte im Befehl, der die Funktion aufruft, außerhalb dieses Bereichs liegt.

Die folgende Parameter Deklaration erstellt einen **Computername** -Parameter, der einen bis fünf Parameterwerte annimmt.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateCount(1,5)]
    [String[]]
    $ComputerName
)
```

### <a name="validatelength-validation-attribute"></a>ValidateLength-Validierungs Attribut

Mit dem **validateLength** -Attribut werden die Mindest-und höchst Anzahl von Zeichen in einem Parameter-oder Variablen Wert angegeben. PowerShell generiert einen Fehler, wenn die Länge eines Werts, der für einen Parameter oder eine Variable angegeben wurde, außerhalb des Bereichs liegt.

Im folgenden Beispiel muss jeder Computername ein bis zehn Zeichen lang sein.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateLength(1,10)]
    [String[]]
    $ComputerName
)
```

Im folgenden Beispiel muss der Wert der `$number` -Variablen mindestens ein Zeichen lang sein und maximal zehn Zeichen enthalten.

```powershell
[Int32][ValidateLength(1,10)]$number = '01'
```

> [!NOTE]
> In diesem Beispiel wird der Wert von `01` in einfache Anführungszeichen eingeschlossen. Das **validateLength** -Attribut akzeptiert keine Zahl, ohne in Anführungszeichen eingeschlossen zu werden.

### <a name="validatepattern-validation-attribute"></a>Validatepattern-Validierungs Attribut

Das **validatepattern** -Attribut gibt einen regulären Ausdruck an, der mit dem-Parameter oder dem Variablen Wert verglichen wird. PowerShell generiert einen Fehler, wenn der Wert nicht dem Muster für reguläre Ausdrücke entspricht.

Im folgenden Beispiel muss der Parameterwert eine vierstellige Zahl enthalten, und jede Ziffer muss eine Zahl von 0 bis 9 sein.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [String[]]
    $ComputerName
)
```

Im folgenden Beispiel muss der Wert der `$number` -Variable genau eine vierstellige Zahl sein, und jede Ziffer muss eine Zahl von 0 bis 9 sein.

```powershell
[Int32][ValidatePattern("^[0-9][0-9][0-9][0-9]$")]$number = 1111
```

### <a name="validaterange-validation-attribute"></a>Validaterange-Validierungs Attribut

Das **validaterange** -Attribut gibt einen numerischen Bereich oder einen **validaterangekind-Enumerationswert** für jeden Parameter oder Variablen Wert an.
PowerShell generiert einen Fehler, wenn ein beliebiger Wert außerhalb dieses Bereichs liegt.

Die **validaterangekind** -Enumeration ermöglicht die folgenden Werte:

- **Positiv** -eine Zahl größer als 0 (null).
- **Negativ** -eine Zahl kleiner als 0 (null).
- **Nicht positiv** -eine Zahl, die kleiner oder gleich 0 (null) ist.
- **Nicht negativ** -eine Zahl größer oder gleich 0 (null).

Im folgenden Beispiel muss der Wert des **Versuchs** -Parameters zwischen 0 und 10 liegen.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateRange(0,10)]
    [Int]
    $Attempts
)
```

Im folgenden Beispiel muss der Wert der `$number` -Variablen zwischen 0 und 10 liegen.

```powershell
[Int32][ValidateRange(0,10)]$number = 5
```

Im folgenden Beispiel muss der Wert der-Variablen `$number` größer als 0 (null) sein.

```powershell
[Int32][ValidateRange("Positive")]$number = 1
```

### <a name="validatescript-validation-attribute"></a>Validatescript-Validierungs Attribut

Das **validatescript** -Attribut gibt ein Skript an, das verwendet wird, um einen Parameter-oder Variablen Wert zu validieren. PowerShell übergibt den Wert an das Skript und generiert einen Fehler, wenn das Skript zurückgibt, `$false` oder wenn das Skript eine Ausnahme auslöst.

Wenn Sie das **validatescript** -Attribut verwenden, wird der zu validierende Wert der `$_` Variablen zugeordnet. Sie können die- `$_` Variable verwenden, um auf den Wert im Skript zu verweisen.

Im folgenden Beispiel muss der Wert des **eventdate** -Parameters größer oder gleich dem aktuellen Datum sein.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateScript({$_ -ge (Get-Date)})]
    [DateTime]
    $EventDate
)
```

Im folgenden Beispiel muss der Wert der-Variablen `$date` größer oder gleich dem aktuellen Datum und der aktuellen Uhrzeit sein.

```powershell
[DateTime][ValidateScript({$_ -ge (Get-Date)})]$date = (Get-Date)
```

> [!NOTE]
> Wenn Sie **validatescript** verwenden, können Sie keinen `$null` Wert an den-Parameter übergeben. Wenn Sie einen NULL-Wert übergeben, kann **validatescript** das Argument nicht validieren.

### <a name="validateset-attribute"></a>Validateset-Attribut

Das **validateset** -Attribut gibt einen Satz gültiger Werte für einen Parameter oder eine Variable an und ermöglicht die Vervollständigung mit der Tab-Taste. PowerShell generiert einen Fehler, wenn ein Parameter-oder Variablen Wert nicht mit einem Wert im Satz identisch ist. Im folgenden Beispiel kann der Wert des **Detail** -Parameters nur "Low", "Average" oder "High" sein.

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("Low", "Average", "High")]
    [String[]]
    $Detail
)
```

Im folgenden Beispiel muss der Wert der Variablen entweder " `$flavor` Chocolate", "Strawberry" oder "Vanilla" lauten.

```powershell
[ValidateSet("Chocolate", "Strawberry", "Vanilla")]
[String]$flavor = "Strawberry"
```

Die Validierung erfolgt immer dann, wenn diese Variable auch innerhalb des Skripts zugewiesen wird. Beispielsweise führt Folgendes zur Laufzeit zu einem Fehler:

```powershell
Param(
    [ValidateSet("hello", "world")]
    [String]$Message
)

$Message = "bye"
```

#### <a name="dynamic-validateset-values"></a>Dynamische validateset-Werte

Sie können eine **Klasse** verwenden, um die Werte für **validateset** zur Laufzeit dynamisch zu generieren. Im folgenden Beispiel werden die gültigen Werte für die Variable `$Sound` über eine **Klasse** namens " **soundnames** " generiert, die drei Dateisystem Pfade auf verfügbare Audiodateien überprüft:

```powershell
Class SoundNames : System.Management.Automation.IValidateSetValuesGenerator {
    [String[]] GetValidValues() {
        $SoundPaths = '/System/Library/Sounds/',
            '/Library/Sounds','~/Library/Sounds'
        $SoundNames = ForEach ($SoundPath in $SoundPaths) {
            If (Test-Path $SoundPath) {
                (Get-ChildItem $SoundPath).BaseName
            }
        }
        return [String[]] $SoundNames
    }
}
```

Die `[SoundNames]` Klasse wird dann wie folgt als dynamischer **validateset** -Wert implementiert:

```powershell
Param(
    [ValidateSet([SoundNames])]
    [String]$Sound
)
```

### <a name="validatenotnull-validation-attribute"></a>Validatenotnull-Validierungs Attribut

Das **validatenotnull** -Attribut gibt an, dass der Parameterwert nicht sein darf `$null` . PowerShell generiert einen Fehler, wenn der Parameterwert ist `$null` .

Das **validatenotnull** -Attribut ist so konzipiert, dass es verwendet wird, wenn der Parameter optional ist und der Typ nicht definiert ist oder über einen Typkonverter verfügt, der einen NULL-Wert wie **Object** nicht implizit konvertieren kann. Wenn Sie einen Typ angeben, der implizit einen NULL-Wert (z. b. eine **Zeichenfolge** ) konvertiert, wird der NULL-Wert in eine leere Zeichenfolge konvertiert, auch wenn das **validatenotnull** -Attribut verwendet wird. Verwenden Sie für dieses Szenario **validatenotnullorempty** .

Im folgenden Beispiel kann der Wert des **ID** -Parameters nicht sein `$null` .

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [ValidateNotNull()]
    $ID
)
```

### <a name="validatenotnullorempty-validation-attribute"></a>Validatenotnullorempty-Validierungs Attribut

Das **validatenotnullorempty** -Attribut gibt an, dass der Parameterwert nicht sein darf `$null` und keine leere Zeichenfolge () sein kann `""` . PowerShell generiert einen Fehler, wenn der Parameter in einem Funktions Aufrufsatz verwendet wird, der Wert `$null` jedoch, eine leere Zeichenfolge ( `""` ) oder ein leeres Array ist `@()` .

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateNotNullOrEmpty()]
    [String[]]
    $UserName
)
```

### <a name="validatedrive-validation-attribute"></a>Validatedrive-Validierungs Attribut

Das **validatedrive** -Attribut gibt an, dass der Parameterwert den Pfad darstellen muss, der nur auf zulässige Laufwerke verweist. PowerShell generiert einen Fehler, wenn der Parameterwert auf Laufwerke verweist, die nicht zulässig sind. Das vorhanden sein des Pfads mit Ausnahme des Laufwerks selbst wird nicht überprüft.

Wenn Sie einen relativen Pfad verwenden, muss das aktuelle Laufwerk in der Liste zulässiger Laufwerke enthalten sein.

```powershell
Param(
    [ValidateDrive("C", "D", "Variable", "Function")]
    [String]$Path
)
```

### <a name="validateuserdrive-validation-attribute"></a>Validateuserdrive-Validierungs Attribut

Das **validateuserdrive** -Attribut gibt an, dass der Parameterwert den Pfad darstellen muss, der sich auf das `User` Laufwerk bezieht. PowerShell generiert einen Fehler, wenn sich der Pfad auf ein anderes Laufwerk bezieht. Das Validierungs Attribut testet nur, ob der Laufwerks Teil des Pfads vorhanden ist.

Wenn Sie einen relativen Pfad verwenden, muss das aktuelle Laufwerk sein `User` .

```powershell
function Test-UserDrivePath{
    [OutputType([bool])]
    Param(
      [Parameter(Mandatory=, Position=0)][ValidateUserDrive()][String]$Path
      )
    $True
}

Test-UserDrivePath -Path C:\
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. The path
argument drive C does not belong to the set of approved drives: User.
Supply a path argument with an approved drive.
```

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
Test-UserDrivePath: Cannot validate argument on parameter 'Path'. Cannot
find drive. A drive with the name 'User' does not exist.
```

Sie können das `User` Laufwerk in Just Enough Administration (Jea)-Sitzungs Konfigurationen definieren. In diesem Beispiel erstellen wir das Laufwerk User:.

```powershell
New-PSDrive -Name 'User' -PSProvider FileSystem -Root $env:HOMEPATH
```

```Output
Name           Used (GB)     Free (GB) Provider      Root
----           ---------     --------- --------      ----
User               75.76         24.24 FileSystem    C:\Users\ExampleUser

```powershell
Test-UserDrivePath -Path 'User:\A_folder_that_does_not_exist'
```

```Output
True
```

### <a name="validatetrusteddata-validation-attribute"></a>Validatetrusteddata-Validierungs Attribut

Dieses Attribut wurde in PowerShell 6.1.1 hinzugefügt.

Zu diesem Zeitpunkt wird das-Attribut intern von PowerShell selbst verwendet und ist nicht für die externe Verwendung vorgesehen.

## <a name="dynamic-parameters"></a>Dynamische Parameter

Dynamische Parameter sind Parameter eines Cmdlets, einer Funktion oder eines Skripts, die nur unter bestimmten Bedingungen verfügbar sind.

Beispielsweise verfügen mehrere Anbieter-Cmdlets über Parameter, die nur verfügbar sind, wenn das Cmdlet im Anbieter Laufwerk oder in einem bestimmten Pfad des Anbieter Laufwerks verwendet wird. Der **Encoding** -Parameter ist beispielsweise `Add-Content` `Get-Content` nur in den-,-und `Set-Content` -Cmdlets verfügbar, wenn er in einem Dateisystem Laufwerk verwendet wird.

Sie können auch einen Parameter erstellen, der nur angezeigt wird, wenn ein anderer Parameter im Funktionsbefehl verwendet wird oder wenn ein anderer Parameter einen bestimmten Wert aufweist.

Dynamische Parameter können nützlich sein, Sie sollten jedoch nur bei Bedarf verwendet werden, da Sie für Benutzer schwer zu erkennen sind. Um einen dynamischen Parameter zu finden, muss sich der Benutzer im Anbieter Pfad befinden, den Argument **List** -Parameter des `Get-Command` Cmdlets verwenden oder den **path** -Parameter von verwenden `Get-Help` .

Um einen dynamischen Parameter für eine Funktion oder ein Skript zu erstellen, verwenden Sie das- `DynamicParam` Schlüsselwort.

Die Syntax ist wie folgt:

`DynamicParam {<statement-list>}`

Verwenden Sie in der Anweisungs Liste eine- `If` Anweisung, um die Bedingungen anzugeben, unter denen der-Parameter in der-Funktion verfügbar ist.

Verwenden `New-Object` Sie das Cmdlet, um ein **System. Management. Automation. runtimedefinedparameter** -Objekt zu erstellen, das den Parameter darstellt, und geben Sie seinen Namen an.

Sie können einen `New-Object` Befehl verwenden, um ein **System. Management. Automation. Parameterattribute** -Objekt zu erstellen, das Attribute des Parameters darstellt, wie z. b. **obligatorisch** , **Position** oder **valuefrompipeline** oder den Parametersatz.

Das folgende Beispiel zeigt eine Beispiel Funktion mit Standardparametern namens " **Name** " und " **path** " und einen optionalen dynamischen Parameter namens **DP1**. Der **DP1** -Parameter ist im `PSet1` Parametersatz und weist den Typ auf `Int32` .
Der **DP1** -Parameter ist nur in der- `Get-Sample` Funktion verfügbar, wenn der Wert des **path** -Parameters mit beginnt `HKLM:` , was darauf hinweist, dass er im `HKEY_LOCAL_MACHINE` Registrierungs Laufwerk verwendet wird.

```powershell
function Get-Sample {
  [CmdletBinding()]
  Param([String]$Name, [String]$Path)

  DynamicParam
  {
    if ($Path.StartsWith("HKLM:"))
    {
      $attributes = New-Object -Type `
        System.Management.Automation.ParameterAttribute
      $attributes.ParameterSetName = "PSet1"
      $attributes.Mandatory = $false
      $attributeCollection = New-Object `
        -Type System.Collections.ObjectModel.Collection[System.Attribute]
      $attributeCollection.Add($attributes)

      $dynParam1 = New-Object -Type `
        System.Management.Automation.RuntimeDefinedParameter("DP1", [Int32],
          $attributeCollection)

      $paramDictionary = New-Object `
        -Type System.Management.Automation.RuntimeDefinedParameterDictionary
      $paramDictionary.Add("DP1", $dynParam1)
      return $paramDictionary
    }
  }
}
```

Weitere Informationen finden Sie unter [runtimedefinedparameter](/dotnet/api/system.management.automation.runtimedefinedparameter).

## <a name="switch-parameters"></a>Switch-Parameter

Switch-Parameter sind Parameter ohne Parameterwert. Sie sind nur wirksam, wenn Sie verwendet werden und nur einen Effekt haben.

Beispielsweise ist der **NoProfile** -Parameter von **powershell.exe** ein Switch-Parameter.

Um einen Switch-Parameter in einer Funktion zu erstellen, geben Sie den `Switch` Typ in der Parameterdefinition an.

Beispiel:

```powershell
Param([Switch]<ParameterName>)
```

Oder Sie können eine andere Methode verwenden:

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [Switch]
    $<ParameterName>
)
```

Switch-Parameter sind einfach zu verwenden und werden gegenüber booleschen Parametern bevorzugt, die eine schwierigere Syntax aufweisen.

Um z. b. einen Switch-Parameter zu verwenden, gibt der Benutzer den-Parameter in den Befehl ein.

`-IncludeAll`

Um einen booleschen Parameter zu verwenden, gibt der Benutzer den-Parameter und einen booleschen Wert ein.

`-IncludeAll:$true`

Wählen Sie beim Erstellen von Switch-Parametern den Parameternamen sorgfältig aus. Stellen Sie sicher, dass der Parameter Name die Auswirkung des Parameters an den Benutzer übermittelt.
Vermeiden Sie mehrdeutige Begriffe, wie z. b. **Filter** oder **Maximum** , die impliziert, dass ein Wert erforderlich ist.

## <a name="argumentcompleter-attribute"></a>Argumentcompleter-Attribut

Mithilfe des **argumentcompleter** -Attributs können Sie einem bestimmten Parameter Tabstopp-Vervollständigungs Werte hinzufügen. Für jeden Parameter, der die Vervollständigung der Tab-Taste erfordert, muss ein Argument **Completer** -Attribut definiert werden Ähnlich wie bei **DynamicParameters** werden die verfügbaren Werte zur Laufzeit berechnet, wenn der Benutzer die <kbd>Tab</kbd> -Taste nach dem Parameternamen drückt.

Zum Hinzufügen eines **argumentcompleter** -Attributs müssen Sie einen Skriptblock definieren, der die Werte bestimmt. Der Skriptblock muss die folgenden Parameter in der unten angegebenen Reihenfolge verwenden. Die Namen des Parameters sind nicht von Bedeutung, da die Werte Positions bedingt bereitgestellt werden.

Die Syntax ist wie folgt:

```powershell
Param(
    [Parameter(Mandatory)]
    [ArgumentCompleter({
        param ( $commandName,
                $parameterName,
                $wordToComplete,
                $commandAst,
                $fakeBoundParameters )
        # Perform calculation of tab completed values here.
    })]
)
```

### <a name="argumentcompleter-script-block"></a>Argumentcompleter-Skriptblock

Die Skriptblock Parameter werden auf die folgenden Werte festgelegt:

- `$commandName` (Position 0): dieser Parameter wird auf den Namen des Befehls festgelegt, für den der Skriptblock die Vervollständigung mit der Tab-Taste bereitstellt.
- `$parameterName` (Position 1): dieser Parameter ist auf den Parameter festgelegt, dessen Wert die Vervollständigung der Tab-Taste erfordert.
- `$wordToComplete` (Position 2): dieser Parameter ist auf den Wert festgelegt, den der Benutzer vor dem Drücken der <kbd>Tab</kbd>-Taste angegeben hat. Der Skriptblock sollte diesen Wert verwenden, um die Vervollständigungs Werte der Registerkarte zu ermitteln.
- `$commandAst` (Position 3): dieser Parameter ist für die aktuelle Eingabezeile auf die abstrakte Syntax Struktur (AST, Abstract Syntax Tree) festgelegt. Weitere Informationen finden Sie unter [AST-Klasse](/dotnet/api/system.management.automation.language.ast).
- `$fakeBoundParameters` (Position 4): dieser Parameter wird auf eine Hash Tabelle festgelegt, die den `$PSBoundParameters` für das Cmdlet enthält, bevor der Benutzer die <kbd>Tab</kbd>-Taste gedrückt hat. Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).

Der **argumentcompleter** -Skriptblock muss die Registrierung der Werte mithilfe der Pipeline, wie `ForEach-Object` z `Where-Object` . b., oder einer anderen geeigneten Methode, aufheben.
Das Zurückgeben eines Arrays von Werten bewirkt, dass PowerShell das gesamte Array als **einen** Vervollständigungs Wert mit der Tab-Taste behandelt.

Im folgenden Beispiel wird dem **value** -Parameter die Befehlszeilen Vervollständigung hinzugefügt. Wenn nur der **value** -Parameter angegeben wird, werden alle möglichen Werte oder Argumente für **value** angezeigt. Wenn der **Typparameter** angegeben wird, zeigt der **value** -Parameter nur die möglichen Werte für diesen Typ an.

Außerdem stellt der- `-like` Operator sicher, dass, wenn der Benutzer den folgenden Befehl eingibt und die <kbd>Tab</kbd> -Taste verwendet, nur **Apple** zurückgegeben wird.

`Test-ArgumentCompleter -Type Fruits -Value A`

```powershell
function Test-ArgumentCompleter {
[CmdletBinding()]
 param (
        [Parameter(Mandatory=$true)]
        [ValidateSet('Fruits', 'Vegetables')]
        $Type,
        [Parameter(Mandatory=$true)]
        [ArgumentCompleter( {
            param ( $commandName,
                    $parameterName,
                    $wordToComplete,
                    $commandAst,
                    $fakeBoundParameters )

            $possibleValues = @{
                Fruits = @('Apple', 'Orange', 'Banana')
                Vegetables = @('Tomato', 'Squash', 'Corn')
            }
            if ($fakeBoundParameters.ContainsKey('Type'))
            {
                $possibleValues[$fakeBoundParameters.Type] | Where-Object {
                    $_ -like "$wordToComplete*"
                }
            }
            else
            {
                $possibleValues.Values | ForEach-Object {$_}
            }
        } )]
        $Value
      )
}
```

## <a name="see-also"></a>Weitere Informationen:

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)
