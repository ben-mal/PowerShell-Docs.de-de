---
description: Erläutert das Hinzufügen von Parametern zu erweiterten Funktionen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced_Parameters
ms.openlocfilehash: 4123d71392f8b32df8d04033d85476cb18b39736
ms.sourcegitcommit: 3b1779890f828130a9d73aebf17ebffae511728f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "93225252"
---
# <a name="about-functions-advanced-parameters"></a><span data-ttu-id="88d15-104">Informationen zu erweiterten Functions-Parametern</span><span class="sxs-lookup"><span data-stu-id="88d15-104">About Functions Advanced Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="88d15-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88d15-105">Short description</span></span>

<span data-ttu-id="88d15-106">Erläutert das Hinzufügen von Parametern zu erweiterten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="88d15-106">Explains how to add parameters to advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="88d15-107">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88d15-107">Long description</span></span>

<span data-ttu-id="88d15-108">Sie können den erweiterten Funktionen, die Sie schreiben, Parameter hinzufügen und Parameter Attribute und-Argumente verwenden, um die Parameterwerte einzuschränken, die Benutzer mit dem-Parameter übermitteln.</span><span class="sxs-lookup"><span data-stu-id="88d15-108">You can add parameters to the advanced functions that you write, and use parameter attributes and arguments to limit the parameter values that function users submit with the parameter.</span></span>

