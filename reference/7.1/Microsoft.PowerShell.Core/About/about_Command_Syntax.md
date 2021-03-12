---
description: Beschreibt die Syntax Diagramme, die in PowerShell verwendet werden.
Locale: en-US
ms.date: 06/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Syntax
ms.openlocfilehash: 60bd9e8f29680d20be803c615f2e93572b4da12f
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195349"
---
# <a name="about-command-syntax"></a><span data-ttu-id="3aaa6-103">Informationen zur Befehls Syntax</span><span class="sxs-lookup"><span data-stu-id="3aaa6-103">About Command Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="3aaa6-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3aaa6-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="3aaa6-105">Beschreibt die Syntax Diagramme, die in PowerShell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-105">Describes the syntax diagrams that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="3aaa6-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3aaa6-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="3aaa6-107">Die Cmdlets " [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) " und " [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) " zeigen Syntax Diagramme an, die Ihnen helfen, Befehle korrekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-107">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlets display syntax diagrams to help you construct commands correctly.</span></span> <span data-ttu-id="3aaa6-108">In diesem Thema wird erläutert, wie die Syntax Diagramme interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-108">This topic explains how to interpret the syntax diagrams.</span></span>

## <a name="syntax-diagrams"></a><span data-ttu-id="3aaa6-109">Syntax Diagramme</span><span class="sxs-lookup"><span data-stu-id="3aaa6-109">SYNTAX DIAGRAMS</span></span>

<span data-ttu-id="3aaa6-110">Jeder Absatz eines Befehlssyntax Diagramms stellt ein gültiges Formular des Befehls dar.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-110">Each paragraph in a command syntax diagram represents a valid form of the command.</span></span>

<span data-ttu-id="3aaa6-111">Um einen Befehl zu erstellen, befolgen Sie das Syntax Diagramm von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-111">To construct a command, follow the syntax diagram from left to right.</span></span> <span data-ttu-id="3aaa6-112">Wählen Sie unter den optionalen Parametern aus, und geben Sie Werte für die Platzhalter an.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-112">Select from among the optional parameters and provide values for the placeholders.</span></span>

<span data-ttu-id="3aaa6-113">PowerShell verwendet die folgende Notation für Syntax Diagramme.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-113">PowerShell uses the following notation for syntax diagrams.</span></span>

```powershell
<command-name> -<Required Parameter Name> <Required Parameter Value>
[-<Optional Parameter Name> <Optional Parameter Value>]
[-<Optional Switch Parameters>]
[-<Optional Parameter Name>] <Required Parameter Value>
```

<span data-ttu-id="3aaa6-114">Im folgenden finden Sie die Syntax für das Cmdlet [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) .</span><span class="sxs-lookup"><span data-stu-id="3aaa6-114">The following is the syntax for the [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) cmdlet.</span></span>

```powershell
New-Alias [-Name] <string> [-Value] <string> [-Description <string>]
[-Force] [-Option {None | ReadOnly | Constant | Private | AllScope}]
[-PassThru] [-Scope <string>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

<span data-ttu-id="3aaa6-115">Die Syntax wird zur besseren Lesbarkeit groß geschrieben, aber bei PowerShell wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-115">The syntax is capitalized for readability, but PowerShell is case-insensitive.</span></span>

<span data-ttu-id="3aaa6-116">Das Syntax Diagramm enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-116">The syntax diagram has the following elements.</span></span>

## <a name="command-name"></a><span data-ttu-id="3aaa6-117">Befehlsname</span><span class="sxs-lookup"><span data-stu-id="3aaa6-117">Command name</span></span>

<span data-ttu-id="3aaa6-118">Befehle beginnen immer mit einem Befehlsnamen, z `New-Alias` . b..</span><span class="sxs-lookup"><span data-stu-id="3aaa6-118">Commands always begin with a command name, such as `New-Alias`.</span></span> <span data-ttu-id="3aaa6-119">Geben Sie den Befehlsnamen oder seinen Alias ein, z. b. "GCM" für `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="3aaa6-119">Type the command name or its alias, such a "gcm" for `Get-Command`.</span></span>

