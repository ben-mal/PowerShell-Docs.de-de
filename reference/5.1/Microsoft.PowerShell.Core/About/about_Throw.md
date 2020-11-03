---
description: Beschreibt das Throw-Schlüsselwort, das einen Abbruchfehler generiert.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: caac7679e2c7ecd21b4fa9e43ab76681ee3faed5
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222484"
---
# <a name="about-throw"></a><span data-ttu-id="7b45e-104">Informationen zu Throw</span><span class="sxs-lookup"><span data-stu-id="7b45e-104">About Throw</span></span>

## <a name="short-description"></a><span data-ttu-id="7b45e-105">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7b45e-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="7b45e-106">Beschreibt das Throw-Schlüsselwort, das einen Abbruchfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="7b45e-106">Describes the Throw keyword, which generates a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="7b45e-107">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7b45e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="7b45e-108">Das throw-Schlüsselwort verursacht einen abschließenden Fehler.</span><span class="sxs-lookup"><span data-stu-id="7b45e-108">The Throw keyword causes a terminating error.</span></span> <span data-ttu-id="7b45e-109">Sie können das throw-Schlüsselwort verwenden, um die Verarbeitung eines Befehls, einer Funktion oder eines Skripts zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="7b45e-109">You can use the Throw keyword to stop the processing of a command, function, or script.</span></span>

<span data-ttu-id="7b45e-110">Beispielsweise können Sie das throw-Schlüsselwort im Skriptblock einer if-Anweisung verwenden, um auf eine Bedingung oder den catch-Block einer try-catch-all-Anweisung zu antworten.</span><span class="sxs-lookup"><span data-stu-id="7b45e-110">For example, you can use the Throw keyword in the script block of an If statement to respond to a condition or in the Catch block of a Try-Catch-Finally statement.</span></span> <span data-ttu-id="7b45e-111">Sie können auch das throw-Schlüsselwort in einer Parameter Deklaration verwenden, um einen Funktionsparameter als obligatorisch zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="7b45e-111">You can also use the Throw keyword in a parameter declaration to make a function parameter mandatory.</span></span>

<span data-ttu-id="7b45e-112">Das throw-Schlüsselwort kann ein beliebiges Objekt auslösen, z. b. eine Zeichenfolge für eine Benutzer Nachricht oder das Objekt, das den Fehler</span><span class="sxs-lookup"><span data-stu-id="7b45e-112">The Throw keyword can throw any object, such as a user message string or the object that caused the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b45e-113">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7b45e-113">SYNTAX</span></span>

<span data-ttu-id="7b45e-114">Die Syntax des Throw-Schlüssel Worts lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7b45e-114">The syntax of the Throw keyword is as follows:</span></span>

```powershell
throw [<expression>]
```

<span data-ttu-id="7b45e-115">Der Ausdruck in der Throw-Syntax ist optional.</span><span class="sxs-lookup"><span data-stu-id="7b45e-115">The expression in the Throw syntax is optional.</span></span> <span data-ttu-id="7b45e-116">Wenn die throw-Anweisung nicht in einem catch-Block angezeigt wird und keinen Ausdruck enthält, generiert Sie einen Skript Fehler.</span><span class="sxs-lookup"><span data-stu-id="7b45e-116">When the Throw statement does not appear in a Catch block, and it does not include an expression, it generates a ScriptHalted error.</span></span>

```powershell
C:\PS> throw

ScriptHalted
At line:1 char:6
+ throw <<<<
+ CategoryInfo          : OperationStopped: (:) [], RuntimeException
+ FullyQualifiedErrorId : ScriptHalted
```

<span data-ttu-id="7b45e-117">Wenn das throw-Schlüsselwort in einem catch-Block ohne einen Ausdruck verwendet wird, wird die aktuelle RuntimeException erneut ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7b45e-117">If the Throw keyword is used in a Catch block without an expression, it throws the current RuntimeException again.</span></span> <span data-ttu-id="7b45e-118">Weitere Informationen finden Sie unter about_Try_Catch_Finally.</span><span class="sxs-lookup"><span data-stu-id="7b45e-118">For more information, see about_Try_Catch_Finally.</span></span>

