---
description: Beschreibt das Throw-Schlüsselwort, das einen Abbruchfehler generiert.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: bef005f47583523f69a8b25651eb0ee5bfc5b224
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103195846"
---
# <a name="about-throw"></a><span data-ttu-id="5ff0b-103">Informationen zu Throw</span><span class="sxs-lookup"><span data-stu-id="5ff0b-103">About Throw</span></span>

## <a name="short-description"></a><span data-ttu-id="5ff0b-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ff0b-104">Short description</span></span>
<span data-ttu-id="5ff0b-105">Beschreibt das Throw-Schlüsselwort, das einen Abbruchfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-105">Describes the Throw keyword, which generates a terminating error.</span></span>

## <a name="long-description"></a><span data-ttu-id="5ff0b-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ff0b-106">Long description</span></span>

<span data-ttu-id="5ff0b-107">Das throw-Schlüsselwort verursacht einen abschließenden Fehler.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-107">The Throw keyword causes a terminating error.</span></span> <span data-ttu-id="5ff0b-108">Sie können das throw-Schlüsselwort verwenden, um die Verarbeitung eines Befehls, einer Funktion oder eines Skripts zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-108">You can use the Throw keyword to stop the processing of a command, function, or script.</span></span>

<span data-ttu-id="5ff0b-109">Beispielsweise können Sie das throw-Schlüsselwort im Skriptblock einer if-Anweisung verwenden, um auf eine Bedingung oder den catch-Block einer try-catch-all-Anweisung zu antworten.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-109">For example, you can use the Throw keyword in the script block of an If statement to respond to a condition or in the Catch block of a Try-Catch-Finally statement.</span></span> <span data-ttu-id="5ff0b-110">Sie können auch das throw-Schlüsselwort in einer Parameter Deklaration verwenden, um einen Funktionsparameter als obligatorisch zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-110">You can also use the Throw keyword in a parameter declaration to make a function parameter mandatory.</span></span>

<span data-ttu-id="5ff0b-111">Das throw-Schlüsselwort kann ein beliebiges Objekt auslösen, z. b. eine Zeichenfolge für eine Benutzer Nachricht oder das Objekt, das den Fehler</span><span class="sxs-lookup"><span data-stu-id="5ff0b-111">The Throw keyword can throw any object, such as a user message string or the object that caused the error.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ff0b-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ff0b-112">Syntax</span></span>

<span data-ttu-id="5ff0b-113">Die Syntax des Throw-Schlüssel Worts lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5ff0b-113">The syntax of the Throw keyword is as follows:</span></span>

```powershell
throw [<expression>]
```

<span data-ttu-id="5ff0b-114">Der Ausdruck in der Throw-Syntax ist optional.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-114">The expression in the Throw syntax is optional.</span></span> <span data-ttu-id="5ff0b-115">Wenn die throw-Anweisung nicht in einem catch-Block angezeigt wird und keinen Ausdruck enthält, generiert Sie einen Skript Fehler.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-115">When the Throw statement does not appear in a Catch block, and it does not include an expression, it generates a ScriptHalted error.</span></span>

```powershell
C:\PS> throw

Exception: ScriptHalted
```

<span data-ttu-id="5ff0b-116">Wenn das throw-Schlüsselwort in einem catch-Block ohne einen Ausdruck verwendet wird, wird die aktuelle RuntimeException erneut ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-116">If the Throw keyword is used in a Catch block without an expression, it throws the current RuntimeException again.</span></span> <span data-ttu-id="5ff0b-117">Weitere Informationen finden Sie unter about_Try_Catch_Finally.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-117">For more information, see about_Try_Catch_Finally.</span></span>

## <a name="throwing-a-string"></a><span data-ttu-id="5ff0b-118">Auslösen einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="5ff0b-118">Throwing a string</span></span>

<span data-ttu-id="5ff0b-119">Der optionale Ausdruck in einer throw-Anweisung kann eine Zeichenfolge sein, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5ff0b-119">The optional expression in a Throw statement can be a string, as shown in the following example:</span></span>

```powershell
C:\PS> throw "This is an error."

Exception: This is an error.
```

## <a name="throwing-other-objects"></a><span data-ttu-id="5ff0b-120">Auslösen anderer Objekte</span><span class="sxs-lookup"><span data-stu-id="5ff0b-120">Throwing other objects</span></span>

<span data-ttu-id="5ff0b-121">Der Ausdruck kann auch ein Objekt sein, das das Objekt, das den PowerShell-Prozess darstellt, auslöst, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5ff0b-121">The expression can also be an object that throws the object that represents the PowerShell process, as shown in the following example:</span></span>