<span data-ttu-id="88d15-109">Die Parameter, die Sie ihrer Funktion hinzufügen, stehen Benutzern zusätzlich zu den allgemeinen Parametern zur Verfügung, die von PowerShell automatisch zu allen Cmdlets und erweiterten Funktionen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="88d15-109">The parameters that you add to your function are available to users in addition to the common parameters that PowerShell adds automatically to all cmdlets and advanced functions.</span></span> <span data-ttu-id="88d15-110">Weitere Informationen zu den allgemeinen PowerShell-Parametern finden Sie unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="88d15-110">For more information about the PowerShell common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="88d15-111">Ab PowerShell 3,0 können Sie Verteilung mit verwenden, `@Args` um die Parameter in einem Befehl darzustellen.</span><span class="sxs-lookup"><span data-stu-id="88d15-111">Beginning in PowerShell 3.0, you can use splatting with `@Args` to represent the parameters in a command.</span></span> <span data-ttu-id="88d15-112">Splatting ist in einfachen und erweiterten Funktionen gültig.</span><span class="sxs-lookup"><span data-stu-id="88d15-112">Splatting is valid on simple and advanced functions.</span></span> <span data-ttu-id="88d15-113">Weitere Informationen finden Sie unter [about_Functions](about_Functions.md) und [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="88d15-113">For more information, see [about_Functions](about_Functions.md) and [about_Splatting](about_Splatting.md).</span></span>

## <a name="type-conversion-of-parameter-values"></a><span data-ttu-id="88d15-114">Typkonvertierung von Parameterwerten</span><span class="sxs-lookup"><span data-stu-id="88d15-114">Type conversion of parameter values</span></span>

<span data-ttu-id="88d15-115">Wenn Sie Zeichen folgen als Argumente für Parameter angeben, die einen anderen Typ erwarten, konvertiert PowerShell die Zeichen folgen implizit in den Zieltyp des Parameters.</span><span class="sxs-lookup"><span data-stu-id="88d15-115">When you supply strings as arguments to parameters that expect a different type, PowerShell implicitly converts the strings to the parameter target type.</span></span>
<span data-ttu-id="88d15-116">Erweiterte Funktionen führen eine Kultur invariante Verarbeitung von Parameterwerten aus.</span><span class="sxs-lookup"><span data-stu-id="88d15-116">Advanced functions perform culture-invariant parsing of parameter values.</span></span>

<span data-ttu-id="88d15-117">Im Gegensatz dazu wird bei der Parameter Bindung für kompilierte Cmdlets eine Kultur abhängige Konvertierung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="88d15-117">By contrast, a culture-sensitive conversion is performed during parameter binding for compiled cmdlets.</span></span>

<span data-ttu-id="88d15-118">In diesem Beispiel erstellen wir ein Cmdlet und eine Skriptfunktion, die einen `[datetime]` Parameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="88d15-118">In this example, we create a cmdlet and a script function that take a `[datetime]` parameter.</span></span> <span data-ttu-id="88d15-119">Die aktuelle Kultur wird so geändert, dass Sie die deutschen Einstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="88d15-119">The current culture is changed to use German settings.</span></span>
<span data-ttu-id="88d15-120">Ein deutsch formatiertes Datum wird an den-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="88d15-120">A German-formatted date is passed to the parameter.</span></span>

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

<span data-ttu-id="88d15-121">Wie oben gezeigt, verwenden Cmdlets die Kultur abhängige Verarbeitung, um die Zeichenfolge zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="88d15-121">As shown above, cmdlets use culture-sensitive parsing to convert the string.</span></span>

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

<span data-ttu-id="88d15-122">Erweiterte Funktionen verwenden eine Kultur invariante Verarbeitung, die zu folgendem Fehler führt.</span><span class="sxs-lookup"><span data-stu-id="88d15-122">Advanced functions use culture-invariant parsing, which results in the following error.</span></span>

```Output
Get-Date_Func : Cannot process argument transformation on parameter 'Date'. Cannot convert
 value "19-06-2018" to type "System.DateTime". Error: "String was not recognized as a valid
 DateTime."
At line:13 char:15
+ Get-Date_Func $dateStr
+               ~~~~~~~~
    + CategoryInfo          : InvalidData: (:) [Get-Date_Func], ParameterBindingArgumentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Get-Date_Func
```

## <a name="static-parameters"></a><span data-ttu-id="88d15-123">Statische Parameter</span><span class="sxs-lookup"><span data-stu-id="88d15-123">Static parameters</span></span>

<span data-ttu-id="88d15-124">Statische Parameter sind Parameter, die in der Funktion immer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="88d15-124">Static parameters are parameters that are always available in the function.</span></span>
<span data-ttu-id="88d15-125">Die meisten Parameter in PowerShell-Cmdlets und-Skripts sind statische Parameter.</span><span class="sxs-lookup"><span data-stu-id="88d15-125">Most parameters in PowerShell cmdlets and scripts are static parameters.</span></span>

<span data-ttu-id="88d15-126">Das folgende Beispiel zeigt die Deklaration eines **Computername** -Parameters, der die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="88d15-126">The following example shows the declaration of a **ComputerName** parameter that has the following characteristics:</span></span>

- <span data-ttu-id="88d15-127">Dies ist obligatorisch (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="88d15-127">It's mandatory (required).</span></span>
- <span data-ttu-id="88d15-128">Er nimmt Eingaben aus der Pipeline an.</span><span class="sxs-lookup"><span data-stu-id="88d15-128">It takes input from the pipeline.</span></span>
- <span data-ttu-id="88d15-129">Es wird ein Array von Zeichen folgen als Eingabe benötigt.</span><span class="sxs-lookup"><span data-stu-id="88d15-129">It takes an array of strings as input.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

## <a name="attributes-of-parameters"></a><span data-ttu-id="88d15-130">Attribute von Parametern</span><span class="sxs-lookup"><span data-stu-id="88d15-130">Attributes of parameters</span></span>

<span data-ttu-id="88d15-131">In diesem Abschnitt werden die Attribute beschrieben, die Sie Funktionsparametern hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="88d15-131">This section describes the attributes that you can add to function parameters.</span></span>

<span data-ttu-id="88d15-132">Alle Attribute sind optional.</span><span class="sxs-lookup"><span data-stu-id="88d15-132">All attributes are optional.</span></span> <span data-ttu-id="88d15-133">Wenn Sie jedoch das **cmdletbinding** -Attribut weglassen und als erweiterte Funktion erkannt werden, muss die Funktion das **Parameter** Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="88d15-133">However, if you omit the **CmdletBinding** attribute, then to be recognized as an advanced function, the function must include the **Parameter** attribute.</span></span>

<span data-ttu-id="88d15-134">Sie können in jeder Parameter Deklaration ein oder mehrere Attribute hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="88d15-134">You can add one or multiple attributes in each parameter declaration.</span></span> <span data-ttu-id="88d15-135">Es gibt keine Beschränkung für die Anzahl der Attribute, die Sie einer Parameter Deklaration hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="88d15-135">There's no limit to the number of attributes that you can add to a parameter declaration.</span></span>

### <a name="parameter-attribute"></a><span data-ttu-id="88d15-136">Parameterattribut</span><span class="sxs-lookup"><span data-stu-id="88d15-136">Parameter attribute</span></span>

<span data-ttu-id="88d15-137">Das **Parameter** -Attribut wird verwendet, um die Attribute von Funktionsparametern zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="88d15-137">The **Parameter** attribute is used to declare the attributes of function parameters.</span></span>

<span data-ttu-id="88d15-138">Das **Parameter** Attribut ist optional, und Sie können es weglassen, wenn keiner der Parameter ihrer Funktionen Attribute benötigt.</span><span class="sxs-lookup"><span data-stu-id="88d15-138">The **Parameter** attribute is optional, and you can omit it if none of the parameters of your functions need attributes.</span></span> <span data-ttu-id="88d15-139">Um jedoch als erweiterte Funktion und nicht als einfache Funktion erkannt zu werden, muss eine Funktion entweder das **cmdletbinding** -Attribut oder das **Parameter** -Attribut oder beides aufweisen.</span><span class="sxs-lookup"><span data-stu-id="88d15-139">But, to be recognized as an advanced function, rather than a simple function, a function must have either the **CmdletBinding** attribute or the **Parameter** attribute, or both.</span></span>

<span data-ttu-id="88d15-140">Das **Parameter** Attribut verfügt über Argumente, die die Merkmale des Parameters definieren, z. b. ob der Parameter obligatorisch oder optional ist.</span><span class="sxs-lookup"><span data-stu-id="88d15-140">The **Parameter** attribute has arguments that define the characteristics of the parameter, such as whether the parameter is mandatory or optional.</span></span>

<span data-ttu-id="88d15-141">Verwenden Sie die folgende Syntax, um das **Parameter** Attribut, ein Argument und einen Argument Wert zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="88d15-141">Use the following syntax to declare the **Parameter** attribute, an argument, and an argument value.</span></span> <span data-ttu-id="88d15-142">Die Klammern, die das Argument und seinen Wert einschließen, müssen **Parameter** ohne dazwischenliegende Leerzeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="88d15-142">The parentheses that enclose the argument and its value must follow **Parameter** with no intervening space.</span></span>

```powershell
Param(
    [Parameter(Argument=value)]
    $ParameterName
)
```

<span data-ttu-id="88d15-143">Verwenden Sie Kommas zum Trennen von Argumenten innerhalb der Klammern.</span><span class="sxs-lookup"><span data-stu-id="88d15-143">Use commas to separate arguments within the parentheses.</span></span> <span data-ttu-id="88d15-144">Verwenden Sie die folgende Syntax, um zwei Argumente des **Parameter** -Attributs zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="88d15-144">Use the following syntax to declare two arguments of the **Parameter** attribute.</span></span>

```powershell
Param(
    [Parameter(Argument1=value1,
    Argument2=value2)]
)
```

<span data-ttu-id="88d15-145">Die booleschen Argument Typen des **Parameter** Attributs werden standardmäßig auf **false** zurückzuführen, wenn Sie im **Parameter** -Attribut ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="88d15-145">The boolean argument types of the **Parameter** attribute default to **False** when omitted from the **Parameter** attribute.</span></span> <span data-ttu-id="88d15-146">Legen Sie den Argument Wert auf fest, `$true` oder Listen Sie einfach das Argument nach Namen auf.</span><span class="sxs-lookup"><span data-stu-id="88d15-146">Set the argument value to `$true` or just list the argument by name.</span></span> <span data-ttu-id="88d15-147">Die folgenden **Parameter** Attribute sind z. b. äquivalent.</span><span class="sxs-lookup"><span data-stu-id="88d15-147">For example, the following **Parameter** attributes are equivalent.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
)

# Boolean arguments can be defined using this shorthand syntax

Param(
    [Parameter(Mandatory)]
)
```

<span data-ttu-id="88d15-148">Wenn Sie das **Parameter** Attribut ohne Argumente als Alternative zur Verwendung des **cmdletbinding** -Attributs verwenden, sind die Klammern, die dem Attributnamen folgen, weiterhin erforderlich.</span><span class="sxs-lookup"><span data-stu-id="88d15-148">If you use the **Parameter** attribute without arguments, as an alternative to using the **CmdletBinding** attribute, the parentheses that follow the attribute name are still required.</span></span>

```powershell
Param(
    [Parameter()]
    $ParameterName
)
```

#### <a name="mandatory-argument"></a><span data-ttu-id="88d15-149">Obligatorisches Argument</span><span class="sxs-lookup"><span data-stu-id="88d15-149">Mandatory argument</span></span>

<span data-ttu-id="88d15-150">Das- `Mandatory` Argument gibt an, dass der-Parameter erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="88d15-150">The `Mandatory` argument indicates that the parameter is required.</span></span> <span data-ttu-id="88d15-151">Wenn dieses Argument nicht angegeben wird, ist der Parameter optional.</span><span class="sxs-lookup"><span data-stu-id="88d15-151">If this argument isn't specified, the parameter is optional.</span></span>

<span data-ttu-id="88d15-152">Im folgenden Beispiel wird der **Computername** -Parameter deklariert.</span><span class="sxs-lookup"><span data-stu-id="88d15-152">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="88d15-153">Er verwendet das- `Mandatory` Argument, um den-Parameter obligatorisch zu machen.</span><span class="sxs-lookup"><span data-stu-id="88d15-153">It uses the `Mandatory` argument to make the parameter mandatory.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="position-argument"></a><span data-ttu-id="88d15-154">Positions Argument</span><span class="sxs-lookup"><span data-stu-id="88d15-154">Position argument</span></span>

<span data-ttu-id="88d15-155">Das- `Position` Argument bestimmt, ob der Parameter Name erforderlich ist, wenn der-Parameter in einem Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-155">The `Position` argument determines whether the parameter name is required when the parameter is used in a command.</span></span> <span data-ttu-id="88d15-156">Wenn eine Parameter Deklaration das- `Position` Argument enthält, kann der Parameter Name ausgelassen werden, und PowerShell identifiziert den unbenannten Parameterwert anhand seiner Position oder Reihenfolge in der Liste unbenannter Parameterwerte im Befehl.</span><span class="sxs-lookup"><span data-stu-id="88d15-156">When a parameter declaration includes the `Position` argument, the parameter name can be omitted and PowerShell identifies the unnamed parameter value by its position, or order, in the list of unnamed parameter values in the command.</span></span>

<span data-ttu-id="88d15-157">Wenn das- `Position` Argument nicht angegeben wird, muss der Parameter Name oder ein Parameter namens Alias oder eine Abkürzung dem Parameterwert vorangestellt werden, wenn der-Parameter in einem-Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-157">If the `Position` argument isn't specified, the parameter name, or a parameter name alias or abbreviation, must precede the parameter value whenever the parameter is used in a command.</span></span>

<span data-ttu-id="88d15-158">Standardmäßig sind alle Funktionsparameter positiontional.</span><span class="sxs-lookup"><span data-stu-id="88d15-158">By default, all function parameters are positional.</span></span> <span data-ttu-id="88d15-159">PowerShell weist den Parametern in der Reihenfolge, in der die Parameter in der Funktion deklariert werden, Positionsnummern zu.</span><span class="sxs-lookup"><span data-stu-id="88d15-159">PowerShell assigns position numbers to parameters in the order in which the parameters are declared in the function.</span></span> <span data-ttu-id="88d15-160">Um diese Funktion zu deaktivieren, legen Sie den Wert des- `PositionalBinding` Arguments des **cmdletbinding** -Attributs auf fest `$False` .</span><span class="sxs-lookup"><span data-stu-id="88d15-160">To disable this feature, set the value of the `PositionalBinding` argument of the **CmdletBinding** attribute to `$False`.</span></span> <span data-ttu-id="88d15-161">Das- `Position` Argument hat Vorrang vor dem Wert des- `PositionalBinding` Arguments des **cmdletbinding** -Attributs.</span><span class="sxs-lookup"><span data-stu-id="88d15-161">The `Position` argument takes precedence over the value of the `PositionalBinding` argument of the **CmdletBinding** attribute.</span></span> <span data-ttu-id="88d15-162">Weitere Informationen finden Sie unter `PositionalBinding` in [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span><span class="sxs-lookup"><span data-stu-id="88d15-162">For more information, see `PositionalBinding` in [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="88d15-163">Der Wert des- `Position` Arguments wird als ganze Zahl angegeben.</span><span class="sxs-lookup"><span data-stu-id="88d15-163">The value of the `Position` argument is specified as an integer.</span></span> <span data-ttu-id="88d15-164">Ein Positionswert von **0** stellt die erste Position im Befehl dar, der Positionswert **1** stellt die zweite Position im Befehl dar usw.</span><span class="sxs-lookup"><span data-stu-id="88d15-164">A position value of **0** represents the first position in the command, a position value of **1** represents the second position in the command, and so on.</span></span>

<span data-ttu-id="88d15-165">Wenn eine Funktion keine Positions Parameter hat, weist PowerShell den einzelnen Parametern Positionen basierend auf der Reihenfolge zu, in der die Parameter deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="88d15-165">If a function has no positional parameters, PowerShell assigns positions to each parameter based on the order in which the parameters are declared.</span></span>
<span data-ttu-id="88d15-166">Als bewährte Vorgehensweise sollten Sie sich jedoch nicht auf diese Zuweisung verlassen.</span><span class="sxs-lookup"><span data-stu-id="88d15-166">However, as a best practice, don't rely on this assignment.</span></span> <span data-ttu-id="88d15-167">Wenn Sie festlegen möchten, dass Parameter positionell sind, verwenden Sie das- `Position` Argument.</span><span class="sxs-lookup"><span data-stu-id="88d15-167">When you want parameters to be positional, use the `Position` argument.</span></span>

<span data-ttu-id="88d15-168">Im folgenden Beispiel wird der **Computername** -Parameter deklariert.</span><span class="sxs-lookup"><span data-stu-id="88d15-168">The following example declares the **ComputerName** parameter.</span></span> <span data-ttu-id="88d15-169">Dabei wird das- `Position` Argument mit dem Wert **0** verwendet.</span><span class="sxs-lookup"><span data-stu-id="88d15-169">It uses the `Position` argument with a value of **0**.</span></span> <span data-ttu-id="88d15-170">Folglich muss, wenn `-ComputerName` im Befehl weggelassen wird, der Wert der erste oder einzige unbenannte Parameterwert im Befehl sein.</span><span class="sxs-lookup"><span data-stu-id="88d15-170">As a result, when `-ComputerName` is omitted from command, its value must be the first or only unnamed parameter value in the command.</span></span>

```powershell
Param(
    [Parameter(Position=0)]
    [String[]]
    $ComputerName
)
```

#### <a name="parametersetname-argument"></a><span data-ttu-id="88d15-171">Parametersetname-Argument</span><span class="sxs-lookup"><span data-stu-id="88d15-171">ParameterSetName argument</span></span>

<span data-ttu-id="88d15-172">Das- `ParameterSetName` Argument gibt den Parametersatz an, zu dem ein Parameter gehört.</span><span class="sxs-lookup"><span data-stu-id="88d15-172">The `ParameterSetName` argument specifies the parameter set to which a parameter belongs.</span></span> <span data-ttu-id="88d15-173">Wenn kein Parametersatz angegeben wird, gehört der Parameter zu allen von der Funktion definierten Parametersätzen.</span><span class="sxs-lookup"><span data-stu-id="88d15-173">If no parameter set is specified, the parameter belongs to all the parameter sets defined by the function.</span></span> <span data-ttu-id="88d15-174">Daher muss jeder Parametersatz über mindestens einen Parameter verfügen, der kein Member eines anderen Parameter Satzes ist, damit er eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="88d15-174">Therefore, to be unique, each parameter set must have at least one parameter that isn't a member of any other parameter set.</span></span>

> [!NOTE]
> <span data-ttu-id="88d15-175">Für ein Cmdlet oder eine Funktion gibt es ein Limit von 32-Parametersätzen.</span><span class="sxs-lookup"><span data-stu-id="88d15-175">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

<span data-ttu-id="88d15-176">Im folgenden Beispiel wird ein **Computername** -Parameter im `Computer` Parametersatz, ein **username** -Parameter im `User` Parametersatz und ein **Summary** -Parameter in beiden Parametersätzen deklariert.</span><span class="sxs-lookup"><span data-stu-id="88d15-176">The following example declares a **ComputerName** parameter in the `Computer` parameter set, a **UserName** parameter in the `User` parameter set, and a **Summary** parameter in both parameter sets.</span></span>

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

<span data-ttu-id="88d15-177">Sie können `ParameterSetName` in jedem Argument nur einen Wert und `ParameterSetName` in jedem **Parameter** Attribut nur ein Argument angeben.</span><span class="sxs-lookup"><span data-stu-id="88d15-177">You can specify only one `ParameterSetName` value in each argument and only one `ParameterSetName` argument in each **Parameter** attribute.</span></span> <span data-ttu-id="88d15-178">Fügen Sie zusätzliche **Parameter** Attribute hinzu, um anzugeben, dass ein Parameter in mehr als einem Parametersatz enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="88d15-178">To indicate that a parameter appears in more than one parameter set, add additional **Parameter** attributes.</span></span>

<span data-ttu-id="88d15-179">Im folgenden Beispiel wird der **Summary** -Parameter explizit dem `Computer` -Parameter und dem- `User` Parametersatz hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="88d15-179">The following example explicitly adds the **Summary** parameter to the `Computer` and `User` parameter sets.</span></span> <span data-ttu-id="88d15-180">Der **Summary** -Parameter ist im `Computer` Parametersatz optional und im `User` Parametersatz obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="88d15-180">The **Summary** parameter is optional in the `Computer` parameter set and mandatory in the `User` parameter set.</span></span>

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

<span data-ttu-id="88d15-181">Weitere Informationen zu Parametersätzen finden Sie unter Informationen [zu Parametersätzen](about_parameter_sets.md).</span><span class="sxs-lookup"><span data-stu-id="88d15-181">For more information about parameter sets, see [About Parameter Sets](about_parameter_sets.md).</span></span>

#### <a name="valuefrompipeline-argument"></a><span data-ttu-id="88d15-182">Valuefrompipeline-Argument</span><span class="sxs-lookup"><span data-stu-id="88d15-182">ValueFromPipeline argument</span></span>

<span data-ttu-id="88d15-183">Das- `ValueFromPipeline` Argument gibt an, dass der-Parameter Eingaben von einem Pipeline Objekt akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="88d15-183">The `ValueFromPipeline` argument indicates that the parameter accepts input from a pipeline object.</span></span> <span data-ttu-id="88d15-184">Geben Sie dieses Argument an, wenn die Funktion das gesamte Objekt akzeptiert, nicht nur eine Eigenschaft des Objekts.</span><span class="sxs-lookup"><span data-stu-id="88d15-184">Specify this argument if the function accepts the entire object, not just a property of the object.</span></span>

<span data-ttu-id="88d15-185">Im folgenden Beispiel wird ein **Computername** -Parameter deklariert, der obligatorisch ist und ein-Objekt akzeptiert, das von der Pipeline an die Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-185">The following example declares a **ComputerName** parameter that's mandatory and accepts an object that's passed to the function from the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipeline=$true)]
    [String[]]
    $ComputerName
)
```

#### <a name="valuefrompipelinebypropertyname-argument"></a><span data-ttu-id="88d15-186">Valuefrompipelinebypropertyname-Argument</span><span class="sxs-lookup"><span data-stu-id="88d15-186">ValueFromPipelineByPropertyName argument</span></span>

<span data-ttu-id="88d15-187">Das- `ValueFromPipelineByPropertyName` Argument gibt an, dass der Parameter Eingaben aus einer Eigenschaft eines Pipeline Objekts akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="88d15-187">The `ValueFromPipelineByPropertyName` argument indicates that the parameter accepts input from a property of a pipeline object.</span></span> <span data-ttu-id="88d15-188">Die Object-Eigenschaft muss denselben Namen oder Alias wie der-Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="88d15-188">The object property must have the same name or alias as the parameter.</span></span>

<span data-ttu-id="88d15-189">Wenn die Funktion z. b. über einen **Computername** -Parameter verfügt und das weitergeleitete Objekt über eine **Computername** -Eigenschaft verfügt, wird der Wert der **Computername** -Eigenschaft dem **Computername** -Parameter der Funktion zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="88d15-189">For example, if the function has a **ComputerName** parameter, and the piped object has a **ComputerName** property, the value of the **ComputerName** property is assigned to the function's **ComputerName** parameter.</span></span>

<span data-ttu-id="88d15-190">Im folgenden Beispiel wird der erforderliche **Computername** -Parameter deklariert und Eingaben aus der **Computername** -Eigenschaft des Objekts akzeptiert, die über die Pipeline an die Funktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-190">The following example declares a **ComputerName** parameter that's mandatory and accepts input from the object's **ComputerName** property that's passed to the function through the pipeline.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    ValueFromPipelineByPropertyName=$true)]
    [String[]]
    $ComputerName
)
```

> [!NOTE]
> <span data-ttu-id="88d15-191">Ein typisierter Parameter, der Pipeline Eingaben ( `by Value` ) oder () akzeptiert, `by PropertyName` ermöglicht die Verwendung von _verzögerten Bindungs_ Skript Blöcken für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="88d15-191">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of _delay-bind_ script blocks on the parameter.</span></span>
>
> <span data-ttu-id="88d15-192">Der _Verzögerungs Bindungs_ Skriptblock wird automatisch während der **ParameterBinding** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="88d15-192">The _delay-bind_ script block is run automatically during **ParameterBinding**.</span></span> <span data-ttu-id="88d15-193">Das Ergebnis wird an den-Parameter gebunden.</span><span class="sxs-lookup"><span data-stu-id="88d15-193">The result is bound to the parameter.</span></span> <span data-ttu-id="88d15-194">Die verzögerte Bindung funktioniert nicht für Parameter, die als Typ oder definiert sind `ScriptBlock` `System.Object` .</span><span class="sxs-lookup"><span data-stu-id="88d15-194">Delay binding does not work for parameters defined as type `ScriptBlock` or `System.Object`.</span></span> <span data-ttu-id="88d15-195">Der Skriptblock wird durchlaufen, _ohne_ aufgerufen zu werden.</span><span class="sxs-lookup"><span data-stu-id="88d15-195">The script block is passed through _without_ being invoked.</span></span>
>
> <span data-ttu-id="88d15-196">Informationen zu _verzögerten Bindungs_ Skript Blöcken finden Sie hier [about_Script_Blocks. MD](about_Script_Blocks.md).</span><span class="sxs-lookup"><span data-stu-id="88d15-196">You can read about _delay-bind_ script blocks here [about_Script_Blocks.md](about_Script_Blocks.md).</span></span>

#### <a name="valuefromremainingarguments-argument"></a><span data-ttu-id="88d15-197">Valuefromremainingarguments-Argument</span><span class="sxs-lookup"><span data-stu-id="88d15-197">ValueFromRemainingArguments argument</span></span>

<span data-ttu-id="88d15-198">Das- `ValueFromRemainingArguments` Argument gibt an, dass der Parameter alle Werte des Parameters im Befehl akzeptiert, die anderen Parametern der Funktion nicht zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="88d15-198">The `ValueFromRemainingArguments` argument indicates that the parameter accepts all the parameter's values in the command that aren't assigned to other parameters of the function.</span></span>

<span data-ttu-id="88d15-199">Es gibt ein bekanntes Problem bei der Verwendung von Sammlungen mit **valuefromrestingarguments** , bei denen die eingehende Auflistung als einzelnes Element behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-199">There's a known issue for using collections with **ValueFromRemainingArguments** where the passed-in collection is treated as a single element.</span></span>

<span data-ttu-id="88d15-200">Im folgenden Beispiel wird dieses bekannte Problem veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="88d15-200">The following example demonstrates this known issue.</span></span> <span data-ttu-id="88d15-201">Der **verbleibende** Parameter sollte **einen** bei **Index 0** und **zwei** bei **Index 1** enthalten.</span><span class="sxs-lookup"><span data-stu-id="88d15-201">The **Remaining** parameter should contain **one** at **index 0** and **two** at **index 1**.</span></span>
<span data-ttu-id="88d15-202">Stattdessen werden beide Elemente zu einer einzelnen Entität zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="88d15-202">Instead, both elements are combined into a single entity.</span></span>

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
Found 1 elements
0: one two
```

