---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-expression?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Expression
ms.openlocfilehash: d8f7df3a4c7197b6cf62eecc0b0b314d9668de90
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209700"
---
# <span data-ttu-id="047df-103">Invoke-Expression</span><span class="sxs-lookup"><span data-stu-id="047df-103">Invoke-Expression</span></span>

## <span data-ttu-id="047df-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="047df-104">SYNOPSIS</span></span>
<span data-ttu-id="047df-105">Führt Befehle oder Ausdrücke auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="047df-105">Runs commands or expressions on the local computer.</span></span>

## <span data-ttu-id="047df-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="047df-106">SYNTAX</span></span>

```
Invoke-Expression [-Command] <String> [<CommonParameters>]
```

## <span data-ttu-id="047df-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="047df-107">DESCRIPTION</span></span>

<span data-ttu-id="047df-108">Das `Invoke-Expression` -Cmdlet wertet eine angegebene Zeichenfolge aus oder führt Sie als Befehl aus und gibt die Ergebnisse des Ausdrucks oder Befehls zurück.</span><span class="sxs-lookup"><span data-stu-id="047df-108">The `Invoke-Expression` cmdlet evaluates or runs a specified string as a command and returns the results of the expression or command.</span></span> <span data-ttu-id="047df-109">Ohne `Invoke-Expression` wird eine Zeichenfolge, die in der Befehlszeile übermittelt wird, unverändert zurückgegeben (ECHO).</span><span class="sxs-lookup"><span data-stu-id="047df-109">Without `Invoke-Expression`, a string submitted at the command line is returned (echoed) unchanged.</span></span>