## <a name="parameters"></a><span data-ttu-id="3aaa6-120">Parameter</span><span class="sxs-lookup"><span data-stu-id="3aaa6-120">Parameters</span></span>

<span data-ttu-id="3aaa6-121">Die Parameter eines Befehls sind Optionen, mit denen bestimmt wird, was der Befehl bewirkt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-121">The parameters of a command are options that determine what the command does.</span></span>
<span data-ttu-id="3aaa6-122">Einige Parameter akzeptieren einen "Wert", bei dem es sich um eine Benutzereingabe für den Befehl handelt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-122">Some parameters take a "value" which is user input to the command.</span></span>

<span data-ttu-id="3aaa6-123">Der- `Get-Help` Befehl verfügt z. b. über einen **Name** -Parameter, mit dem Sie den Namen des Themas angeben können, für das die Hilfe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-123">For example, the `Get-Help` command has a **Name** parameter that lets you specify the name of the topic for which help is displayed.</span></span> <span data-ttu-id="3aaa6-124">Der Themenname ist der Wert des **Name** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-124">The topic name is the value of the **Name** parameter.</span></span>

<span data-ttu-id="3aaa6-125">In einem PowerShell-Befehl beginnen Parameternamen immer mit einem Bindestrich.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-125">In a PowerShell command, parameter names always begin with a hyphen.</span></span>
<span data-ttu-id="3aaa6-126">Der Bindestrich weist PowerShell an, dass das Element im Befehl ein Parameter Name ist.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-126">The hyphen tells PowerShell that the item in the command is a parameter name.</span></span>

<span data-ttu-id="3aaa6-127">Wenn Sie z. b. den Name-Parameter von verwenden möchten `New-Alias` , geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-127">For example, to use the Name parameter of `New-Alias`, you type the following:</span></span>

```powershell
-Name
```

<span data-ttu-id="3aaa6-128">Parameter können obligatorisch oder optional sein.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-128">Parameters can be mandatory or optional.</span></span> <span data-ttu-id="3aaa6-129">In einem Syntax Diagramm werden optionale Elemente in eckige Klammern eingeschlossen `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="3aaa6-129">In a syntax diagram, optional items are enclosed in brackets `[ ]`.</span></span>