> [!NOTE]
> <span data-ttu-id="88d15-203">Dieses Problem ist in PowerShell 6,2 behoben.</span><span class="sxs-lookup"><span data-stu-id="88d15-203">This issue is resolved in PowerShell 6.2.</span></span>

#### <a name="helpmessage-argument"></a><span data-ttu-id="88d15-204">Helpmessage-Argument</span><span class="sxs-lookup"><span data-stu-id="88d15-204">HelpMessage argument</span></span>

<span data-ttu-id="88d15-205">Das- `HelpMessage` Argument gibt eine Zeichenfolge an, die eine kurze Beschreibung des Parameters oder seines Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="88d15-205">The `HelpMessage` argument specifies a string that contains a brief description of the parameter or its value.</span></span> <span data-ttu-id="88d15-206">PowerShell zeigt diese Meldung an der Eingabeaufforderung an, die angezeigt wird, wenn ein obligatorischer Parameterwert in einem Befehl fehlt.</span><span class="sxs-lookup"><span data-stu-id="88d15-206">PowerShell displays this message in the prompt that appears when a mandatory parameter value is missing from a command.</span></span> <span data-ttu-id="88d15-207">Dieses Argument hat keine Auswirkung auf optionale Parameter.</span><span class="sxs-lookup"><span data-stu-id="88d15-207">This argument has no effect on optional parameters.</span></span>