## <a name="throwing-a-string"></a><span data-ttu-id="7b45e-119">Auslösen einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7b45e-119">THROWING A STRING</span></span>

<span data-ttu-id="7b45e-120">Der optionale Ausdruck in einer throw-Anweisung kann eine Zeichenfolge sein, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7b45e-120">The optional expression in a Throw statement can be a string, as shown in the following example:</span></span>

```powershell
C:\PS> throw "This is an error."

This is an error.
At line:1 char:6
+ throw <<<<  "This is an error."
+ CategoryInfo          : OperationStopped: (This is an error.:String) [], R
untimeException
+ FullyQualifiedErrorId : This is an error.
```

## <a name="throwing-other-objects"></a><span data-ttu-id="7b45e-121">auslösen anderer Objekte</span><span class="sxs-lookup"><span data-stu-id="7b45e-121">THROWING OTHER OBJECTS</span></span>

<span data-ttu-id="7b45e-122">Der Ausdruck kann auch ein Objekt sein, das das Objekt, das den PowerShell-Prozess darstellt, auslöst, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7b45e-122">The expression can also be an object that throws the object that represents the PowerShell process, as shown in the following example:</span></span>

```powershell
C:\PS> throw (get-process PowerShell)

System.Diagnostics.Process (PowerShell)
At line:1 char:6
+ throw <<<<  (get-process PowerShell)
+ CategoryInfo          : OperationStopped: (System.Diagnostics.Process (Pow
erShell):Process) [],
RuntimeException
+ FullyQualifiedErrorId : System.Diagnostics.Process (PowerShell)
```

<span data-ttu-id="7b45e-123">Sie können die TargetObject-Eigenschaft des ErrorRecord-Objekts in der $Error automatischen Variable verwenden, um den Fehler zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="7b45e-123">You can use the TargetObject property of the ErrorRecord object in the $error automatic variable to examine the error.</span></span>

```powershell
C:\PS> $error[0].targetobject

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
319      26    61016      70864   568     3.28   5548 PowerShell
```

<span data-ttu-id="7b45e-124">Sie können auch ein ErrorRecord-Objekt oder eine Microsoft .NET Framework-Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="7b45e-124">You can also throw an ErrorRecord object or a Microsoft .NET Framework exception.</span></span> <span data-ttu-id="7b45e-125">Im folgenden Beispiel wird das throw-Schlüsselwort verwendet, um ein System. FormatException-Objekt auszulösen.</span><span class="sxs-lookup"><span data-stu-id="7b45e-125">The following example uses the Throw keyword to throw a System.FormatException object.</span></span>

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