<span data-ttu-id="047df-110">Ausdrücke werden im aktuellen Gültigkeitsbereich ausgewertet und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="047df-110">Expressions are evaluated and run in the current scope.</span></span> <span data-ttu-id="047df-111">Weitere Informationen finden Sie unter [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="047df-111">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="047df-112">Treffen Sie angemessene Vorsichtsmaßnahmen, wenn Sie das `Invoke-Expression` Cmdlet in Skripts verwenden.</span><span class="sxs-lookup"><span data-stu-id="047df-112">Take reasonable precautions when using the `Invoke-Expression` cmdlet in scripts.</span></span> <span data-ttu-id="047df-113">Wenn Sie verwenden, `Invoke-Expression` um einen Befehl auszuführen, den der Benutzer eingibt, vergewissern Sie sich, dass der Befehl sicher ausgeführt werden kann, bevor er ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="047df-113">When using `Invoke-Expression` to run a command that the user enters, verify that the command is safe to run before running it.</span></span> <span data-ttu-id="047df-114">Im Allgemeinen empfiehlt es sich, Ihr Skript mit vordefinierten Eingabeoptionen zu entwerfen, statt die Freihandformeingabe zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="047df-114">In general, it is best to design your script with predefined input options, rather than allowing freeform input.</span></span>

## <span data-ttu-id="047df-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="047df-115">EXAMPLES</span></span>

### <span data-ttu-id="047df-116">Beispiel 1: Auswerten eines Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="047df-116">Example 1: Evaluate an expression</span></span>

```powershell
$Command = "Get-Process"
$Command
```

```Output
Get-Process
```

```powershell
Invoke-Expression $Command
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
296       4       1572       1956    20       0.53     1348   AdtAgent
270       6       1328       800     34       0.06     2396   alg
67        2       620        484     20       0.22     716    ati2evxx
1060      15      12904      11840   74       11.48    892    CcmExec
1400      33      25280      37544   223      38.44    2564   communicator
...
```

<span data-ttu-id="047df-117">In diesem Beispiel wird die Verwendung von `Invoke-Expression` zum Auswerten eines Ausdrucks veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="047df-117">This example demonstrates the use of `Invoke-Expression` to evaluate an expression.</span></span> <span data-ttu-id="047df-118">Ohne `Invoke-Expression` wird der Ausdruck gedruckt, aber nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="047df-118">Without `Invoke-Expression`, the expression is printed, but not evaluated.</span></span>

<span data-ttu-id="047df-119">Der erste Befehl weist `Get-Process` der Variablen den Wert (eine Zeichenfolge) zu `$Command` .</span><span class="sxs-lookup"><span data-stu-id="047df-119">The first command assigns a value of `Get-Process` (a string) to the `$Command` variable.</span></span>

<span data-ttu-id="047df-120">Der zweite Befehl veranschaulicht die Auswirkungen bei der Eingabe des Namens der Variablen in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="047df-120">The second command shows the effect of typing the variable name at the command line.</span></span> <span data-ttu-id="047df-121">PowerShell gibt die Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="047df-121">PowerShell echoes the string.</span></span>

<span data-ttu-id="047df-122">Der dritte Befehl verwendet `Invoke-Expression` , um die Zeichenfolge zu evaluieren.</span><span class="sxs-lookup"><span data-stu-id="047df-122">The third command uses `Invoke-Expression` to evaluate the string.</span></span>

### <span data-ttu-id="047df-123">Beispiel 2: Ausführen eines Skripts auf dem lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="047df-123">Example 2: Run a script on the local computer</span></span>

```powershell
Invoke-Expression -Command "C:\ps-test\testscript.ps1"
"C:\ps-test\testscript.ps1" | Invoke-Expression
```

<span data-ttu-id="047df-124">Diese Befehle verwenden, `Invoke-Expression` um ein Skript, TestScript.ps1, auf dem lokalen Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="047df-124">These commands use `Invoke-Expression` to run a script, TestScript.ps1, on the local computer.</span></span> <span data-ttu-id="047df-125">Die beiden Befehle sind äquivalent.</span><span class="sxs-lookup"><span data-stu-id="047df-125">The two commands are equivalent.</span></span> <span data-ttu-id="047df-126">Der erste verwendet den **Command** -Parameter, um den Befehl anzugeben, der ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="047df-126">The first uses the **Command** parameter to specify the command to run.</span></span>
<span data-ttu-id="047df-127">Der zweite verwendet einen Pipeline Operator ( `|` ), um die Befehls Zeichenfolge an zu senden `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="047df-127">The second uses a pipeline operator (`|`) to send the command string to `Invoke-Expression`.</span></span>

### <span data-ttu-id="047df-128">Beispiel 3: Ausführen eines Befehls in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="047df-128">Example 3: Run a command in a variable</span></span>

```powershell
$Command = 'Get-Process | where {$_.cpu -gt 1000}'
Invoke-Expression $Command
```

<span data-ttu-id="047df-129">In diesem Beispiel wird eine Befehls Zeichenfolge ausgeführt, die in der-Variablen gespeichert ist `$Command` .</span><span class="sxs-lookup"><span data-stu-id="047df-129">This example runs a command string that is saved in the `$Command` variable.</span></span>

<span data-ttu-id="047df-130">Die Befehls Zeichenfolge wird in einfache Anführungszeichen eingeschlossen, da Sie eine Variable enthält, die `$_` das aktuelle Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="047df-130">The command string is enclosed in single quotation marks because it includes a variable, `$_`, which represents the current object.</span></span> <span data-ttu-id="047df-131">Wenn Sie in doppelte Anführungszeichen eingeschlossen `$_` wäre, wird die Variable durch ihren Wert ersetzt, bevor Sie in der Variablen gespeichert wurde `$Command` .</span><span class="sxs-lookup"><span data-stu-id="047df-131">If it were enclosed in double quotation marks, the `$_` variable would be replaced by its value before it was saved in the `$Command` variable.</span></span>

### <span data-ttu-id="047df-132">Beispiel 4: erhalten und Ausführen eines Cmdlet-Hilfe Beispiels</span><span class="sxs-lookup"><span data-stu-id="047df-132">Example 4: Get and run a cmdlet Help example</span></span>

```powershell
$Cmdlet_name = "Get-EventLog"
$Example_number = 1
$Example_code = (Get-Help $Cmdlet_name).examples.example[($Example_number-1)].code
Invoke-Expression $Example_code
```

<span data-ttu-id="047df-133">Dieser Befehl ruft das erste Beispiel im Hilfethema für das Cmdlet ab und führt es aus `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="047df-133">This command retrieves and runs the first example in the `Get-EventLog` cmdlet Help topic.</span></span>

<span data-ttu-id="047df-134">Um ein Beispiel für ein anderes Cmdlet auszuführen, ändern Sie den Wert der `$Cmdlet_name` Variablen in den Namen des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="047df-134">To run an example of a different cmdlet, change the value of the `$Cmdlet_name` variable to the name of the cmdlet.</span></span> <span data-ttu-id="047df-135">Und ändern Sie die `$Example_number` Variable in die Beispiel Zahl, die Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="047df-135">And, change the `$Example_number` variable to the example number you want to run.</span></span> <span data-ttu-id="047df-136">Der Befehl schlägt fehl, wenn die Beispiel Nummer ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="047df-136">The command fails if the example number is not valid.</span></span>

## <span data-ttu-id="047df-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="047df-137">PARAMETERS</span></span>

### <span data-ttu-id="047df-138">-Command</span><span class="sxs-lookup"><span data-stu-id="047df-138">-Command</span></span>

<span data-ttu-id="047df-139">Gibt den auszuführenden Befehl oder Ausdruck an.</span><span class="sxs-lookup"><span data-stu-id="047df-139">Specifies the command or expression to run.</span></span> <span data-ttu-id="047df-140">Geben Sie den Befehl oder Ausdruck oder eine Variable ein, die den Befehl oder Ausdruck enthält.</span><span class="sxs-lookup"><span data-stu-id="047df-140">Type the command or expression or enter a variable that contains the command or expression.</span></span> <span data-ttu-id="047df-141">Der **Command** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="047df-141">The **Command** parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="047df-142">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="047df-142">CommonParameters</span></span>

<span data-ttu-id="047df-143">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="047df-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="047df-144">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="047df-144">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="047df-145">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="047df-145">INPUTS</span></span>

### <span data-ttu-id="047df-146">System. String oder psobject</span><span class="sxs-lookup"><span data-stu-id="047df-146">System.String or PSObject</span></span>

<span data-ttu-id="047df-147">Sie können ein Objekt, das den Befehl darstellt, an die Pipeline übergeben `Invoke-Expression` .</span><span class="sxs-lookup"><span data-stu-id="047df-147">You can pipe an object that represents the command to `Invoke-Expression`.</span></span>
<span data-ttu-id="047df-148">Verwenden `$Input` Sie die automatische Variable, um die Eingabe Objekte im Befehl darzustellen.</span><span class="sxs-lookup"><span data-stu-id="047df-148">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="047df-149">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="047df-149">OUTPUTS</span></span>

### <span data-ttu-id="047df-150">PSObject</span><span class="sxs-lookup"><span data-stu-id="047df-150">PSObject</span></span>

<span data-ttu-id="047df-151">Gibt die Ausgabe zurück, die vom aufgerufenen Befehl (dem Wert des **Befehls** Parameters) generiert wird.</span><span class="sxs-lookup"><span data-stu-id="047df-151">Returns the output that is generated by the invoked command (the value of the **Command** parameter).</span></span>

## <span data-ttu-id="047df-152">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="047df-152">NOTES</span></span>

<span data-ttu-id="047df-153">In den meisten Fällen rufen Sie Ausdrücke mit dem Aufruf Operator von PowerShell auf und erzielen dieselben Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="047df-153">In most cases, you invoke expressions using PowerShell's call operator and achieve the same results.</span></span>
<span data-ttu-id="047df-154">Der "calloperator" ist eine sicherere Methode.</span><span class="sxs-lookup"><span data-stu-id="047df-154">The call operator is a safer method.</span></span> <span data-ttu-id="047df-155">Weitere Informationen finden Sie unter [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span><span class="sxs-lookup"><span data-stu-id="047df-155">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#call-operator-).</span></span>

## <span data-ttu-id="047df-156">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="047df-156">RELATED LINKS</span></span>

[<span data-ttu-id="047df-157">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="047df-157">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="047df-158">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="047df-158">about_Scopes</span></span>](../Microsoft.PowerShell.Core/About/about_Scopes.md)