<span data-ttu-id="88d15-208">Das folgende Beispiel deklariert einen obligatorischen **Computername** -Parameter und eine Hilfe Meldung, in der der erwartete Parameterwert erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-208">The following example declares a mandatory **ComputerName** parameter and a help message that explains the expected parameter value.</span></span>

<span data-ttu-id="88d15-209">Wenn keine andere [Kommentar basierte Hilfe](./about_comment_based_help.md) Syntax für die Funktion vorliegt (z. b.), wird `.SYNOPSIS` Diese Meldung auch in der `Get-Help` Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d15-209">If there is no other [comment-based help](./about_comment_based_help.md) syntax for the function (for example, `.SYNOPSIS`) then this message also shows up in `Get-Help` output.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true,
    HelpMessage="Enter one or more computer names separated by commas.")]
    [String[]]
    $ComputerName
)
```

### <a name="alias-attribute"></a><span data-ttu-id="88d15-210">Alias-Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-210">Alias attribute</span></span>

<span data-ttu-id="88d15-211">Das **Alias** -Attribut richtet einen alternativen Namen für den Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="88d15-211">The **Alias** attribute establishes an alternate name for the parameter.</span></span>
<span data-ttu-id="88d15-212">Es gibt keine Beschränkung für die Anzahl der Aliase, die Sie einem Parameter zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="88d15-212">There's no limit to the number of aliases that you can assign to a parameter.</span></span>

<span data-ttu-id="88d15-213">Das folgende Beispiel zeigt eine Parameter Deklaration, die die Aliase " **CN** " und " **MachineName** " dem obligatorischen **Computername** -Parameter hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="88d15-213">The following example shows a parameter declaration that adds the **CN** and **MachineName** aliases to the mandatory **ComputerName** parameter.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [Alias("CN","MachineName")]
    [String[]]
    $ComputerName
)
```

### <a name="supportswildcards-attribute"></a><span data-ttu-id="88d15-214">Supportswildcards-Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-214">SupportsWildcards attribute</span></span>

<span data-ttu-id="88d15-215">Das **supportswildcards** -Attribut wird verwendet, um anzugeben, dass der Parameter Platzhalter Werte annimmt.</span><span class="sxs-lookup"><span data-stu-id="88d15-215">The **SupportsWildcards** attribute is used to indicate that the parameter accepts wildcard values.</span></span> <span data-ttu-id="88d15-216">Das folgende Beispiel zeigt eine Parameter Deklaration für einen obligatorischen **path** -Parameter, der Platzhalter Werte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="88d15-216">The following example shows a parameter declaration for a mandatory **Path** parameter that supports wildcard values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [SupportsWildcards()]
    [String[]]
    $Path
)
```

<span data-ttu-id="88d15-217">Durch die Verwendung dieses Attributs wird die Platzhalter Unterstützung nicht automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="88d15-217">Using this attribute does not automatically enable wildcard support.</span></span> <span data-ttu-id="88d15-218">Der Cmdlet-Entwickler muss den Code implementieren, um die Platzhalter Eingabe zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="88d15-218">The cmdlet developer must implement the code to handle the wildcard input.</span></span> <span data-ttu-id="88d15-219">Welche Platzhalter unterstützt werden, hängt von der zugrunde liegenden API oder dem PowerShell-Anbieter ab.</span><span class="sxs-lookup"><span data-stu-id="88d15-219">The wildcards supported can vary according to the underlying API or PowerShell provider.</span></span> <span data-ttu-id="88d15-220">Weitere Informationen finden Sie unter [about_Wildcards](about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="88d15-220">For more information, see [about_Wildcards](about_Wildcards.md).</span></span>

### <a name="parameter-and-variable-validation-attributes"></a><span data-ttu-id="88d15-221">Parameter-und Variablen Validierungs Attribute</span><span class="sxs-lookup"><span data-stu-id="88d15-221">Parameter and variable validation attributes</span></span>

<span data-ttu-id="88d15-222">Validierungs Attribute leiten PowerShell ein, um die Parameterwerte zu testen, die Benutzer beim Aufrufen der erweiterten Funktion senden.</span><span class="sxs-lookup"><span data-stu-id="88d15-222">Validation attributes direct PowerShell to test the parameter values that users submit when they call the advanced function.</span></span> <span data-ttu-id="88d15-223">Wenn die Parameterwerte den Test nicht bestanden haben, wird ein Fehler generiert, und die Funktion wird nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="88d15-223">If the parameter values fail the test, an error is generated and the function isn't called.</span></span> <span data-ttu-id="88d15-224">Die Parameter Validierung wird nur auf die angegebene Eingabe angewendet, und alle anderen Werte wie Standardwerte werden nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="88d15-224">Parameter validation is only applied to the input provided and any other values like default values are not validated.</span></span>

<span data-ttu-id="88d15-225">Sie können auch die Validierungs Attribute verwenden, um die Werte einzuschränken, die Benutzer für Variablen angeben können.</span><span class="sxs-lookup"><span data-stu-id="88d15-225">You can also use the validation attributes to restrict the values that users can specify for variables.</span></span> <span data-ttu-id="88d15-226">Wenn Sie einen Typkonverter zusammen mit einem Validierungs Attribut verwenden, muss der Typkonverter vor dem-Attribut definiert werden.</span><span class="sxs-lookup"><span data-stu-id="88d15-226">When you use a type converter along with a validation attribute, the type converter has to be defined before the attribute.</span></span>

```powershell
[int32][AllowNull()] $number = 7
```

### <a name="allownull-validation-attribute"></a><span data-ttu-id="88d15-227">AllowNull-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-227">AllowNull validation attribute</span></span>

<span data-ttu-id="88d15-228">Das **AllowNull** -Attribut ermöglicht, dass der Wert eines obligatorischen Parameters ist `$null` .</span><span class="sxs-lookup"><span data-stu-id="88d15-228">The **AllowNull** attribute allows the value of a mandatory parameter to be `$null`.</span></span> <span data-ttu-id="88d15-229">Im folgenden Beispiel wird ein Hash Table **ComputerInfo** -Parameter deklariert, der einen **null** -Wert aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="88d15-229">The following example declares a hashtable **ComputerInfo** parameter that can have a **null** value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowNull()]
    [hashtable]
    $ComputerInfo
)
```