One of the identified items was in an invalid format.
At line:1 char:6
+ throw <<<<  $formatError
+ CategoryInfo          : OperationStopped: (:) [], FormatException
+ FullyQualifiedErrorId : One of the identified items was in an invalid
format.
```

## <a name="resulting-error"></a><span data-ttu-id="7b45e-126">Ergebnis Fehler</span><span class="sxs-lookup"><span data-stu-id="7b45e-126">RESULTING ERROR</span></span>

<span data-ttu-id="7b45e-127">Das throw-Schlüsselwort kann ein ErrorRecord-Objekt generieren.</span><span class="sxs-lookup"><span data-stu-id="7b45e-127">The Throw keyword can generate an ErrorRecord object.</span></span> <span data-ttu-id="7b45e-128">Die Exception-Eigenschaft des ErrorRecord-Objekts enthält ein RuntimeException-Objekt.</span><span class="sxs-lookup"><span data-stu-id="7b45e-128">The Exception property of the ErrorRecord object contains a RuntimeException object.</span></span> <span data-ttu-id="7b45e-129">Der Rest des ErrorRecord-Objekts und das RuntimeException-Objekt variieren mit dem Objekt, das das throw-Schlüsselwort auslöst.</span><span class="sxs-lookup"><span data-stu-id="7b45e-129">The remainder of the ErrorRecord object and the RuntimeException object vary with the object that the Throw keyword throws.</span></span>

<span data-ttu-id="7b45e-130">Das RuntimeException-Objekt ist in einem ErrorRecord-Objekt umschließt, und das ErrorRecord-Objekt wird automatisch in der $Error automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7b45e-130">The RunTimeException object is wrapped in an ErrorRecord object, and the ErrorRecord object is automatically saved in the $Error automatic variable.</span></span>

## <a name="using-throw-to-create-a-mandatory-parameter"></a><span data-ttu-id="7b45e-131">Verwenden von Throw zum Erstellen eines obligatorischen Parameters</span><span class="sxs-lookup"><span data-stu-id="7b45e-131">USING THROW TO CREATE A MANDATORY PARAMETER</span></span>

<span data-ttu-id="7b45e-132">Sie können das throw-Schlüsselwort verwenden, um einen Funktionsparameter als obligatorisch zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="7b45e-132">You can use the Throw keyword to make a function parameter mandatory.</span></span>

<span data-ttu-id="7b45e-133">Dies ist eine Alternative zur Verwendung des obligatorischen Parameters des Parameter Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="7b45e-133">This is an alternative to using the Mandatory parameter of the Parameter keyword.</span></span> <span data-ttu-id="7b45e-134">Wenn Sie den obligatorischen Parameter verwenden, fordert das System den Benutzer zum erforderlichen Parameterwert auf.</span><span class="sxs-lookup"><span data-stu-id="7b45e-134">When you use the Mandatory parameter, the system prompts the user for the required parameter value.</span></span> <span data-ttu-id="7b45e-135">Wenn Sie das throw-Schlüsselwort verwenden, wird der Befehl beendet und der Fehler Daten Satz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7b45e-135">When you use the Throw keyword, the command stops and displays the error record.</span></span>

<span data-ttu-id="7b45e-136">Beispielsweise macht das throw-Schlüsselwort im Parameter Teil Ausdruck den path-Parameter zu einem erforderlichen Parameter in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="7b45e-136">For example, the Throw keyword in the parameter subexpression makes the Path parameter a required parameter in the function.</span></span>

<span data-ttu-id="7b45e-137">In diesem Fall löst das throw-Schlüsselwort eine Meldungs Zeichenfolge aus, aber es ist das vorhanden sein des Throw-Schlüssel Worts, das den abschließenden Fehler generiert, wenn der path-Parameter nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="7b45e-137">In this case, the Throw keyword throws a message string, but it is the presence of the Throw keyword that generates the terminating error if the Path parameter is not specified.</span></span> <span data-ttu-id="7b45e-138">Der Ausdruck, der auf throw folgt, ist optional.</span><span class="sxs-lookup"><span data-stu-id="7b45e-138">The expression that follows Throw is optional.</span></span>

```powershell
function Get-XMLFiles
{
  param ($path = $(throw "The Path parameter is required."))
  dir -path $path\*.xml -recurse |
    sort lastwritetime |
      ft lastwritetime, attributes, name  -auto
}
```

## <a name="see-also"></a><span data-ttu-id="7b45e-139">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="7b45e-139">SEE ALSO</span></span>

[<span data-ttu-id="7b45e-140">about_Break</span><span class="sxs-lookup"><span data-stu-id="7b45e-140">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="7b45e-141">about_Continue</span><span class="sxs-lookup"><span data-stu-id="7b45e-141">about_Continue</span></span>](about_Continue.md)

[<span data-ttu-id="7b45e-142">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="7b45e-142">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="7b45e-143">about_Trap</span><span class="sxs-lookup"><span data-stu-id="7b45e-143">about_Trap</span></span>](about_Trap.md)

[<span data-ttu-id="7b45e-144">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="7b45e-144">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