```powershell
C:\PS> throw (get-process Pwsh)

Exception: System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh)
```

<span data-ttu-id="5ff0b-122">Sie können die TargetObject-Eigenschaft des ErrorRecord-Objekts in der $Error automatischen Variable verwenden, um den Fehler zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-122">You can use the TargetObject property of the ErrorRecord object in the $error automatic variable to examine the error.</span></span>

```powershell
C:\PS> $error[0].targetobject

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    125   174.44     229.57      23.61    1548   2 pwsh
     63    44.07      81.95       1.75    1732   2 pwsh
     63    43.32      77.65       1.48    9092   2 pwsh
```

<span data-ttu-id="5ff0b-123">Sie können auch ein ErrorRecord-Objekt oder eine .NET-Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-123">You can also throw an ErrorRecord object or a .NET exception.</span></span> <span data-ttu-id="5ff0b-124">Im folgenden Beispiel wird das throw-Schlüsselwort verwendet, um ein System. FormatException-Objekt auszulösen.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-124">The following example uses the Throw keyword to throw a System.FormatException object.</span></span>

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

OperationStopped: One of the identified items was in an invalid format.
```

## <a name="the-resulting-error"></a><span data-ttu-id="5ff0b-125">Der resultierende Fehler</span><span class="sxs-lookup"><span data-stu-id="5ff0b-125">The resulting error</span></span>

<span data-ttu-id="5ff0b-126">Das throw-Schlüsselwort kann ein ErrorRecord-Objekt generieren.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-126">The Throw keyword can generate an ErrorRecord object.</span></span> <span data-ttu-id="5ff0b-127">Die Exception-Eigenschaft des ErrorRecord-Objekts enthält ein RuntimeException-Objekt.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-127">The Exception property of the ErrorRecord object contains a RuntimeException object.</span></span> <span data-ttu-id="5ff0b-128">Der Rest des ErrorRecord-Objekts und das RuntimeException-Objekt variieren mit dem Objekt, das das throw-Schlüsselwort auslöst.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-128">The remainder of the ErrorRecord object and the RuntimeException object vary with the object that the Throw keyword throws.</span></span>

<span data-ttu-id="5ff0b-129">Das RuntimeException-Objekt ist in einem ErrorRecord-Objekt umschließt, und das ErrorRecord-Objekt wird automatisch in der $Error automatischen Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-129">The RunTimeException object is wrapped in an ErrorRecord object, and the ErrorRecord object is automatically saved in the $Error automatic variable.</span></span>

## <a name="using-throw-to-create-a-mandatory-parameter"></a><span data-ttu-id="5ff0b-130">Verwenden von Throw zum Erstellen eines obligatorischen Parameters</span><span class="sxs-lookup"><span data-stu-id="5ff0b-130">Using Throw to create a mandatory parameter</span></span>

<span data-ttu-id="5ff0b-131">Verwenden Sie im Gegensatz zu früheren Versionen von PowerShell nicht das throw-Schlüsselwort für die Parameter Validierung.</span><span class="sxs-lookup"><span data-stu-id="5ff0b-131">Unlike past versions of PowerShell, do not use the Throw keyword for parameter validation.</span></span> <span data-ttu-id="5ff0b-132">Die richtige Vorgehensweise finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) .</span><span class="sxs-lookup"><span data-stu-id="5ff0b-132">See [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) for the correct way.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ff0b-133">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="5ff0b-133">See also</span></span>

- [<span data-ttu-id="5ff0b-134">about_Break</span><span class="sxs-lookup"><span data-stu-id="5ff0b-134">about_Break</span></span>](about_Break.md)
- [<span data-ttu-id="5ff0b-135">about_Continue</span><span class="sxs-lookup"><span data-stu-id="5ff0b-135">about_Continue</span></span>](about_Continue.md)
- [<span data-ttu-id="5ff0b-136">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="5ff0b-136">about_Scopes</span></span>](about_Scopes.md)
- [<span data-ttu-id="5ff0b-137">about_Trap</span><span class="sxs-lookup"><span data-stu-id="5ff0b-137">about_Trap</span></span>](about_Trap.md)
- [<span data-ttu-id="5ff0b-138">about_Try_Catch_Finally</span><span class="sxs-lookup"><span data-stu-id="5ff0b-138">about_Try_Catch_Finally</span></span>](about_Try_Catch_Finally.md)