<span data-ttu-id="3aaa6-130">Weitere Informationen zu Parametern finden Sie unter [about_Parameters](about_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="3aaa6-130">For more information about parameters, see [about_Parameters](about_Parameters.md).</span></span>

## <a name="parameter-values"></a><span data-ttu-id="3aaa6-131">Parameterwerte</span><span class="sxs-lookup"><span data-stu-id="3aaa6-131">Parameter Values</span></span>

<span data-ttu-id="3aaa6-132">Ein Parameterwert ist die Eingabe, die der-Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-132">A parameter value is the input that the parameter takes.</span></span> <span data-ttu-id="3aaa6-133">Da Windows PowerShell auf dem Microsoft .NET Framework basiert, werden Parameterwerte im Syntax Diagramm durch ihren .NET-Typ dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-133">Because Windows PowerShell is based on the Microsoft .NET Framework, parameter values are represented in the syntax diagram by their .NET type.</span></span>

<span data-ttu-id="3aaa6-134">Beispielsweise übernimmt der Name-Parameter von den `Get-Help` Wert "String", bei dem es sich um eine Text Zeichenfolge handelt, z. b. ein einzelnes Wort oder mehrere Wörter, die in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-134">For example, the Name parameter of `Get-Help` takes a "String" value, which is a text string, such as a single word or multiple words enclosed in quotation marks.</span></span>

```powershell
[-Name] <string>
```

<span data-ttu-id="3aaa6-135">Der .NET-Typ eines Parameter Werts wird in spitzen Klammern eingeschlossen `< >` , um anzugeben, dass es sich um einen Platzhalter für einen Wert handelt, nicht um ein Literalzeichen, das Sie in einen Befehl eingeben.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-135">The .NET type of a parameter value is enclosed in angle brackets `< >` to indicate that it is placeholder for a value and not a literal that you type in a command.</span></span>

<span data-ttu-id="3aaa6-136">Um den-Parameter zu verwenden, ersetzen Sie den .net-Typplatzhalter durch ein-Objekt, das über den angegebenen .NET-Typ verfügt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-136">To use the parameter, replace the .NET type placeholder with an object that has the specified .NET type.</span></span>

<span data-ttu-id="3aaa6-137">Wenn Sie z. b. den **Name** -Parameter verwenden möchten, geben Sie "-Name" gefolgt von einer Zeichenfolge ein, z. b. Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-137">For example, to use the **Name** parameter, type "-Name" followed by a string, such as the following:</span></span>

```powershell
-Name MyAlias
```

## <a name="parameters-with-no-values"></a><span data-ttu-id="3aaa6-138">Parameter ohne Werte</span><span class="sxs-lookup"><span data-stu-id="3aaa6-138">Parameters with no values</span></span>

<span data-ttu-id="3aaa6-139">Einige Parameter akzeptieren keine Eingaben, sodass Sie nicht über einen Parameterwert verfügen.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-139">Some parameters do not accept input, so they do not have a parameter value.</span></span>
<span data-ttu-id="3aaa6-140">Parameter ohne Werte werden als "Switch-Parameter" bezeichnet, da Sie wie on/off-Switches funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-140">Parameters without values are called "switch parameters" because they work like on/off switches.</span></span> <span data-ttu-id="3aaa6-141">Sie fügen Sie ein (on), oder Sie können Sie (aus) über einen Befehl weglassen.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-141">You include them (on) or you omit them (off) from a command.</span></span>

<span data-ttu-id="3aaa6-142">Um einen Switch-Parameter zu verwenden, geben Sie einfach den Parameternamen ein, dem ein Bindestrich vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-142">To use a switch parameter, just type the parameter name, preceded by a hyphen.</span></span>

<span data-ttu-id="3aaa6-143">Wenn Sie z. b. den **WhatIf** -Parameter des `New-Alias` Cmdlets verwenden möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-143">For example, to use the **WhatIf** parameter of the `New-Alias` cmdlet, type the following:</span></span>

```powershell
-WhatIf
```

## <a name="parameter-sets"></a><span data-ttu-id="3aaa6-144">Parameter Sätze</span><span class="sxs-lookup"><span data-stu-id="3aaa6-144">Parameter Sets</span></span>

<span data-ttu-id="3aaa6-145">Die Parameter eines Befehls werden in Parametersätzen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-145">The parameters of a command are listed in parameter sets.</span></span> <span data-ttu-id="3aaa6-146">Parameter Sätze sehen wie die Absätze eines Syntax Diagramms aus.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-146">Parameter sets look like the paragraphs of a syntax diagram.</span></span>

<span data-ttu-id="3aaa6-147">Für das `New-Alias` Cmdlet ist ein Parametersatz festgelegt, aber viele Cmdlets verfügen über mehrere Parametersätze.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-147">The `New-Alias` cmdlet has one parameter set, but many cmdlets have multiple parameter sets.</span></span> <span data-ttu-id="3aaa6-148">Einige der Cmdlet-Parameter sind für einen Parametersatz eindeutig, und andere sind in mehreren Parametersätzen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-148">Some of the cmdlet parameters are unique to a parameter set, and others appear in multiple parameter sets.</span></span> <span data-ttu-id="3aaa6-149">Jeder Parametersatz stellt das Format eines gültigen Befehls dar.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-149">Each parameter set represents the format of a valid command.</span></span> <span data-ttu-id="3aaa6-150">Ein Parametersatz enthält nur Parameter, die in einem Befehl verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-150">A parameter set includes only parameters that can be used together in a command.</span></span> <span data-ttu-id="3aaa6-151">Wenn Parameter nicht im selben Befehl verwendet werden können, werden Sie in separaten Parametersätzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-151">If parameters cannot be used in the same command, they appear in separate parameter sets.</span></span>

<span data-ttu-id="3aaa6-152">Beispielsweise verfügt das [Get-Random-](xref:Microsoft.PowerShell.Utility.Get-Random) Cmdlet über die folgenden Parametersätze:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-152">For example, the [Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random) cmdlet has the following parameter sets:</span></span>

```powershell
Get-Random [[-Maximum] <Object>] [-Minimum <Object>] [-SetSeed <int>]
[<CommonParameters>]

Get-Random [-InputObject] <Object[]> [-Count <int>] [-SetSeed <int>]
[<CommonParameters>]
```

<span data-ttu-id="3aaa6-153">Der erste Parametersatz, der eine Zufallszahl zurückgibt, hat den **minimalen** und den **maximalen** Parameter.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-153">The first parameter set, which returns a random number, has the **Minimum** and **Maximum** parameters.</span></span> <span data-ttu-id="3aaa6-154">Der zweite Parametersatz, der ein zufällig ausgewähltes Objekt aus einem Satz von Objekten zurückgibt, enthält die Parameter **Inputobject** und **count** .</span><span class="sxs-lookup"><span data-stu-id="3aaa6-154">The second parameter set, which returns a randomly selected object from a set of objects, includes the **InputObject** and **Count** parameters.</span></span> <span data-ttu-id="3aaa6-155">Beide Parametersätze verfügen über den **setseed** -Parameter und die allgemeinen Parameter.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-155">Both parameter sets have the **SetSeed** parameter and the common parameters.</span></span>

<span data-ttu-id="3aaa6-156">Diese Parametersätze geben an, dass Sie die **Inputobject** -und **count** -Parameter im gleichen Befehl verwenden können, aber Sie können die Parameter " **Maximum** " und " **count** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-156">These parameter sets indicate that you can use the **InputObject** and **Count** parameters in the same command, but you cannot use the **Maximum** and **Count** parameters in the same command.</span></span>

<span data-ttu-id="3aaa6-157">Sie geben den Parametersatz an, den Sie verwenden möchten, indem Sie die Parameter in diesem Parametersatz verwenden.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-157">You indicate which parameter set you want to use by using the parameters in that parameter set.</span></span>

<span data-ttu-id="3aaa6-158">Allerdings verfügt jedes Cmdlet auch über einen Standardparameter Satz.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-158">However, every cmdlet also has a default parameter set.</span></span> <span data-ttu-id="3aaa6-159">Der Standardparameter Satz wird verwendet, wenn Sie keine Parameter angeben, die für einen Parametersatz eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-159">The default parameter set is used when you do not specify parameters that are unique to a parameter set.</span></span> <span data-ttu-id="3aaa6-160">Wenn Sie z. b. `Get-Random` ohne Parameter verwenden, geht Windows PowerShell davon aus, dass Sie den **Number** -Parametersatz verwenden und eine Zufallszahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-160">For example, if you use `Get-Random` without parameters, Windows PowerShell assumes that you are using the **Number** parameter set and it returns a random number.</span></span>

<span data-ttu-id="3aaa6-161">In jedem Parametersatz werden die Parameter in der Positions Reihenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-161">In each parameter set, the parameters appear in position order.</span></span> <span data-ttu-id="3aaa6-162">Die Reihenfolge von Parametern in einem Befehl ist nur wichtig, wenn Sie die optionalen Parameternamen weglassen.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-162">The order of parameters in a command matters only when you omit the optional parameter names.</span></span> <span data-ttu-id="3aaa6-163">Wenn Parameternamen ausgelassen werden, werden den Parametern von PowerShell Werte nach Position und Typ zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-163">When parameter names are omitted, PowerShell assigns values to parameters by position and type.</span></span> <span data-ttu-id="3aaa6-164">Weitere Informationen zur Parameter Position finden Sie unter `about_Parameters` .</span><span class="sxs-lookup"><span data-stu-id="3aaa6-164">For more information about parameter position, see `about_Parameters`.</span></span>

## <a name="symbols-in-syntax-diagrams"></a><span data-ttu-id="3aaa6-165">Symbole in Syntax Diagrammen</span><span class="sxs-lookup"><span data-stu-id="3aaa6-165">Symbols in Syntax Diagrams</span></span>

<span data-ttu-id="3aaa6-166">Das Syntax Diagramm listet den Befehlsnamen, die Befehlsparameter und die Parameterwerte auf.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-166">The syntax diagram lists the command name, the command parameters, and the parameter values.</span></span> <span data-ttu-id="3aaa6-167">Außerdem werden Symbole verwendet, um anzuzeigen, wie ein gültiger Befehl erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-167">It also uses symbols to show how to construct a valid command.</span></span>

<span data-ttu-id="3aaa6-168">In den Syntax Diagrammen werden die folgenden Symbole verwendet:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-168">The syntax diagrams use the following symbols:</span></span>

- <span data-ttu-id="3aaa6-169">Ein Bindestrich `-` gibt einen Parameternamen an.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-169">A hyphen `-` indicates a parameter name.</span></span> <span data-ttu-id="3aaa6-170">Geben Sie in einem Befehl den Bindestrich direkt vor dem Parameternamen ohne dazwischenliegende Leerzeichen ein, wie im Syntax Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-170">In a command, type the hyphen immediately before the parameter name with no intervening spaces, as shown in the syntax diagram.</span></span>

  <span data-ttu-id="3aaa6-171">Wenn Sie beispielsweise den **Name** -Parameter von verwenden möchten, geben Sie Folgendes ein `New-Alias` :</span><span class="sxs-lookup"><span data-stu-id="3aaa6-171">For example, to use the **Name** parameter of `New-Alias`, type:</span></span>

  ```powershell
  -Name
  ```

- <span data-ttu-id="3aaa6-172">Spitze Klammern `<>` geben Platzhalter Text an.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-172">Angle brackets `<>` indicate placeholder text.</span></span> <span data-ttu-id="3aaa6-173">Sie dürfen nicht die spitzen Klammern oder den Platzhalter Text in einem Befehl eingeben.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-173">You do not type the angle brackets or the placeholder text in a command.</span></span> <span data-ttu-id="3aaa6-174">Stattdessen wird Sie durch das Element ersetzt, das beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-174">Instead, you replace it with the item that it describes.</span></span>

  <span data-ttu-id="3aaa6-175">Mithilfe von spitzen Klammern wird der .NET-Typ des Werts identifiziert, der von einem Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-175">Angle brackets are used to identify the .NET type of the value that a parameter takes.</span></span> <span data-ttu-id="3aaa6-176">Wenn Sie z. b. den **Name** -Parameter des `New-Alias` Cmdlets verwenden möchten, ersetzen Sie den `<string>` durch eine Zeichenfolge, bei der es sich um ein einzelnes Wort oder eine Gruppe von Wörtern handelt, die in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-176">For example, to use the **Name** parameter of the `New-Alias` cmdlet, you replace the `<string>` with a string, which is a single word or a group of words that are enclosed in quotation marks.</span></span>

- <span data-ttu-id="3aaa6-177">Eckige Klammern `[ ]` zeigen optionale Elemente an.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-177">Brackets `[ ]` indicate optional items.</span></span> <span data-ttu-id="3aaa6-178">Ein Parameter und sein Wert können optional sein, oder der Name eines erforderlichen Parameters kann optional sein.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-178">A parameter and its value can be optional, or the name of a required parameter can be optional.</span></span>

  <span data-ttu-id="3aaa6-179">Beispielsweise werden der **Description** -Parameter von `New-Alias` und sein Wert in eckige Klammern eingeschlossen, da Sie beide optional sind.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-179">For example, the **Description** parameter of `New-Alias` and its value are enclosed in brackets because they are both optional.</span></span>

  ```powershell
  [-Description <string>]
  ```

  <span data-ttu-id="3aaa6-180">Die Klammern geben auch an, dass der Name-Parameterwert `<string>` erforderlich ist, aber der Parameter Name "Name" ist optional.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-180">The brackets also indicate that the Name parameter value `<string>` is required, but the parameter name, "Name", is optional.</span></span>

  ```powershell
  [-Name] <string>
  ```

- <span data-ttu-id="3aaa6-181">Eine `[]` an einen .NET-Typ angefügte Rechte und linke eckige Klammer gibt an, dass der Parameter einen oder mehrere Werte dieses Typs annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-181">A right and left bracket `[]` appended to a .NET type indicates that the parameter can accept one or multiple values of that type.</span></span> <span data-ttu-id="3aaa6-182">Geben Sie die Werte in eine durch Kommas getrennte Liste ein.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-182">Enter the values in a comma-separated list.</span></span>

  <span data-ttu-id="3aaa6-183">Der **Name** -Parameter des `New-Alias` Cmdlets nimmt z. b. nur eine Zeichenfolge an, aber der **Name** -Parameter von [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) kann eine oder mehrere Zeichen folgen annehmen.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-183">For example, the **Name** parameter of the `New-Alias` cmdlet takes only one string, but the **Name** parameter of [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) can take one or many strings.</span></span>

  ```powershell
  New-Alias [-Name] <string>

  New-Alias -Name MyAlias
  ```

  ```powershell
  Get-Process [-Name] <string[]>

  Get-Process -Name Explorer, Winlogon, Services
  ```

- <span data-ttu-id="3aaa6-184">Geschweifte Klammern `{}` geben eine "Enumeration" an, bei der es sich um einen Satz gültiger Werte für einen Parameter handelt.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-184">Braces `{}` indicate an "enumeration," which is a set of valid values for a parameter.</span></span>

  <span data-ttu-id="3aaa6-185">Die Werte in geschweiften Klammern werden durch vertikale Balken voneinander getrennt `|` .</span><span class="sxs-lookup"><span data-stu-id="3aaa6-185">The values in the braces are separated by vertical bars `|`.</span></span> <span data-ttu-id="3aaa6-186">Diese Balken weisen auf eine "exklusive oder"-Auswahl hin. Dies bedeutet, dass Sie nur einen Wert aus dem Satz von Werten auswählen können, die in den geschweiften Klammern aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-186">These bars indicate an "exclusive OR" choice, meaning that you can choose only one value from the set of values that are listed inside the braces.</span></span>

  <span data-ttu-id="3aaa6-187">Die Syntax für das `New-Alias` Cmdlet enthält z. b. die folgende Wertenumeration für den Parameter **Option** :</span><span class="sxs-lookup"><span data-stu-id="3aaa6-187">For example, the syntax for the `New-Alias` cmdlet includes the following value enumeration for the **Option** parameter:</span></span>

  ```powershell
  -Option {None | ReadOnly | Constant | Private | AllScope}
  ```

  <span data-ttu-id="3aaa6-188">Die geschweiften Klammern und senkrechten Balken zeigen an, dass Sie einen der aufgelisteten Werte für den **options** Parameter, z. b. "schreibgeschützt" oder "allscope", auswählen können.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-188">The braces and vertical bars indicate that you can choose any one of the listed values for the **Option** parameter, such as "ReadOnly" or "AllScope".</span></span>

  ```powershell
  -Option ReadOnly
  ```

## <a name="optional-items"></a><span data-ttu-id="3aaa6-189">Optionale Elemente</span><span class="sxs-lookup"><span data-stu-id="3aaa6-189">Optional Items</span></span>

<span data-ttu-id="3aaa6-190">Eckige Klammern `[]` umschließen optionale Elemente.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-190">Brackets `[]` surround optional items.</span></span> <span data-ttu-id="3aaa6-191">Beispielsweise `New-Alias` ist der **Scope** -Parameter in der Beschreibung der Cmdlet-Syntax optional.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-191">For example, in the `New-Alias` cmdlet syntax description, the **Scope** parameter is optional.</span></span> <span data-ttu-id="3aaa6-192">Dies wird in der Syntax durch die Klammern um den Parameternamen und den Typ angegeben:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-192">This is indicated in the syntax by the brackets around the parameter name and type:</span></span>

```powershell
[-Scope <string>]
```

<span data-ttu-id="3aaa6-193">Beide folgenden Beispiele sind die richtige Verwendung des `New-Alias` Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-193">Both the following examples are correct uses of the `New-Alias` cmdlet:</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd -Value Update-TypeData -Scope Global
```

<span data-ttu-id="3aaa6-194">Ein Parameter Name kann optional sein, auch wenn der Wert für diesen Parameter erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-194">A parameter name can be optional even if the value for that parameter is required.</span></span> <span data-ttu-id="3aaa6-195">Dies wird in der Syntax durch die Klammern um den Parameternamen, aber nicht durch den Parametertyp angegeben, wie in diesem Beispiel aus dem `New-Alias` Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-195">This is indicated in the syntax by the brackets around the parameter name but not the parameter type, as in this example from the `New-Alias` cmdlet:</span></span>

```powershell
[-Name] <string> [-Value] <string>
```

<span data-ttu-id="3aaa6-196">Die folgenden Befehle verwenden das `New-Alias` Cmdlet ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-196">The following commands correctly use the `New-Alias` cmdlet.</span></span> <span data-ttu-id="3aaa6-197">Die Befehle führen zu demselben Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-197">The commands produce the same result.</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd Update-TypeData
New-Alias utd -Value Update-TypeData
New-Alias utd Update-TypeData
```

<span data-ttu-id="3aaa6-198">Wenn der Parameter Name nicht in der Anweisung als typisiert enthalten ist, versucht Windows PowerShell, die Position der Argumente zu verwenden, um die Werte den Parametern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-198">If the parameter name is not included in the statement as typed, Windows PowerShell tries to use the position of the arguments to assign the values to parameters.</span></span>

<span data-ttu-id="3aaa6-199">Das folgende Beispiel ist nicht fertiggestellt:</span><span class="sxs-lookup"><span data-stu-id="3aaa6-199">The following example is not complete:</span></span>

```powershell
New-Alias utd
```

<span data-ttu-id="3aaa6-200">Dieses Cmdlet erfordert Werte für den **Name** -Parameter und den **value** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-200">This cmdlet requires values for both the **Name** and **Value** parameters.</span></span>

<span data-ttu-id="3aaa6-201">In Syntax Beispielen werden auch eckige Klammern zum Benennen und umwandeln in .NET Framework Typen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-201">In syntax examples, brackets are also used in naming and casting to .NET Framework types.</span></span> <span data-ttu-id="3aaa6-202">In diesem Kontext geben eckige Klammern nicht an, dass ein Element optional ist.</span><span class="sxs-lookup"><span data-stu-id="3aaa6-202">In this context, brackets do not indicate an element is optional.</span></span>

## <a name="see-also"></a><span data-ttu-id="3aaa6-203">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="3aaa6-203">SEE ALSO</span></span>

- [<span data-ttu-id="3aaa6-204">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="3aaa6-204">about_Parameters</span></span>](about_Parameters.md)
- [<span data-ttu-id="3aaa6-205">Get-Command</span><span class="sxs-lookup"><span data-stu-id="3aaa6-205">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="3aaa6-206">Get-Help</span><span class="sxs-lookup"><span data-stu-id="3aaa6-206">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