> [!NOTE]
> <span data-ttu-id="88d15-230">Das Attribut " **AllowNull** " funktioniert nicht, wenn der Typkonverter auf "String" festgelegt ist, da der Zeichen Folgentyp keinen NULL-Wert annimmt.</span><span class="sxs-lookup"><span data-stu-id="88d15-230">The **AllowNull** attribute doesn't work if the type converter is set to string as the string type will not accept a null value.</span></span> <span data-ttu-id="88d15-231">Sie können das Attribut " **attribuwemptystring** " für dieses Szenario verwenden.</span><span class="sxs-lookup"><span data-stu-id="88d15-231">You can use the **AllowEmptyString** attribute for this scenario.</span></span>

### <a name="allowemptystring-validation-attribute"></a><span data-ttu-id="88d15-232">Attribut "zuder Zuordnung von zuder Zuweisung"</span><span class="sxs-lookup"><span data-stu-id="88d15-232">AllowEmptyString validation attribute</span></span>

<span data-ttu-id="88d15-233">Das Attribut " **attribuwemptystring** " ermöglicht, dass der Wert eines obligatorischen Parameters eine leere Zeichenfolge ( `""` ) ist.</span><span class="sxs-lookup"><span data-stu-id="88d15-233">The **AllowEmptyString** attribute allows the value of a mandatory parameter to be an empty string (`""`).</span></span> <span data-ttu-id="88d15-234">Im folgenden Beispiel wird ein **Computername** -Parameter deklariert, der einen leeren Zeichen folgen Wert aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="88d15-234">The following example declares a **ComputerName** parameter that can have an empty string value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyString()]
    [String]
    $ComputerName
)
```

### <a name="allowemptycollection-validation-attribute"></a><span data-ttu-id="88d15-235">Zustellungs Attribut für Zustellungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-235">AllowEmptyCollection validation attribute</span></span>

<span data-ttu-id="88d15-236">Das Attribut " **attribuwemptycollection** " ermöglicht, dass der Wert eines obligatorischen Parameters eine leere Auflistung ist `@()` .</span><span class="sxs-lookup"><span data-stu-id="88d15-236">The **AllowEmptyCollection** attribute allows the value of a mandatory parameter to be an empty collection `@()`.</span></span> <span data-ttu-id="88d15-237">Im folgenden Beispiel wird ein **Computername** -Parameter deklariert, der einen leeren Sammlungs Wert aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="88d15-237">The following example declares a **ComputerName** parameter that can have an empty collection value.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [AllowEmptyCollection()]
    [String[]]
    $ComputerName
)
```

### <a name="validatecount-validation-attribute"></a><span data-ttu-id="88d15-238">Validatecount-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-238">ValidateCount validation attribute</span></span>

<span data-ttu-id="88d15-239">Das **validatecount** -Attribut gibt die minimale und maximale Anzahl von Parameterwerten an, die von einem Parameter akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="88d15-239">The **ValidateCount** attribute specifies the minimum and maximum number of parameter values that a parameter accepts.</span></span> <span data-ttu-id="88d15-240">PowerShell generiert einen Fehler, wenn die Anzahl der Parameterwerte im Befehl, der die Funktion aufruft, außerhalb dieses Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="88d15-240">PowerShell generates an error if the number of parameter values in the command that calls the function is outside that range.</span></span>

<span data-ttu-id="88d15-241">Die folgende Parameter Deklaration erstellt einen **Computername** -Parameter, der einen bis fünf Parameterwerte annimmt.</span><span class="sxs-lookup"><span data-stu-id="88d15-241">The following parameter declaration creates a **ComputerName** parameter that takes one to five parameter values.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateCount(1,5)]
    [String[]]
    $ComputerName
)
```

### <a name="validatelength-validation-attribute"></a><span data-ttu-id="88d15-242">ValidateLength-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-242">ValidateLength validation attribute</span></span>

<span data-ttu-id="88d15-243">Mit dem **validateLength** -Attribut werden die Mindest-und höchst Anzahl von Zeichen in einem Parameter-oder Variablen Wert angegeben.</span><span class="sxs-lookup"><span data-stu-id="88d15-243">The **ValidateLength** attribute specifies the minimum and maximum number of characters in a parameter or variable value.</span></span> <span data-ttu-id="88d15-244">PowerShell generiert einen Fehler, wenn die Länge eines Werts, der für einen Parameter oder eine Variable angegeben wurde, außerhalb des Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="88d15-244">PowerShell generates an error if the length of a value specified for a parameter or a variable is outside of the range.</span></span>

<span data-ttu-id="88d15-245">Im folgenden Beispiel muss jeder Computername ein bis zehn Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="88d15-245">In the following example, each computer name must have one to ten characters.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateLength(1,10)]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="88d15-246">Im folgenden Beispiel muss der Wert der `$number` -Variablen mindestens ein Zeichen lang sein und maximal zehn Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="88d15-246">In the following example, the value of the variable `$number` must be a minimum of one character in length, and a maximum of ten characters.</span></span>

```powershell
[Int32][ValidateLength(1,10)]$number = '01'
```

> [!NOTE]
> <span data-ttu-id="88d15-247">In diesem Beispiel wird der Wert von `01` in einfache Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="88d15-247">In this example, the value of `01` is wrapped in single quotes.</span></span> <span data-ttu-id="88d15-248">Das **validateLength** -Attribut akzeptiert keine Zahl, ohne in Anführungszeichen eingeschlossen zu werden.</span><span class="sxs-lookup"><span data-stu-id="88d15-248">The **ValidateLength** attribute won't accept a number without being wrapped in quotes.</span></span>

### <a name="validatepattern-validation-attribute"></a><span data-ttu-id="88d15-249">Validatepattern-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-249">ValidatePattern validation attribute</span></span>

<span data-ttu-id="88d15-250">Das **validatepattern** -Attribut gibt einen regulären Ausdruck an, der mit dem-Parameter oder dem Variablen Wert verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-250">The **ValidatePattern** attribute specifies a regular expression that's compared to the parameter or variable value.</span></span> <span data-ttu-id="88d15-251">PowerShell generiert einen Fehler, wenn der Wert nicht dem Muster für reguläre Ausdrücke entspricht.</span><span class="sxs-lookup"><span data-stu-id="88d15-251">PowerShell generates an error if the value doesn't match the regular expression pattern.</span></span>

<span data-ttu-id="88d15-252">Im folgenden Beispiel muss der Parameterwert eine vierstellige Zahl enthalten, und jede Ziffer muss eine Zahl von 0 bis 9 sein.</span><span class="sxs-lookup"><span data-stu-id="88d15-252">In the following example, the parameter value must contain a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [String[]]
    $ComputerName
)
```

<span data-ttu-id="88d15-253">Im folgenden Beispiel muss der Wert der `$number` -Variable genau eine vierstellige Zahl sein, und jede Ziffer muss eine Zahl von 0 bis 9 sein.</span><span class="sxs-lookup"><span data-stu-id="88d15-253">In the following example, the value of the variable `$number` must be exactly a four-digit number, and each digit must be a number zero to nine.</span></span>

```powershell
[Int32][ValidatePattern("^[0-9][0-9][0-9][0-9]$")]$number = 1111
```

### <a name="validaterange-validation-attribute"></a><span data-ttu-id="88d15-254">Validaterange-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-254">ValidateRange validation attribute</span></span>

<span data-ttu-id="88d15-255">Das **validaterange** -Attribut gibt einen numerischen Bereich für jeden Parameter oder Variablen Wert an.</span><span class="sxs-lookup"><span data-stu-id="88d15-255">The **ValidateRange** attribute specifies a numeric range for each parameter or variable value.</span></span> <span data-ttu-id="88d15-256">PowerShell generiert einen Fehler, wenn ein beliebiger Wert außerhalb dieses Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="88d15-256">PowerShell generates an error if any value is outside that range.</span></span> <span data-ttu-id="88d15-257">Im folgenden Beispiel muss der Wert des **Versuchs** -Parameters zwischen 0 und 10 liegen.</span><span class="sxs-lookup"><span data-stu-id="88d15-257">In the following example, the value of the **Attempts** parameter must be between zero and ten.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateRange(0,10)]
    [Int]
    $Attempts
)
```

<span data-ttu-id="88d15-258">Im folgenden Beispiel muss der Wert der `$number` -Variablen zwischen 0 und 10 liegen.</span><span class="sxs-lookup"><span data-stu-id="88d15-258">In the following example, the value of the variable `$number` must be between zero and ten.</span></span>

```powershell
[Int32][ValidateRange(0,10)]$number = 5
```

### <a name="validatescript-validation-attribute"></a><span data-ttu-id="88d15-259">Validatescript-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-259">ValidateScript validation attribute</span></span>

<span data-ttu-id="88d15-260">Das **validatescript** -Attribut gibt ein Skript an, das verwendet wird, um einen Parameter-oder Variablen Wert zu validieren.</span><span class="sxs-lookup"><span data-stu-id="88d15-260">The **ValidateScript** attribute specifies a script that is used to validate a parameter or variable value.</span></span> <span data-ttu-id="88d15-261">PowerShell übergibt den Wert an das Skript und generiert einen Fehler, wenn das Skript zurückgibt, `$false` oder wenn das Skript eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="88d15-261">PowerShell pipes the value to the script, and generates an error if the script returns `$false` or if the script throws an exception.</span></span>

<span data-ttu-id="88d15-262">Wenn Sie das **validatescript** -Attribut verwenden, wird der zu validierende Wert der `$_` Variablen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="88d15-262">When you use the **ValidateScript** attribute, the value that's being validated is mapped to the `$_` variable.</span></span> <span data-ttu-id="88d15-263">Sie können die- `$_` Variable verwenden, um auf den Wert im Skript zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="88d15-263">You can use the `$_` variable to refer to the value in the script.</span></span>

<span data-ttu-id="88d15-264">Im folgenden Beispiel muss der Wert des **eventdate** -Parameters größer oder gleich dem aktuellen Datum sein.</span><span class="sxs-lookup"><span data-stu-id="88d15-264">In the following example, the value of the **EventDate** parameter must be greater than or equal to the current date.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateScript({$_ -ge (Get-Date)})]
    [DateTime]
    $EventDate
)
```

