---
description: Beschreibt die Syntax Diagramme, die in PowerShell verwendet werden.
keywords: powershell,cmdlet
ms.date: 06/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_syntax?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Syntax
ms.openlocfilehash: 143d1673ca03e390a85651f0083cef6ab6e43ba3
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220743"
---
# <a name="about-command-syntax"></a><span data-ttu-id="0cfa2-104">Informationen zur Befehls Syntax</span><span class="sxs-lookup"><span data-stu-id="0cfa2-104">About Command Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="0cfa2-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0cfa2-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="0cfa2-106">Beschreibt die Syntax Diagramme, die in PowerShell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-106">Describes the syntax diagrams that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0cfa2-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0cfa2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="0cfa2-108">Die Cmdlets " [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) " und " [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) " zeigen Syntax Diagramme an, die Ihnen helfen, Befehle korrekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-108">The [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlets display syntax diagrams to help you construct commands correctly.</span></span> <span data-ttu-id="0cfa2-109">In diesem Thema wird erläutert, wie die Syntax Diagramme interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-109">This topic explains how to interpret the syntax diagrams.</span></span>

## <a name="syntax-diagrams"></a><span data-ttu-id="0cfa2-110">Syntax Diagramme</span><span class="sxs-lookup"><span data-stu-id="0cfa2-110">SYNTAX DIAGRAMS</span></span>

<span data-ttu-id="0cfa2-111">Jeder Absatz eines Befehlssyntax Diagramms stellt ein gültiges Formular des Befehls dar.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-111">Each paragraph in a command syntax diagram represents a valid form of the command.</span></span>

<span data-ttu-id="0cfa2-112">Um einen Befehl zu erstellen, befolgen Sie das Syntax Diagramm von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-112">To construct a command, follow the syntax diagram from left to right.</span></span> <span data-ttu-id="0cfa2-113">Wählen Sie unter den optionalen Parametern aus, und geben Sie Werte für die Platzhalter an.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-113">Select from among the optional parameters and provide values for the placeholders.</span></span>

<span data-ttu-id="0cfa2-114">PowerShell verwendet die folgende Notation für Syntax Diagramme.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-114">PowerShell uses the following notation for syntax diagrams.</span></span>

```powershell
<command-name> -<Required Parameter Name> <Required Parameter Value>
[-<Optional Parameter Name> <Optional Parameter Value>]
[-<Optional Switch Parameters>]
[-<Optional Parameter Name>] <Required Parameter Value>
```

<span data-ttu-id="0cfa2-115">Im folgenden finden Sie die Syntax für das Cmdlet [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) .</span><span class="sxs-lookup"><span data-stu-id="0cfa2-115">The following is the syntax for the [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias) cmdlet.</span></span>

```powershell
New-Alias [-Name] <string> [-Value] <string> [-Description <string>]
[-Force] [-Option {None | ReadOnly | Constant | Private | AllScope}]
[-PassThru] [-Scope <string>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

<span data-ttu-id="0cfa2-116">Die Syntax wird zur besseren Lesbarkeit groß geschrieben, aber bei PowerShell wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-116">The syntax is capitalized for readability, but PowerShell is case-insensitive.</span></span>

<span data-ttu-id="0cfa2-117">Das Syntax Diagramm enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-117">The syntax diagram has the following elements.</span></span>

## <a name="command-name"></a><span data-ttu-id="0cfa2-118">Befehlsname</span><span class="sxs-lookup"><span data-stu-id="0cfa2-118">Command name</span></span>

<span data-ttu-id="0cfa2-119">Befehle beginnen immer mit einem Befehlsnamen, z `New-Alias` . b..</span><span class="sxs-lookup"><span data-stu-id="0cfa2-119">Commands always begin with a command name, such as `New-Alias`.</span></span> <span data-ttu-id="0cfa2-120">Geben Sie den Befehlsnamen oder seinen Alias ein, z. b. "GCM" für `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="0cfa2-120">Type the command name or its alias, such a "gcm" for `Get-Command`.</span></span>

## <a name="parameters"></a><span data-ttu-id="0cfa2-121">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cfa2-121">Parameters</span></span>

<span data-ttu-id="0cfa2-122">Die Parameter eines Befehls sind Optionen, mit denen bestimmt wird, was der Befehl bewirkt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-122">The parameters of a command are options that determine what the command does.</span></span>
<span data-ttu-id="0cfa2-123">Einige Parameter akzeptieren einen "Wert", bei dem es sich um eine Benutzereingabe für den Befehl handelt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-123">Some parameters take a "value" which is user input to the command.</span></span>

<span data-ttu-id="0cfa2-124">Der- `Get-Help` Befehl verfügt z. b. über einen **Name** -Parameter, mit dem Sie den Namen des Themas angeben können, für das die Hilfe angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-124">For example, the `Get-Help` command has a **Name** parameter that lets you specify the name of the topic for which help is displayed.</span></span> <span data-ttu-id="0cfa2-125">Der Themenname ist der Wert des **Name** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-125">The topic name is the value of the **Name** parameter.</span></span>

<span data-ttu-id="0cfa2-126">In einem PowerShell-Befehl beginnen Parameternamen immer mit einem Bindestrich.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-126">In a PowerShell command, parameter names always begin with a hyphen.</span></span>
<span data-ttu-id="0cfa2-127">Der Bindestrich weist PowerShell an, dass das Element im Befehl ein Parameter Name ist.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-127">The hyphen tells PowerShell that the item in the command is a parameter name.</span></span>

<span data-ttu-id="0cfa2-128">Wenn Sie z. b. den Name-Parameter von verwenden möchten `New-Alias` , geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-128">For example, to use the Name parameter of `New-Alias`, you type the following:</span></span>

```powershell
-Name
```

<span data-ttu-id="0cfa2-129">Parameter können obligatorisch oder optional sein.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-129">Parameters can be mandatory or optional.</span></span> <span data-ttu-id="0cfa2-130">In einem Syntax Diagramm werden optionale Elemente in eckige Klammern eingeschlossen `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="0cfa2-130">In a syntax diagram, optional items are enclosed in brackets `[ ]`.</span></span>