<span data-ttu-id="88d15-265">Im folgenden Beispiel muss der Wert der-Variablen `$date` größer oder gleich dem aktuellen Datum und der aktuellen Uhrzeit sein.</span><span class="sxs-lookup"><span data-stu-id="88d15-265">In the following example, the value of the variable `$date` must be greater than or equal to the current date and time.</span></span>

```powershell
[DateTime][ValidateScript({$_ -ge (Get-Date)})]$date = (Get-Date)
```

> [!NOTE]
> <span data-ttu-id="88d15-266">Wenn Sie **validatescript** verwenden, können Sie keinen `$null` Wert an den-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="88d15-266">If you use **ValidateScript** , you cannot pass a `$null` value to the parameter.</span></span> <span data-ttu-id="88d15-267">Wenn Sie einen NULL-Wert übergeben, kann **validatescript** das Argument nicht validieren.</span><span class="sxs-lookup"><span data-stu-id="88d15-267">When you pass a null value **ValidateScript** can't validate the argument.</span></span>

### <a name="validateset-attribute"></a><span data-ttu-id="88d15-268">Validateset-Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-268">ValidateSet attribute</span></span>

<span data-ttu-id="88d15-269">Das **validateset** -Attribut gibt einen Satz gültiger Werte für einen Parameter oder eine Variable an und ermöglicht die Vervollständigung mit der Tab-Taste.</span><span class="sxs-lookup"><span data-stu-id="88d15-269">The **ValidateSet** attribute specifies a set of valid values for a parameter or variable and enables tab completion.</span></span> <span data-ttu-id="88d15-270">PowerShell generiert einen Fehler, wenn ein Parameter-oder Variablen Wert nicht mit einem Wert im Satz identisch ist.</span><span class="sxs-lookup"><span data-stu-id="88d15-270">PowerShell generates an error if a parameter or variable value doesn't match a value in the set.</span></span> <span data-ttu-id="88d15-271">Im folgenden Beispiel kann der Wert des **Detail** -Parameters nur "Low", "Average" oder "High" sein.</span><span class="sxs-lookup"><span data-stu-id="88d15-271">In the following example, the value of the **Detail** parameter can only be Low, Average, or High.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateSet("Low", "Average", "High")]
    [String[]]
    $Detail
)
```

<span data-ttu-id="88d15-272">Im folgenden Beispiel muss der Wert der Variablen entweder " `$flavor` Chocolate", "Strawberry" oder "Vanilla" lauten.</span><span class="sxs-lookup"><span data-stu-id="88d15-272">In the following example, the value of the variable `$flavor` must be either Chocolate, Strawberry, or Vanilla.</span></span>

```powershell
[ValidateSet("Chocolate", "Strawberry", "Vanilla")]
[String]$flavor = "Strawberry"
```

<span data-ttu-id="88d15-273">Die Validierung erfolgt immer dann, wenn diese Variable auch innerhalb des Skripts zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-273">The validation occurs whenever that variable is assigned even within the script.</span></span> <span data-ttu-id="88d15-274">Beispielsweise führt Folgendes zur Laufzeit zu einem Fehler:</span><span class="sxs-lookup"><span data-stu-id="88d15-274">For example, the following results in an error at runtime:</span></span>

```powershell
Param(
    [ValidateSet("hello", "world")]
    [String]$Message
)

$Message = "bye"
```

### <a name="validatenotnull-validation-attribute"></a><span data-ttu-id="88d15-275">Validatenotnull-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-275">ValidateNotNull validation attribute</span></span>

<span data-ttu-id="88d15-276">Das **validatenotnull** -Attribut gibt an, dass der Parameterwert nicht sein darf `$null` .</span><span class="sxs-lookup"><span data-stu-id="88d15-276">The **ValidateNotNull** attribute specifies that the parameter value can't be `$null`.</span></span> <span data-ttu-id="88d15-277">PowerShell generiert einen Fehler, wenn der Parameterwert ist `$null` .</span><span class="sxs-lookup"><span data-stu-id="88d15-277">PowerShell generates an error if the parameter value is `$null`.</span></span>

<span data-ttu-id="88d15-278">Das **validatenotnull** -Attribut ist so konzipiert, dass es verwendet wird, wenn der Parameter optional ist und der Typ nicht definiert ist oder über einen Typkonverter verfügt, der einen NULL-Wert wie **Object** nicht implizit konvertieren kann.</span><span class="sxs-lookup"><span data-stu-id="88d15-278">The **ValidateNotNull** attribute is designed to be used when the parameter is optional and the type is undefined or has a type converter that can't implicitly convert a null value like **object**.</span></span> <span data-ttu-id="88d15-279">Wenn Sie einen Typ angeben, der implizit einen NULL-Wert (z. b. eine **Zeichenfolge** ) konvertiert, wird der NULL-Wert in eine leere Zeichenfolge konvertiert, auch wenn das **validatenotnull** -Attribut verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-279">If you specify a type that that will implicitly convert a null value such as a **string** , the null value is converted to an empty string even when using the **ValidateNotNull** attribute.</span></span> <span data-ttu-id="88d15-280">Verwenden Sie für dieses Szenario **validatenotnullorempty** .</span><span class="sxs-lookup"><span data-stu-id="88d15-280">For this scenario use the **ValidateNotNullOrEmpty**</span></span>

<span data-ttu-id="88d15-281">Im folgenden Beispiel kann der Wert des **ID** -Parameters nicht sein `$null` .</span><span class="sxs-lookup"><span data-stu-id="88d15-281">In the following example, the value of the **ID** parameter can't be `$null`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [ValidateNotNull()]
    $ID
)
```

### <a name="validatenotnullorempty-validation-attribute"></a><span data-ttu-id="88d15-282">Validatenotnullorempty-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-282">ValidateNotNullOrEmpty validation attribute</span></span>