<span data-ttu-id="0cfa2-131">Weitere Informationen zu Parametern finden Sie unter [about_Parameters](about_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa2-131">For more information about parameters, see [about_Parameters](about_Parameters.md).</span></span>

## <a name="parameter-values"></a><span data-ttu-id="0cfa2-132">Parameterwerte</span><span class="sxs-lookup"><span data-stu-id="0cfa2-132">Parameter Values</span></span>

<span data-ttu-id="0cfa2-133">Ein Parameterwert ist die Eingabe, die der-Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-133">A parameter value is the input that the parameter takes.</span></span> <span data-ttu-id="0cfa2-134">Da Windows PowerShell auf dem Microsoft .NET Framework basiert, werden Parameterwerte im Syntax Diagramm durch ihren .NET-Typ dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-134">Because Windows PowerShell is based on the Microsoft .NET Framework, parameter values are represented in the syntax diagram by their .NET type.</span></span>

<span data-ttu-id="0cfa2-135">Beispielsweise übernimmt der Name-Parameter von den `Get-Help` Wert "String", bei dem es sich um eine Text Zeichenfolge handelt, z. b. ein einzelnes Wort oder mehrere Wörter, die in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-135">For example, the Name parameter of `Get-Help` takes a "String" value, which is a text string, such as a single word or multiple words enclosed in quotation marks.</span></span>

```powershell
[-Name] <string>
```

<span data-ttu-id="0cfa2-136">Der .NET-Typ eines Parameter Werts wird in spitzen Klammern eingeschlossen `< >` , um anzugeben, dass es sich um einen Platzhalter für einen Wert handelt, nicht um ein Literalzeichen, das Sie in einen Befehl eingeben.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-136">The .NET type of a parameter value is enclosed in angle brackets `< >` to indicate that it is placeholder for a value and not a literal that you type in a command.</span></span>

<span data-ttu-id="0cfa2-137">Um den-Parameter zu verwenden, ersetzen Sie den .net-Typplatzhalter durch ein-Objekt, das über den angegebenen .NET-Typ verfügt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-137">To use the parameter, replace the .NET type placeholder with an object that has the specified .NET type.</span></span>

<span data-ttu-id="0cfa2-138">Wenn Sie z. b. den **Name** -Parameter verwenden möchten, geben Sie "-Name" gefolgt von einer Zeichenfolge ein, z. b. Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-138">For example, to use the **Name** parameter, type "-Name" followed by a string, such as the following:</span></span>

```powershell
-Name MyAlias
```

## <a name="parameters-with-no-values"></a><span data-ttu-id="0cfa2-139">Parameter ohne Werte</span><span class="sxs-lookup"><span data-stu-id="0cfa2-139">Parameters with no values</span></span>

<span data-ttu-id="0cfa2-140">Einige Parameter akzeptieren keine Eingaben, sodass Sie nicht über einen Parameterwert verfügen.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-140">Some parameters do not accept input, so they do not have a parameter value.</span></span>
<span data-ttu-id="0cfa2-141">Parameter ohne Werte werden als "Switch-Parameter" bezeichnet, da Sie wie on/off-Switches funktionieren.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-141">Parameters without values are called "switch parameters" because they work like on/off switches.</span></span> <span data-ttu-id="0cfa2-142">Sie fügen Sie ein (on), oder Sie können Sie (aus) über einen Befehl weglassen.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-142">You include them (on) or you omit them (off) from a command.</span></span>

<span data-ttu-id="0cfa2-143">Um einen Switch-Parameter zu verwenden, geben Sie einfach den Parameternamen ein, dem ein Bindestrich vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-143">To use a switch parameter, just type the parameter name, preceded by a hyphen.</span></span>

<span data-ttu-id="0cfa2-144">Wenn Sie z. b. den **WhatIf** -Parameter des `New-Alias` Cmdlets verwenden möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-144">For example, to use the **WhatIf** parameter of the `New-Alias` cmdlet, type the following:</span></span>

```powershell
-WhatIf
```

## <a name="parameter-sets"></a><span data-ttu-id="0cfa2-145">Parameter Sätze</span><span class="sxs-lookup"><span data-stu-id="0cfa2-145">Parameter Sets</span></span>

<span data-ttu-id="0cfa2-146">Die Parameter eines Befehls werden in Parametersätzen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-146">The parameters of a command are listed in parameter sets.</span></span> <span data-ttu-id="0cfa2-147">Parameter Sätze sehen wie die Absätze eines Syntax Diagramms aus.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-147">Parameter sets look like the paragraphs of a syntax diagram.</span></span>

<span data-ttu-id="0cfa2-148">Für das `New-Alias` Cmdlet ist ein Parametersatz festgelegt, aber viele Cmdlets verfügen über mehrere Parametersätze.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-148">The `New-Alias` cmdlet has one parameter set, but many cmdlets have multiple parameter sets.</span></span> <span data-ttu-id="0cfa2-149">Einige der Cmdlet-Parameter sind für einen Parametersatz eindeutig, und andere sind in mehreren Parametersätzen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-149">Some of the cmdlet parameters are unique to a parameter set, and others appear in multiple parameter sets.</span></span> <span data-ttu-id="0cfa2-150">Jeder Parametersatz stellt das Format eines gültigen Befehls dar.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-150">Each parameter set represents the format of a valid command.</span></span> <span data-ttu-id="0cfa2-151">Ein Parametersatz enthält nur Parameter, die in einem Befehl verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-151">A parameter set includes only parameters that can be used together in a command.</span></span> <span data-ttu-id="0cfa2-152">Wenn Parameter nicht im selben Befehl verwendet werden können, werden Sie in separaten Parametersätzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-152">If parameters cannot be used in the same command, they appear in separate parameter sets.</span></span>

<span data-ttu-id="0cfa2-153">Beispielsweise verfügt das [Get-Random-](xref:Microsoft.PowerShell.Utility.Get-Random) Cmdlet über die folgenden Parametersätze:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-153">For example, the [Get-Random](xref:Microsoft.PowerShell.Utility.Get-Random) cmdlet has the following parameter sets:</span></span>

```powershell
Get-Random [[-Maximum] <Object>] [-Minimum <Object>] [-SetSeed <int>]
[<CommonParameters>]

Get-Random [-InputObject] <Object[]> [-Count <int>] [-SetSeed <int>]
[<CommonParameters>]
```

<span data-ttu-id="0cfa2-154">Der erste Parametersatz, der eine Zufallszahl zurückgibt, hat den **minimalen** und den **maximalen** Parameter.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-154">The first parameter set, which returns a random number, has the **Minimum** and **Maximum** parameters.</span></span> <span data-ttu-id="0cfa2-155">Der zweite Parametersatz, der ein zufällig ausgewähltes Objekt aus einem Satz von Objekten zurückgibt, enthält die Parameter **Inputobject** und **count** .</span><span class="sxs-lookup"><span data-stu-id="0cfa2-155">The second parameter set, which returns a randomly selected object from a set of objects, includes the **InputObject** and **Count** parameters.</span></span> <span data-ttu-id="0cfa2-156">Beide Parametersätze verfügen über den **setseed** -Parameter und die allgemeinen Parameter.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-156">Both parameter sets have the **SetSeed** parameter and the common parameters.</span></span>

<span data-ttu-id="0cfa2-157">Diese Parametersätze geben an, dass Sie die **Inputobject** -und **count** -Parameter im gleichen Befehl verwenden können, aber Sie können die Parameter " **Maximum** " und " **count** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-157">These parameter sets indicate that you can use the **InputObject** and **Count** parameters in the same command, but you cannot use the **Maximum** and **Count** parameters in the same command.</span></span>

<span data-ttu-id="0cfa2-158">Sie geben den Parametersatz an, den Sie verwenden möchten, indem Sie die Parameter in diesem Parametersatz verwenden.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-158">You indicate which parameter set you want to use by using the parameters in that parameter set.</span></span>

<span data-ttu-id="0cfa2-159">Allerdings verfügt jedes Cmdlet auch über einen Standardparameter Satz.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-159">However, every cmdlet also has a default parameter set.</span></span> <span data-ttu-id="0cfa2-160">Der Standardparameter Satz wird verwendet, wenn Sie keine Parameter angeben, die für einen Parametersatz eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-160">The default parameter set is used when you do not specify parameters that are unique to a parameter set.</span></span> <span data-ttu-id="0cfa2-161">Wenn Sie z. b. `Get-Random` ohne Parameter verwenden, geht Windows PowerShell davon aus, dass Sie den **Number** -Parametersatz verwenden und eine Zufallszahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-161">For example, if you use `Get-Random` without parameters, Windows PowerShell assumes that you are using the **Number** parameter set and it returns a random number.</span></span>

<span data-ttu-id="0cfa2-162">In jedem Parametersatz werden die Parameter in der Positions Reihenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-162">In each parameter set, the parameters appear in position order.</span></span> <span data-ttu-id="0cfa2-163">Die Reihenfolge von Parametern in einem Befehl ist nur wichtig, wenn Sie die optionalen Parameternamen weglassen.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-163">The order of parameters in a command matters only when you omit the optional parameter names.</span></span> <span data-ttu-id="0cfa2-164">Wenn Parameternamen ausgelassen werden, werden den Parametern von PowerShell Werte nach Position und Typ zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-164">When parameter names are omitted, PowerShell assigns values to parameters by position and type.</span></span> <span data-ttu-id="0cfa2-165">Weitere Informationen zur Parameter Position finden Sie unter `about_Parameters` .</span><span class="sxs-lookup"><span data-stu-id="0cfa2-165">For more information about parameter position, see `about_Parameters`.</span></span>

## <a name="symbols-in-syntax-diagrams"></a><span data-ttu-id="0cfa2-166">Symbole in Syntax Diagrammen</span><span class="sxs-lookup"><span data-stu-id="0cfa2-166">Symbols in Syntax Diagrams</span></span>

<span data-ttu-id="0cfa2-167">Das Syntax Diagramm listet den Befehlsnamen, die Befehlsparameter und die Parameterwerte auf.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-167">The syntax diagram lists the command name, the command parameters, and the parameter values.</span></span> <span data-ttu-id="0cfa2-168">Außerdem werden Symbole verwendet, um anzuzeigen, wie ein gültiger Befehl erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-168">It also uses symbols to show how to construct a valid command.</span></span>

<span data-ttu-id="0cfa2-169">In den Syntax Diagrammen werden die folgenden Symbole verwendet:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-169">The syntax diagrams use the following symbols:</span></span>

- <span data-ttu-id="0cfa2-170">Ein Bindestrich `-` gibt einen Parameternamen an.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-170">A hyphen `-` indicates a parameter name.</span></span> <span data-ttu-id="0cfa2-171">Geben Sie in einem Befehl den Bindestrich direkt vor dem Parameternamen ohne dazwischenliegende Leerzeichen ein, wie im Syntax Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-171">In a command, type the hyphen immediately before the parameter name with no intervening spaces, as shown in the syntax diagram.</span></span>

  <span data-ttu-id="0cfa2-172">Wenn Sie beispielsweise den **Name** -Parameter von verwenden möchten, geben Sie Folgendes ein `New-Alias` :</span><span class="sxs-lookup"><span data-stu-id="0cfa2-172">For example, to use the **Name** parameter of `New-Alias`, type:</span></span>

  ```powershell
  -Name
  ```

- <span data-ttu-id="0cfa2-173">Spitze Klammern `<>` geben Platzhalter Text an.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-173">Angle brackets `<>` indicate placeholder text.</span></span> <span data-ttu-id="0cfa2-174">Sie dürfen nicht die spitzen Klammern oder den Platzhalter Text in einem Befehl eingeben.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-174">You do not type the angle brackets or the placeholder text in a command.</span></span> <span data-ttu-id="0cfa2-175">Stattdessen wird Sie durch das Element ersetzt, das beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-175">Instead, you replace it with the item that it describes.</span></span>

  <span data-ttu-id="0cfa2-176">Mithilfe von spitzen Klammern wird der .NET-Typ des Werts identifiziert, der von einem Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-176">Angle brackets are used to identify the .NET type of the value that a parameter takes.</span></span> <span data-ttu-id="0cfa2-177">Wenn Sie z. b. den **Name** -Parameter des `New-Alias` Cmdlets verwenden möchten, ersetzen Sie den `<string>` durch eine Zeichenfolge, bei der es sich um ein einzelnes Wort oder eine Gruppe von Wörtern handelt, die in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-177">For example, to use the **Name** parameter of the `New-Alias` cmdlet, you replace the `<string>` with a string, which is a single word or a group of words that are enclosed in quotation marks.</span></span>

- <span data-ttu-id="0cfa2-178">Eckige Klammern `[ ]` zeigen optionale Elemente an.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-178">Brackets `[ ]` indicate optional items.</span></span> <span data-ttu-id="0cfa2-179">Ein Parameter und sein Wert können optional sein, oder der Name eines erforderlichen Parameters kann optional sein.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-179">A parameter and its value can be optional, or the name of a required parameter can be optional.</span></span>

  <span data-ttu-id="0cfa2-180">Beispielsweise werden der **Description** -Parameter von `New-Alias` und sein Wert in eckige Klammern eingeschlossen, da Sie beide optional sind.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-180">For example, the **Description** parameter of `New-Alias` and its value are enclosed in brackets because they are both optional.</span></span>

  ```powershell
  [-Description <string>]
  ```

  <span data-ttu-id="0cfa2-181">Die Klammern geben auch an, dass der Name-Parameterwert `<string>` erforderlich ist, aber der Parameter Name "Name" ist optional.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-181">The brackets also indicate that the Name parameter value `<string>` is required, but the parameter name, "Name", is optional.</span></span>

  ```powershell
  [-Name] <string>
  ```

- <span data-ttu-id="0cfa2-182">Eine `[]` an einen .NET-Typ angefügte Rechte und linke eckige Klammer gibt an, dass der Parameter einen oder mehrere Werte dieses Typs annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-182">A right and left bracket `[]` appended to a .NET type indicates that the parameter can accept one or multiple values of that type.</span></span> <span data-ttu-id="0cfa2-183">Geben Sie die Werte in eine durch Kommas getrennte Liste ein.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-183">Enter the values in a comma-separated list.</span></span>

  <span data-ttu-id="0cfa2-184">Der **Name** -Parameter des `New-Alias` Cmdlets nimmt z. b. nur eine Zeichenfolge an, aber der **Name** -Parameter von [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) kann eine oder mehrere Zeichen folgen annehmen.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-184">For example, the **Name** parameter of the `New-Alias` cmdlet takes only one string, but the **Name** parameter of [Get-Process](xref:Microsoft.PowerShell.Management.Get-Process) can take one or many strings.</span></span>

  ```powershell
  New-Alias [-Name] <string>

  New-Alias -Name MyAlias
  ```

  ```powershell
  Get-Process [-Name] <string[]>

  Get-Process -Name Explorer, Winlogon, Services
  ```

- <span data-ttu-id="0cfa2-185">Geschweifte Klammern `{}` geben eine "Enumeration" an, bei der es sich um einen Satz gültiger Werte für einen Parameter handelt.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-185">Braces `{}` indicate an "enumeration," which is a set of valid values for a parameter.</span></span>

  <span data-ttu-id="0cfa2-186">Die Werte in geschweiften Klammern werden durch vertikale Balken voneinander getrennt `|` .</span><span class="sxs-lookup"><span data-stu-id="0cfa2-186">The values in the braces are separated by vertical bars `|`.</span></span> <span data-ttu-id="0cfa2-187">Diese Balken weisen auf eine "exklusive oder"-Auswahl hin. Dies bedeutet, dass Sie nur einen Wert aus dem Satz von Werten auswählen können, die in den geschweiften Klammern aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-187">These bars indicate an "exclusive OR" choice, meaning that you can choose only one value from the set of values that are listed inside the braces.</span></span>

  <span data-ttu-id="0cfa2-188">Die Syntax für das `New-Alias` Cmdlet enthält z. b. die folgende Wertenumeration für den Parameter **Option** :</span><span class="sxs-lookup"><span data-stu-id="0cfa2-188">For example, the syntax for the `New-Alias` cmdlet includes the following value enumeration for the **Option** parameter:</span></span>

  ```powershell
  -Option {None | ReadOnly | Constant | Private | AllScope}
  ```

  <span data-ttu-id="0cfa2-189">Die geschweiften Klammern und senkrechten Balken zeigen an, dass Sie einen der aufgelisteten Werte für den **options** Parameter, z. b. "schreibgeschützt" oder "allscope", auswählen können.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-189">The braces and vertical bars indicate that you can choose any one of the listed values for the **Option** parameter, such as "ReadOnly" or "AllScope".</span></span>

  ```powershell
  -Option ReadOnly
  ```

## <a name="optional-items"></a><span data-ttu-id="0cfa2-190">Optionale Elemente</span><span class="sxs-lookup"><span data-stu-id="0cfa2-190">Optional Items</span></span>

<span data-ttu-id="0cfa2-191">Eckige Klammern `[]` umschließen optionale Elemente.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-191">Brackets `[]` surround optional items.</span></span> <span data-ttu-id="0cfa2-192">Beispielsweise `New-Alias` ist der **Scope** -Parameter in der Beschreibung der Cmdlet-Syntax optional.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-192">For example, in the `New-Alias` cmdlet syntax description, the **Scope** parameter is optional.</span></span> <span data-ttu-id="0cfa2-193">Dies wird in der Syntax durch die Klammern um den Parameternamen und den Typ angegeben:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-193">This is indicated in the syntax by the brackets around the parameter name and type:</span></span>

```powershell
[-Scope <string>]
```

<span data-ttu-id="0cfa2-194">Beide folgenden Beispiele sind die richtige Verwendung des `New-Alias` Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-194">Both the following examples are correct uses of the `New-Alias` cmdlet:</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd -Value Update-TypeData -Scope Global
```

<span data-ttu-id="0cfa2-195">Ein Parameter Name kann optional sein, auch wenn der Wert für diesen Parameter erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-195">A parameter name can be optional even if the value for that parameter is required.</span></span> <span data-ttu-id="0cfa2-196">Dies wird in der Syntax durch die Klammern um den Parameternamen, aber nicht durch den Parametertyp angegeben, wie in diesem Beispiel aus dem `New-Alias` Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-196">This is indicated in the syntax by the brackets around the parameter name but not the parameter type, as in this example from the `New-Alias` cmdlet:</span></span>

```powershell
[-Name] <string> [-Value] <string>
```

<span data-ttu-id="0cfa2-197">Die folgenden Befehle verwenden das `New-Alias` Cmdlet ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-197">The following commands correctly use the `New-Alias` cmdlet.</span></span> <span data-ttu-id="0cfa2-198">Die Befehle führen zu demselben Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-198">The commands produce the same result.</span></span>

```powershell
New-Alias -Name utd -Value Update-TypeData
New-Alias -Name utd Update-TypeData
New-Alias utd -Value Update-TypeData
New-Alias utd Update-TypeData
```

<span data-ttu-id="0cfa2-199">Wenn der Parameter Name nicht in der Anweisung als typisiert enthalten ist, versucht Windows PowerShell, die Position der Argumente zu verwenden, um die Werte den Parametern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-199">If the parameter name is not included in the statement as typed, Windows PowerShell tries to use the position of the arguments to assign the values to parameters.</span></span>

<span data-ttu-id="0cfa2-200">Das folgende Beispiel ist nicht fertiggestellt:</span><span class="sxs-lookup"><span data-stu-id="0cfa2-200">The following example is not complete:</span></span>

```powershell
New-Alias utd
```

<span data-ttu-id="0cfa2-201">Dieses Cmdlet erfordert Werte für den **Name** -Parameter und den **value** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-201">This cmdlet requires values for both the **Name** and **Value** parameters.</span></span>

<span data-ttu-id="0cfa2-202">In Syntax Beispielen werden auch eckige Klammern zum Benennen und umwandeln in .NET Framework Typen verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-202">In syntax examples, brackets are also used in naming and casting to .NET Framework types.</span></span> <span data-ttu-id="0cfa2-203">In diesem Kontext geben eckige Klammern nicht an, dass ein Element optional ist.</span><span class="sxs-lookup"><span data-stu-id="0cfa2-203">In this context, brackets do not indicate an element is optional.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cfa2-204">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="0cfa2-204">SEE ALSO</span></span>

- [<span data-ttu-id="0cfa2-205">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="0cfa2-205">about_Parameters</span></span>](about_Parameters.md)
- [<span data-ttu-id="0cfa2-206">Get-Command</span><span class="sxs-lookup"><span data-stu-id="0cfa2-206">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="0cfa2-207">Get-Help</span><span class="sxs-lookup"><span data-stu-id="0cfa2-207">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)