<span data-ttu-id="88d15-283">Das **validatenotnullorempty** -Attribut gibt an, dass der Parameterwert nicht sein darf `$null` und keine leere Zeichenfolge () sein kann `""` .</span><span class="sxs-lookup"><span data-stu-id="88d15-283">The **ValidateNotNullOrEmpty** attribute specifies that the parameter value can't be `$null` and can't be an empty string (`""`).</span></span> <span data-ttu-id="88d15-284">PowerShell generiert einen Fehler, wenn der Parameter in einem Funktions Aufrufsatz verwendet wird, der Wert `$null` jedoch, eine leere Zeichenfolge ( `""` ) oder ein leeres Array ist `@()` .</span><span class="sxs-lookup"><span data-stu-id="88d15-284">PowerShell generates an error if the parameter is used in a function call, but its value is `$null`, an empty string (`""`), or an empty array `@()`.</span></span>

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [ValidateNotNullOrEmpty()]
    [String[]]
    $UserName
)
```

### <a name="validatedrive-validation-attribute"></a><span data-ttu-id="88d15-285">Validatedrive-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-285">ValidateDrive validation attribute</span></span>

<span data-ttu-id="88d15-286">Das **validatedrive** -Attribut gibt an, dass der Parameterwert den Pfad darstellen muss, der nur auf zulässige Laufwerke verweist.</span><span class="sxs-lookup"><span data-stu-id="88d15-286">The **ValidateDrive** attribute specifies that the parameter value must represent the path, that's referring to allowed drives only.</span></span> <span data-ttu-id="88d15-287">PowerShell generiert einen Fehler, wenn der Parameterwert auf Laufwerke verweist, die nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="88d15-287">PowerShell generates an error if the parameter value refers to drives other than the allowed.</span></span> <span data-ttu-id="88d15-288">Das vorhanden sein des Pfads mit Ausnahme des Laufwerks selbst wird nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="88d15-288">Existence of the path, except for the drive itself, isn't verified.</span></span>

<span data-ttu-id="88d15-289">Wenn Sie einen relativen Pfad verwenden, muss das aktuelle Laufwerk in der Liste zulässiger Laufwerke enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="88d15-289">If you use relative path, the current drive must be in the allowed drive list.</span></span>

```powershell
Param(
    [ValidateDrive("C", "D", "Variable", "Function")]
    [String]$Path
)
```

### <a name="validateuserdrive-validation-attribute"></a><span data-ttu-id="88d15-290">Validateuserdrive-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-290">ValidateUserDrive validation attribute</span></span>

<span data-ttu-id="88d15-291">Das **validateuserdrive** -Attribut gibt an, dass der Parameterwert den Pfad darstellen muss, der sich auf das `User` Laufwerk bezieht.</span><span class="sxs-lookup"><span data-stu-id="88d15-291">The **ValidateUserDrive** attribute specifies that the parameter value must represent the path, that is referring to `User` drive.</span></span> <span data-ttu-id="88d15-292">PowerShell generiert einen Fehler, wenn sich der Pfad auf ein anderes Laufwerk bezieht.</span><span class="sxs-lookup"><span data-stu-id="88d15-292">PowerShell generates an error if the path refers to a different drive.</span></span> <span data-ttu-id="88d15-293">Das Validierungs Attribut testet nur, ob der Laufwerks Teil des Pfads vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="88d15-293">The validation attribute only tests for the existence of the drive portion of the path.</span></span>

<span data-ttu-id="88d15-294">Wenn Sie einen relativen Pfad verwenden, muss das aktuelle Laufwerk sein `User` .</span><span class="sxs-lookup"><span data-stu-id="88d15-294">If you use relative path, the current drive must be `User`.</span></span>

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

<span data-ttu-id="88d15-295">Sie können das `User` Laufwerk in Just Enough Administration (Jea)-Sitzungs Konfigurationen definieren.</span><span class="sxs-lookup"><span data-stu-id="88d15-295">You can define `User` drive in Just Enough Administration (JEA) session configurations.</span></span> <span data-ttu-id="88d15-296">In diesem Beispiel erstellen wir das Laufwerk User:.</span><span class="sxs-lookup"><span data-stu-id="88d15-296">For this example, we create the User: drive.</span></span>

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

### <a name="validatetrusteddata-validation-attribute"></a><span data-ttu-id="88d15-297">Validatetrusteddata-Validierungs Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-297">ValidateTrustedData validation attribute</span></span>

<span data-ttu-id="88d15-298">Dieses Attribut wurde in PowerShell 6.1.1 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="88d15-298">This attribute was added in PowerShell 6.1.1.</span></span>

<span data-ttu-id="88d15-299">Zu diesem Zeitpunkt wird das-Attribut intern von PowerShell selbst verwendet und ist nicht für die externe Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="88d15-299">At this time, the attribute is used internally by PowerShell itself and is not intended for external usage.</span></span>

## <a name="dynamic-parameters"></a><span data-ttu-id="88d15-300">Dynamische Parameter</span><span class="sxs-lookup"><span data-stu-id="88d15-300">Dynamic parameters</span></span>

<span data-ttu-id="88d15-301">Dynamische Parameter sind Parameter eines Cmdlets, einer Funktion oder eines Skripts, die nur unter bestimmten Bedingungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="88d15-301">Dynamic parameters are parameters of a cmdlet, function, or script that are available only under certain conditions.</span></span>

<span data-ttu-id="88d15-302">Beispielsweise verfügen mehrere Anbieter-Cmdlets über Parameter, die nur verfügbar sind, wenn das Cmdlet im Anbieter Laufwerk oder in einem bestimmten Pfad des Anbieter Laufwerks verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-302">For example, several provider cmdlets have parameters that are available only when the cmdlet is used in the provider drive, or in a particular path of the provider drive.</span></span> <span data-ttu-id="88d15-303">Der **Encoding** -Parameter ist beispielsweise `Add-Content` `Get-Content` nur in den-,-und `Set-Content` -Cmdlets verfügbar, wenn er in einem Dateisystem Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-303">For example, the **Encoding** parameter is available on the `Add-Content`, `Get-Content`, and `Set-Content` cmdlets only when it's used in a file system drive.</span></span>

<span data-ttu-id="88d15-304">Sie können auch einen Parameter erstellen, der nur angezeigt wird, wenn ein anderer Parameter im Funktionsbefehl verwendet wird oder wenn ein anderer Parameter einen bestimmten Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="88d15-304">You can also create a parameter that appears only when another parameter is used in the function command or when another parameter has a certain value.</span></span>

<span data-ttu-id="88d15-305">Dynamische Parameter können nützlich sein, Sie sollten jedoch nur bei Bedarf verwendet werden, da Sie für Benutzer schwer zu erkennen sind.</span><span class="sxs-lookup"><span data-stu-id="88d15-305">Dynamic parameters can be useful, but use them only when necessary, because they can be difficult for users to discover.</span></span> <span data-ttu-id="88d15-306">Um einen dynamischen Parameter zu finden, muss sich der Benutzer im Anbieter Pfad befinden, den Argument **List** -Parameter des `Get-Command` Cmdlets verwenden oder den **path** -Parameter von verwenden `Get-Help` .</span><span class="sxs-lookup"><span data-stu-id="88d15-306">To find a dynamic parameter, the user must be in the provider path, use the **ArgumentList** parameter of the `Get-Command` cmdlet, or use the **Path** parameter of `Get-Help`.</span></span>

<span data-ttu-id="88d15-307">Um einen dynamischen Parameter für eine Funktion oder ein Skript zu erstellen, verwenden Sie das- `DynamicParam` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="88d15-307">To create a dynamic parameter for a function or script, use the `DynamicParam` keyword.</span></span>

<span data-ttu-id="88d15-308">Die Syntax ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="88d15-308">The syntax is as follows:</span></span>

`DynamicParam {<statement-list>}`

<span data-ttu-id="88d15-309">Verwenden Sie in der Anweisungs Liste eine- `If` Anweisung, um die Bedingungen anzugeben, unter denen der-Parameter in der-Funktion verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="88d15-309">In the statement list, use an `If` statement to specify the conditions under which the parameter is available in the function.</span></span>

<span data-ttu-id="88d15-310">Verwenden `New-Object` Sie das Cmdlet, um ein **System. Management. Automation. runtimedefinedparameter** -Objekt zu erstellen, das den Parameter darstellt, und geben Sie seinen Namen an.</span><span class="sxs-lookup"><span data-stu-id="88d15-310">Use the `New-Object` cmdlet to create a **System.Management.Automation.RuntimeDefinedParameter** object to represent the parameter and specify its name.</span></span>

<span data-ttu-id="88d15-311">Sie können einen `New-Object` Befehl verwenden, um ein **System. Management. Automation. Parameterattribute** -Objekt zu erstellen, das Attribute des Parameters darstellt, wie z. b. **obligatorisch** , **Position** oder **valuefrompipeline** oder den Parametersatz.</span><span class="sxs-lookup"><span data-stu-id="88d15-311">You can use a `New-Object` command to create a **System.Management.Automation.ParameterAttribute** object to represent attributes of the parameter, such as **Mandatory** , **Position** , or **ValueFromPipeline** or its parameter set.</span></span>

<span data-ttu-id="88d15-312">Das folgende Beispiel zeigt eine Beispiel Funktion mit Standardparametern namens " **Name** " und " **path** " und einen optionalen dynamischen Parameter namens **DP1**.</span><span class="sxs-lookup"><span data-stu-id="88d15-312">The following example shows a sample function with standard parameters named **Name** and **Path** , and an optional dynamic parameter named **DP1**.</span></span> <span data-ttu-id="88d15-313">Der **DP1** -Parameter ist im `PSet1` Parametersatz und weist den Typ auf `Int32` .</span><span class="sxs-lookup"><span data-stu-id="88d15-313">The **DP1** parameter is in the `PSet1` parameter set and has a type of `Int32`.</span></span>
<span data-ttu-id="88d15-314">Der **DP1** -Parameter ist nur in der- `Get-Sample` Funktion verfügbar, wenn der Wert des **path** -Parameters mit beginnt `HKLM:` , was darauf hinweist, dass er im `HKEY_LOCAL_MACHINE` Registrierungs Laufwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-314">The **DP1** parameter is available in the `Get-Sample` function only when the value of the **Path** parameter starts with `HKLM:`, indicating that it's being used in the `HKEY_LOCAL_MACHINE` registry drive.</span></span>

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

<span data-ttu-id="88d15-315">Weitere Informationen finden Sie unter [runtimedefinedparameter](/dotnet/api/system.management.automation.runtimedefinedparameter).</span><span class="sxs-lookup"><span data-stu-id="88d15-315">For more information, see [RuntimeDefinedParameter](/dotnet/api/system.management.automation.runtimedefinedparameter).</span></span>

## <a name="switch-parameters"></a><span data-ttu-id="88d15-316">Switch-Parameter</span><span class="sxs-lookup"><span data-stu-id="88d15-316">Switch parameters</span></span>

<span data-ttu-id="88d15-317">Switch-Parameter sind Parameter ohne Parameterwert.</span><span class="sxs-lookup"><span data-stu-id="88d15-317">Switch parameters are parameters with no parameter value.</span></span> <span data-ttu-id="88d15-318">Sie sind nur wirksam, wenn Sie verwendet werden und nur einen Effekt haben.</span><span class="sxs-lookup"><span data-stu-id="88d15-318">They're effective only when they're used and have only one effect.</span></span>

<span data-ttu-id="88d15-319">Beispielsweise ist der **NoProfile** -Parameter von **powershell.exe** ein Switch-Parameter.</span><span class="sxs-lookup"><span data-stu-id="88d15-319">For example, the **NoProfile** parameter of **powershell.exe** is a switch parameter.</span></span>

<span data-ttu-id="88d15-320">Um einen Switch-Parameter in einer Funktion zu erstellen, geben Sie den `Switch` Typ in der Parameterdefinition an.</span><span class="sxs-lookup"><span data-stu-id="88d15-320">To create a switch parameter in a function, specify the `Switch` type in the parameter definition.</span></span>

<span data-ttu-id="88d15-321">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="88d15-321">For example:</span></span>

```powershell
Param([Switch]<ParameterName>)
```

<span data-ttu-id="88d15-322">Oder Sie können eine andere Methode verwenden:</span><span class="sxs-lookup"><span data-stu-id="88d15-322">Or, you can use an another method:</span></span>

```powershell
Param(
    [Parameter(Mandatory=$false)]
    [Switch]
    $<ParameterName>
)
```

<span data-ttu-id="88d15-323">Switch-Parameter sind einfach zu verwenden und werden gegenüber booleschen Parametern bevorzugt, die eine schwierigere Syntax aufweisen.</span><span class="sxs-lookup"><span data-stu-id="88d15-323">Switch parameters are easy to use and are preferred over Boolean parameters, which have a more difficult syntax.</span></span>

<span data-ttu-id="88d15-324">Um z. b. einen Switch-Parameter zu verwenden, gibt der Benutzer den-Parameter in den Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="88d15-324">For example, to use a switch parameter, the user types the parameter in the command.</span></span>

`-IncludeAll`

<span data-ttu-id="88d15-325">Um einen booleschen Parameter zu verwenden, gibt der Benutzer den-Parameter und einen booleschen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="88d15-325">To use a Boolean parameter, the user types the parameter and a Boolean value.</span></span>

`-IncludeAll:$true`

<span data-ttu-id="88d15-326">Wählen Sie beim Erstellen von Switch-Parametern den Parameternamen sorgfältig aus.</span><span class="sxs-lookup"><span data-stu-id="88d15-326">When creating switch parameters, choose the parameter name carefully.</span></span> <span data-ttu-id="88d15-327">Stellen Sie sicher, dass der Parameter Name die Auswirkung des Parameters an den Benutzer übermittelt.</span><span class="sxs-lookup"><span data-stu-id="88d15-327">Be sure that the parameter name communicates the effect of the parameter to the user.</span></span>
<span data-ttu-id="88d15-328">Vermeiden Sie mehrdeutige Begriffe, wie z. b. **Filter** oder **Maximum** , die impliziert, dass ein Wert erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="88d15-328">Avoid ambiguous terms, such as **Filter** or **Maximum** that might imply a value is required.</span></span>

## <a name="argumentcompleter-attribute"></a><span data-ttu-id="88d15-329">Argumentcompleter-Attribut</span><span class="sxs-lookup"><span data-stu-id="88d15-329">ArgumentCompleter attribute</span></span>

<span data-ttu-id="88d15-330">Mithilfe des **argumentcompleter** -Attributs können Sie einem bestimmten Parameter Tabstopp-Vervollständigungs Werte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="88d15-330">The **ArgumentCompleter** attribute allows you to add tab completion values to a specific parameter.</span></span> <span data-ttu-id="88d15-331">Für jeden Parameter, der die Vervollständigung der Tab-Taste erfordert, muss ein Argument **Completer** -Attribut definiert werden</span><span class="sxs-lookup"><span data-stu-id="88d15-331">An **ArgumentCompleter** attribute must be defined for each parameter that needs tab completion.</span></span> <span data-ttu-id="88d15-332">Ähnlich wie bei **DynamicParameters** werden die verfügbaren Werte zur Laufzeit berechnet, wenn der Benutzer die <kbd>Tab</kbd> -Taste nach dem Parameternamen drückt.</span><span class="sxs-lookup"><span data-stu-id="88d15-332">Similar to **DynamicParameters** , the available values are calculated at runtime when the user presses <kbd>Tab</kbd> after the parameter name.</span></span>

<span data-ttu-id="88d15-333">Zum Hinzufügen eines **argumentcompleter** -Attributs müssen Sie einen Skriptblock definieren, der die Werte bestimmt.</span><span class="sxs-lookup"><span data-stu-id="88d15-333">To add an **ArgumentCompleter** attribute, you need to define a script block that determines the values.</span></span> <span data-ttu-id="88d15-334">Der Skriptblock muss die folgenden Parameter in der unten angegebenen Reihenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="88d15-334">The script block must take the following parameters in the order specified below.</span></span> <span data-ttu-id="88d15-335">Die Namen des Parameters sind nicht von Bedeutung, da die Werte Positions bedingt bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="88d15-335">The parameter's names don't matter as the values are provided positionally.</span></span>

<span data-ttu-id="88d15-336">Die Syntax ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="88d15-336">The syntax is as follows:</span></span>

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

### <a name="argumentcompleter-script-block"></a><span data-ttu-id="88d15-337">Argumentcompleter-Skriptblock</span><span class="sxs-lookup"><span data-stu-id="88d15-337">ArgumentCompleter script block</span></span>

<span data-ttu-id="88d15-338">Die Skriptblock Parameter werden auf die folgenden Werte festgelegt:</span><span class="sxs-lookup"><span data-stu-id="88d15-338">The script block parameters are set to the following values:</span></span>

- <span data-ttu-id="88d15-339">`$commandName` (Position 0): dieser Parameter wird auf den Namen des Befehls festgelegt, für den der Skriptblock die Vervollständigung mit der Tab-Taste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="88d15-339">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="88d15-340">`$parameterName` (Position 1): dieser Parameter ist auf den Parameter festgelegt, dessen Wert die Vervollständigung der Tab-Taste erfordert.</span><span class="sxs-lookup"><span data-stu-id="88d15-340">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="88d15-341">`$wordToComplete` (Position 2): dieser Parameter ist auf den Wert festgelegt, den der Benutzer vor dem Drücken der <kbd>Tab</kbd>-Taste angegeben hat. Der Skriptblock sollte diesen Wert verwenden, um die Vervollständigungs Werte der Registerkarte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="88d15-341">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="88d15-342">`$commandAst` (Position 3): dieser Parameter ist für die aktuelle Eingabezeile auf die abstrakte Syntax Struktur (AST, Abstract Syntax Tree) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="88d15-342">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="88d15-343">Weitere Informationen finden Sie unter [AST-Klasse](/dotnet/api/system.management.automation.language.ast).</span><span class="sxs-lookup"><span data-stu-id="88d15-343">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="88d15-344">`$fakeBoundParameters` (Position 4): dieser Parameter wird auf eine Hash Tabelle festgelegt, die den `$PSBoundParameters` für das Cmdlet enthält, bevor der Benutzer die <kbd>Tab</kbd>-Taste gedrückt hat. Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="88d15-344">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="88d15-345">Der **argumentcompleter** -Skriptblock muss die Registrierung der Werte mithilfe der Pipeline, wie `ForEach-Object` z `Where-Object` . b., oder einer anderen geeigneten Methode, aufheben.</span><span class="sxs-lookup"><span data-stu-id="88d15-345">The **ArgumentCompleter** script block must unroll the values using the pipeline, such as `ForEach-Object`, `Where-Object`, or another suitable method.</span></span>
<span data-ttu-id="88d15-346">Das Zurückgeben eines Arrays von Werten bewirkt, dass PowerShell das gesamte Array als **einen** Vervollständigungs Wert mit der Tab-Taste behandelt.</span><span class="sxs-lookup"><span data-stu-id="88d15-346">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="88d15-347">Im folgenden Beispiel wird dem **value** -Parameter die Befehlszeilen Vervollständigung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="88d15-347">The following example adds tab completion to the **Value** parameter.</span></span> <span data-ttu-id="88d15-348">Wenn nur der **value** -Parameter angegeben wird, werden alle möglichen Werte oder Argumente für **value** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d15-348">If only the **Value** parameter is specified, all possible values, or arguments, for **Value** are displayed.</span></span> <span data-ttu-id="88d15-349">Wenn der **Typparameter** angegeben wird, zeigt der **value** -Parameter nur die möglichen Werte für diesen Typ an.</span><span class="sxs-lookup"><span data-stu-id="88d15-349">When the **Type** parameter is specified, the **Value** parameter only displays the possible values for that type.</span></span>

<span data-ttu-id="88d15-350">Außerdem stellt der- `-like` Operator sicher, dass, wenn der Benutzer den folgenden Befehl eingibt und die <kbd>Tab</kbd> -Taste verwendet, nur **Apple** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="88d15-350">In addition, the `-like` operator ensures that if the user types the following command and uses <kbd>Tab</kbd> completion, only **Apple** is returned.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="88d15-351">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="88d15-351">See also</span></span>

[<span data-ttu-id="88d15-352">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="88d15-352">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="88d15-353">about_Functions</span><span class="sxs-lookup"><span data-stu-id="88d15-353">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="88d15-354">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="88d15-354">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="88d15-355">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="88d15-355">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="88d15-356">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="88d15-356">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="88d15-357">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="88d15-357">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
