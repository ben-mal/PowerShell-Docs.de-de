---
description: Beschreibt, wie Variablen Werte speichern, die in PowerShell verwendet werden können.
Locale: en-US
ms.date: 03/30/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Variables
ms.openlocfilehash: ac5e2a065d7d510c5d3f577b9ff81b35c49b30d2
ms.sourcegitcommit: 4d6ed6f7d747a9bbb3fcfcf6c981c5aa8a973a08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "106072490"
---
# <a name="about-variables"></a><span data-ttu-id="d4a80-103">Informationen zu Variablen</span><span class="sxs-lookup"><span data-stu-id="d4a80-103">About Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="d4a80-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4a80-104">Short description</span></span>

<span data-ttu-id="d4a80-105">Beschreibt, wie Variablen Werte speichern, die in PowerShell verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d4a80-105">Describes how variables store values that can be used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="d4a80-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4a80-106">Long description</span></span>

<span data-ttu-id="d4a80-107">Sie können alle Typen von Werten in PowerShell-Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="d4a80-107">You can store all types of values in PowerShell variables.</span></span> <span data-ttu-id="d4a80-108">Speichern Sie z. b. die Ergebnisse von Befehlen, und speichern Sie Elemente, die in Befehlen und Ausdrücken verwendet werden, wie z. b. Namen, Pfade, Einstellungen und Werte.</span><span class="sxs-lookup"><span data-stu-id="d4a80-108">For example, store the results of commands, and store elements that are used in commands and expressions, such as names, paths, settings, and values.</span></span>

<span data-ttu-id="d4a80-109">Eine Variable ist eine Speichereinheit, in der Werte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d4a80-109">A variable is a unit of memory in which values are stored.</span></span> <span data-ttu-id="d4a80-110">In PowerShell werden Variablen durch Text Zeichenfolgen dargestellt, die mit einem Dollarzeichen ( `$` ) beginnen, z `$a` . b., `$process` oder `$my_var` .</span><span class="sxs-lookup"><span data-stu-id="d4a80-110">In PowerShell, variables are represented by text strings that begin with a dollar sign (`$`), such as `$a`, `$process`, or `$my_var`.</span></span>

<span data-ttu-id="d4a80-111">Bei Variablennamen wird die Groß-/Kleinschreibung nicht beachtet, und Sie können Leerzeichen und Sonderzeichen enthalten</span><span class="sxs-lookup"><span data-stu-id="d4a80-111">Variable names aren't case-sensitive, and can include spaces and special characters.</span></span> <span data-ttu-id="d4a80-112">Variablennamen, die Sonderzeichen und Leerzeichen enthalten, sind jedoch schwer zu verwenden und sollten vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="d4a80-112">But, variable names that include special characters and spaces are difficult to use and should be avoided.</span></span> <span data-ttu-id="d4a80-113">Weitere Informationen finden Sie unter [Variablennamen, die Sonderzeichen enthalten](#variable-names-that-include-special-characters).</span><span class="sxs-lookup"><span data-stu-id="d4a80-113">For more information, see [Variable names that include special characters](#variable-names-that-include-special-characters).</span></span>

<span data-ttu-id="d4a80-114">Es gibt mehrere verschiedene Arten von Variablen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4a80-114">There are several different types of variables in PowerShell.</span></span>

- <span data-ttu-id="d4a80-115">Vom Benutzer erstellte Variablen: vom Benutzer erstellte Variablen werden erstellt und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d4a80-115">User-created variables: User-created variables are created and maintained by the user.</span></span> <span data-ttu-id="d4a80-116">Standardmäßig existieren die Variablen, die Sie in der PowerShell-Befehlszeile erstellen, nur, während das PowerShell-Fenster geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="d4a80-116">By default, the variables that you create at the PowerShell command line exist only while the PowerShell window is open.</span></span> <span data-ttu-id="d4a80-117">Wenn das PowerShell-Fenster geschlossen wird, werden die Variablen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d4a80-117">When the PowerShell windows is closed, the variables are deleted.</span></span> <span data-ttu-id="d4a80-118">Um eine Variable zu speichern, fügen Sie Sie Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="d4a80-118">To save a variable, add it to your PowerShell profile.</span></span> <span data-ttu-id="d4a80-119">Sie können auch Variablen in Skripts mit dem globalen, Skript-oder lokalen Gültigkeitsbereich erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-119">You can also create variables in scripts with global, script, or local scope.</span></span>

- <span data-ttu-id="d4a80-120">Automatische Variablen: automatische Variablen speichern den Status von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4a80-120">Automatic variables: Automatic variables store the state of PowerShell.</span></span> <span data-ttu-id="d4a80-121">Diese Variablen werden von PowerShell erstellt, und PowerShell ändert ihre Werte nach Bedarf, um Ihre Genauigkeit beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="d4a80-121">These variables are created by PowerShell, and PowerShell changes their values as required to maintain their accuracy.</span></span> <span data-ttu-id="d4a80-122">Benutzer können den Wert dieser Variablen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="d4a80-122">Users can't change the value of these variables.</span></span> <span data-ttu-id="d4a80-123">Die `$PSHOME` Variable speichert beispielsweise den Pfad zum PowerShell-Installationsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d4a80-123">For example, the `$PSHOME` variable stores the path to the PowerShell installation directory.</span></span>

  <span data-ttu-id="d4a80-124">Weitere Informationen, eine Liste und eine Beschreibung der automatischen Variablen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d4a80-124">For more information, a list, and a description of the automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="d4a80-125">Einstellungs Variablen: Einstellungs Variablen speichern Benutzereinstellungen für PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4a80-125">Preference variables: Preference variables store user preferences for PowerShell.</span></span> <span data-ttu-id="d4a80-126">Diese Variablen werden von PowerShell erstellt und mit Standardwerten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d4a80-126">These variables are created by PowerShell and are populated with default values.</span></span> <span data-ttu-id="d4a80-127">Benutzer können die Werte dieser Variablen ändern.</span><span class="sxs-lookup"><span data-stu-id="d4a80-127">Users can change the values of these variables.</span></span> <span data-ttu-id="d4a80-128">Beispielsweise legt die- `$MaximumHistoryCount` Variable die maximale Anzahl von Einträgen im Sitzungsverlauf fest.</span><span class="sxs-lookup"><span data-stu-id="d4a80-128">For example, the `$MaximumHistoryCount` variable determines the maximum number of entries in the session history.</span></span>

  <span data-ttu-id="d4a80-129">Weitere Informationen, eine Liste und eine Beschreibung der Einstellungs Variablen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d4a80-129">For more information, a list, and a description of the preference variables, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="working-with-variables"></a><span data-ttu-id="d4a80-130">Arbeiten mit Variablen</span><span class="sxs-lookup"><span data-stu-id="d4a80-130">Working with variables</span></span>

<span data-ttu-id="d4a80-131">Um eine neue Variable zu erstellen, verwenden Sie eine Zuweisungsanweisung, um der Variablen einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-131">To create a new variable, use an assignment statement to assign a value to the variable.</span></span> <span data-ttu-id="d4a80-132">Sie müssen die Variable nicht deklarieren, bevor Sie Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4a80-132">You don't have to declare the variable before using it.</span></span> <span data-ttu-id="d4a80-133">Der Standardwert aller Variablen ist `$null` .</span><span class="sxs-lookup"><span data-stu-id="d4a80-133">The default value of all variables is `$null`.</span></span>

<span data-ttu-id="d4a80-134">Geben Sie ein, um eine Liste aller Variablen in der PowerShell-Sitzung zu erhalten `Get-Variable` .</span><span class="sxs-lookup"><span data-stu-id="d4a80-134">To get a list of all the variables in your PowerShell session, type `Get-Variable`.</span></span> <span data-ttu-id="d4a80-135">Die Variablennamen werden ohne das vorangehende Dollar `$` Zeichen () angezeigt, das für den Verweis auf Variablen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4a80-135">The variable names are displayed without the preceding dollar (`$`) sign that is used to reference variables.</span></span>

<span data-ttu-id="d4a80-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a80-136">For example:</span></span>

```powershell
$MyVariable = 1, 2, 3

$Path = "C:\Windows\System32"
```

<span data-ttu-id="d4a80-137">Variablen sind nützlich, um die Ergebnisse von Befehlen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d4a80-137">Variables are useful for storing the results of commands.</span></span>

<span data-ttu-id="d4a80-138">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a80-138">For example:</span></span>

```powershell
$Processes = Get-Process

$Today = (Get-Date).DateTime
```

<span data-ttu-id="d4a80-139">Wenn Sie den Wert einer Variablen anzeigen möchten, geben Sie den Variablennamen ein, dem ein Dollarzeichen () vorangestellt ist `$` .</span><span class="sxs-lookup"><span data-stu-id="d4a80-139">To display the value of a variable, type the variable name, preceded by a dollar sign (`$`).</span></span>

<span data-ttu-id="d4a80-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a80-140">For example:</span></span>

```powershell
$MyVariable
```

```Output
1
2
3
```

```powershell
$Today
```

```Output
Tuesday, September 3, 2019 09:46:46
```

<span data-ttu-id="d4a80-141">Um den Wert einer Variablen zu ändern, weisen Sie der Variablen einen neuen Wert zu.</span><span class="sxs-lookup"><span data-stu-id="d4a80-141">To change the value of a variable, assign a new value to the variable.</span></span>

<span data-ttu-id="d4a80-142">In den folgenden Beispielen wird der Wert der- `$MyVariable` Variablen angezeigt, der Wert der-Variablen geändert und dann der neue Wert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4a80-142">The following examples display the value of the `$MyVariable` variable, changes the value of the variable, and then displays the new value.</span></span>

```powershell
$MyVariable = 1, 2, 3
$MyVariable
```

```Output
1
2
3
```

```powershell
$MyVariable = "The green cat."
$MyVariable
```

```Output
The green cat.
```

<span data-ttu-id="d4a80-143">Um den Wert einer Variablen zu löschen, verwenden Sie das- `Clear-Variable` Cmdlet, oder ändern Sie den Wert in `$null` .</span><span class="sxs-lookup"><span data-stu-id="d4a80-143">To delete the value of a variable, use the `Clear-Variable` cmdlet or change the value to `$null`.</span></span>

```powershell
Clear-Variable -Name MyVariable
```

```powershell
$MyVariable = $null
```

<span data-ttu-id="d4a80-144">Um die Variable zu löschen, verwenden Sie [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) oder [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span><span class="sxs-lookup"><span data-stu-id="d4a80-144">To delete the variable, use [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) or [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span></span>

```powershell
Remove-Variable -Name MyVariable
```

```powershell
Remove-Item -Path Variable:\MyVariable
```

<span data-ttu-id="d4a80-145">Es ist auch möglich, mit einer Anweisung mehrere Variablen zu Werten.</span><span class="sxs-lookup"><span data-stu-id="d4a80-145">It is also possible to values to multiple variables with one statement.</span></span> <span data-ttu-id="d4a80-146">In den folgenden Beispielen wird der gleiche Wert mehreren Variablen zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="d4a80-146">The following examples assigns the same value to multiple variables:</span></span>

```powershell
$a = $b = $c = 0
```

<span data-ttu-id="d4a80-147">Im nächsten Beispiel werden mehrere Werte mehreren Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-147">The next example assigns multiple values to multiple variables.</span></span>

```powershell
$i,$j,$k = 10, "red", $true    # $i is 10, $j is "red", $k is True
$i,$j = 10, "red", $true       # $i is 10, $j is [object[]], Length 2
```

<span data-ttu-id="d4a80-148">Ausführlichere Informationen finden Sie im Abschnitt **zuweisen mehrerer Variablen** [about_Assignment_Operators](about_assignment_operators.md#assigning-multiple-variables).</span><span class="sxs-lookup"><span data-stu-id="d4a80-148">For more detailed information, see the **Assigning multiple variables** section of [about_Assignment_Operators](about_assignment_operators.md#assigning-multiple-variables).</span></span>

## <a name="types-of-variables"></a><span data-ttu-id="d4a80-149">Typen von Variablen</span><span class="sxs-lookup"><span data-stu-id="d4a80-149">Types of variables</span></span>

<span data-ttu-id="d4a80-150">Sie können beliebige Objekttypen in einer Variablen speichern, einschließlich Ganzzahlen, Zeichen folgen, Arrays und Hash Tabellen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-150">You can store any type of object in a variable, including integers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="d4a80-151">Und,-Objekte, die Prozesse, Dienste, Ereignisprotokolle und Computer darstellen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-151">And, objects that represent processes, services, event logs, and computers.</span></span>

<span data-ttu-id="d4a80-152">PowerShell-Variablen sind lose typisiert, was bedeutet, dass Sie nicht auf einen bestimmten Objekttyp beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="d4a80-152">PowerShell variables are loosely typed, which means that they aren't limited to a particular type of object.</span></span> <span data-ttu-id="d4a80-153">Eine einzelne Variable kann sogar eine Auflistung oder ein Array von unterschiedlichen Objekttypen gleichzeitig enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4a80-153">A single variable can even contain a collection, or array, of different types of objects at the same time.</span></span>

<span data-ttu-id="d4a80-154">Der Datentyp einer Variablen wird durch die .NET-Typen der Werte der Variablen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d4a80-154">The data type of a variable is determined by the .NET types of the values of the variable.</span></span> <span data-ttu-id="d4a80-155">Verwenden [Sie Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member), um den Objekttyp einer Variablen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-155">To view a variable's object type, use [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).</span></span>

<span data-ttu-id="d4a80-156">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4a80-156">For example:</span></span>

```powershell
$a = 12                         # System.Int32
$a = "Word"                     # System.String
$a = 12, "Word"                 # array of System.Int32, System.String
$a = Get-ChildItem C:\Windows   # FileInfo and DirectoryInfo types
```

<span data-ttu-id="d4a80-157">Sie können ein Type-Attribut und eine Cast Notation verwenden, um sicherzustellen, dass eine Variable nur bestimmte Objekttypen oder Objekte enthalten kann, die in diesen Typ konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="d4a80-157">You can use a type attribute and cast notation to ensure that a variable can contain only specific object types or objects that can be converted to that type.</span></span> <span data-ttu-id="d4a80-158">Wenn Sie versuchen, einen Wert eines anderen Typs zuzuweisen, versucht PowerShell, den Wert in seinen Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d4a80-158">If you try to assign a value of another type, PowerShell tries to convert the value to its type.</span></span> <span data-ttu-id="d4a80-159">Wenn der Typ nicht konvertiert werden kann, schlägt die Zuweisungsanweisung fehl.</span><span class="sxs-lookup"><span data-stu-id="d4a80-159">If the type can't be converted, the assignment statement fails.</span></span>

<span data-ttu-id="d4a80-160">Um Cast Notation zu verwenden, geben Sie vor dem Variablennamen (auf der linken Seite der Zuweisungsanweisung) einen Typnamen ein, der in Klammern eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d4a80-160">To use cast notation, enter a type name, enclosed in brackets, before the variable name (on the left side of the assignment statement).</span></span> <span data-ttu-id="d4a80-161">Im folgenden Beispiel wird eine `$number` Variable erstellt, die nur ganze Zahlen enthalten kann, eine `$words` Variable, die nur Zeichen folgen enthalten kann, und eine `$dates` Variable, die nur **DateTime** -Objekte enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="d4a80-161">The following example creates a `$number` variable that can contain only integers, a `$words` variable that can contain only strings, and a `$dates` variable that can contain only **DateTime** objects.</span></span>

```powershell
[int]$number = 8
$number = "12345"  # The string is converted to an integer.
$number = "Hello"
```

```Output
Cannot convert value "Hello" to type "System.Int32". Error: "Input string was
 not in a correct format."
At line:1 char:1
+ $number = "Hello"
+ ~~~~~~~~~~~~~~~~~
+ CategoryInfo          : MetadataError: (:) [],
    ArgumentTransformationMetadataException
+ FullyQualifiedErrorId : RuntimeException
```

```powershell
[string]$words = "Hello"
$words = 2       # The integer is converted to a string.
$words += 10     # The plus (+) sign concatenates the strings.
$words
```

```Output
210
```

```powershell
[datetime] $dates = "09/12/91"  # The string is converted to a DateTime object.
$dates
```

```Output
Thursday, September 12, 1991 00:00:00
```

```powershell
$dates = 10    # The integer is converted to a DateTime object.
$dates
```

```Output
Monday, January 1, 0001 00:00:00
```

## <a name="using-variables-in-commands-and-expressions"></a><span data-ttu-id="d4a80-162">Verwenden von Variablen in Befehlen und Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="d4a80-162">Using variables in commands and expressions</span></span>

<span data-ttu-id="d4a80-163">Wenn Sie eine Variable in einem Befehl oder Ausdruck verwenden möchten, geben Sie den Variablennamen ein, dem das Dollarzeichen () vorangestellt ist `$` .</span><span class="sxs-lookup"><span data-stu-id="d4a80-163">To use a variable in a command or expression, type the variable name, preceded by the dollar (`$`) sign.</span></span>

<span data-ttu-id="d4a80-164">Wenn der Variablenname und das Dollarzeichen nicht in Anführungszeichen eingeschlossen sind oder wenn Sie in doppelte Anführungszeichen ( `"` ) eingeschlossen sind, wird der Wert der Variablen im Befehl oder Ausdruck verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4a80-164">If the variable name and dollar sign aren't enclosed in quotation marks, or if they're enclosed in double quotation (`"`) marks, the value of the variable is used in the command or expression.</span></span>

<span data-ttu-id="d4a80-165">Wenn der Variablenname und das Dollarzeichen in einfache Anführungszeichen ( `'` ) eingeschlossen sind, wird der Variablenname im Ausdruck verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4a80-165">If the variable name and dollar sign are enclosed in single quotation (`'`) marks, the variable name is used in the expression.</span></span>

<span data-ttu-id="d4a80-166">Weitere Informationen zum Verwenden von Anführungszeichen in PowerShell finden Sie unter [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="d4a80-166">For more information about using quotation marks in PowerShell, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

<span data-ttu-id="d4a80-167">In diesem Beispiel wird der Wert der- `$PROFILE` Variablen abgerufen, d. h. der Pfad zur PowerShell-Benutzerprofil Datei in der PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="d4a80-167">This example gets the value of the `$PROFILE` variable, which is the path to the PowerShell user profile file in the PowerShell console.</span></span>

```powershell
$PROFILE
```

```Output
C:\Users\User01\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
```

<span data-ttu-id="d4a80-168">In diesem Beispiel werden zwei Befehle angezeigt, die das PowerShell-Profil in **notepad.exe** öffnen können.</span><span class="sxs-lookup"><span data-stu-id="d4a80-168">In this example, two commands are shown that can open the PowerShell profile in **notepad.exe**.</span></span> <span data-ttu-id="d4a80-169">Im Beispiel mit doppelten Anführungszeichen ( `"` ) wird der Wert der Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4a80-169">The example with double-quote (`"`) marks uses the variable's value.</span></span>

```powershell
notepad $PROFILE

notepad "$PROFILE"
```

<span data-ttu-id="d4a80-170">In den folgenden Beispielen werden einfache Anführungs `'` Zeichen () verwendet, mit denen die Variable als Literaltext behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="d4a80-170">The following examples use single-quote (`'`) marks that treat the variable as literal text.</span></span>

```powershell
'$PROFILE'
```

```Output
$PROFILE
```

```powershell
'Use the $PROFILE variable.'
```

```Output
Use the $PROFILE variable.
```

## <a name="variable-names-that-include-special-characters"></a><span data-ttu-id="d4a80-171">Variablennamen, die Sonderzeichen enthalten</span><span class="sxs-lookup"><span data-stu-id="d4a80-171">Variable names that include special characters</span></span>

<span data-ttu-id="d4a80-172">Variablennamen beginnen mit einem Dollar `$` Zeichen () und können alphanumerische Zeichen und Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4a80-172">Variable names begin with a dollar (`$`) sign and can include alphanumeric characters and special characters.</span></span> <span data-ttu-id="d4a80-173">Die Länge des Variablen namens ist nur durch den verfügbaren Arbeitsspeicher beschränkt.</span><span class="sxs-lookup"><span data-stu-id="d4a80-173">The variable name length is limited only by available memory.</span></span>

<span data-ttu-id="d4a80-174">Die bewährte Vorgehensweise besteht darin, dass Variablennamen nur alphanumerische Zeichen und den Unterstrich ( `_` ) enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4a80-174">The best practice is that variable names include only alphanumeric characters and the underscore (`_`) character.</span></span> <span data-ttu-id="d4a80-175">Variablennamen, die Leerzeichen und andere Sonderzeichen enthalten, sind schwer zu verwenden und sollten vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="d4a80-175">Variable names that include spaces and other special characters, are difficult to use and should be avoided.</span></span>

<span data-ttu-id="d4a80-176">Alphanumerische Variablennamen können folgende Zeichen enthalten:</span><span class="sxs-lookup"><span data-stu-id="d4a80-176">Alphanumeric variable names can contain these characters:</span></span>

- <span data-ttu-id="d4a80-177">Unicode-Zeichen aus diesen Kategorien: **lu**, **ll**, **lt**, **LM**, **Lo** oder **ND**.</span><span class="sxs-lookup"><span data-stu-id="d4a80-177">Unicode characters from these categories: **Lu**, **Ll**, **Lt**, **Lm**, **Lo**, or **Nd**.</span></span>
- <span data-ttu-id="d4a80-178">Unterstrich ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="d4a80-178">Underscore (`_`) character.</span></span>
- <span data-ttu-id="d4a80-179">Fragezeichen ( `?` ).</span><span class="sxs-lookup"><span data-stu-id="d4a80-179">Question mark (`?`) character.</span></span>

<span data-ttu-id="d4a80-180">Die folgende Liste enthält die Beschreibungen der Unicode-Kategorie.</span><span class="sxs-lookup"><span data-stu-id="d4a80-180">The following list contains the Unicode category descriptions.</span></span> <span data-ttu-id="d4a80-181">Weitere Informationen finden Sie unter [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span><span class="sxs-lookup"><span data-stu-id="d4a80-181">For more information, see [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span></span>

- <span data-ttu-id="d4a80-182">**Lu** -UppercaseLetter</span><span class="sxs-lookup"><span data-stu-id="d4a80-182">**Lu** - UppercaseLetter</span></span>
- <span data-ttu-id="d4a80-183">**Ll** -LowercaseLetter</span><span class="sxs-lookup"><span data-stu-id="d4a80-183">**Ll** - LowercaseLetter</span></span>
- <span data-ttu-id="d4a80-184">**Lt** -TitlecaseLetter</span><span class="sxs-lookup"><span data-stu-id="d4a80-184">**Lt** - TitlecaseLetter</span></span>
- <span data-ttu-id="d4a80-185">**LM** -ModifierLetter</span><span class="sxs-lookup"><span data-stu-id="d4a80-185">**Lm** - ModifierLetter</span></span>
- <span data-ttu-id="d4a80-186">**Lo** -OtherLetter</span><span class="sxs-lookup"><span data-stu-id="d4a80-186">**Lo** - OtherLetter</span></span>
- <span data-ttu-id="d4a80-187">**ND** -DecimalDigitNumber</span><span class="sxs-lookup"><span data-stu-id="d4a80-187">**Nd** - DecimalDigitNumber</span></span>

<span data-ttu-id="d4a80-188">Um einen Variablennamen zu erstellen oder anzuzeigen, der Leerzeichen oder Sonderzeichen enthält, schließen Sie den Variablennamen in die geschweiften Klammern ( `{}` ) ein.</span><span class="sxs-lookup"><span data-stu-id="d4a80-188">To create or display a variable name that includes spaces or special characters, enclose the variable name with the curly braces (`{}`) characters.</span></span>
<span data-ttu-id="d4a80-189">Die geschweiften Klammern leiten PowerShell ein, um die Zeichen des Variablen namens als Literale zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="d4a80-189">The curly braces direct PowerShell to interpret the variable name's characters as literals.</span></span>

<span data-ttu-id="d4a80-190">Variablennamen mit Sonderzeichen können folgende Zeichen enthalten:</span><span class="sxs-lookup"><span data-stu-id="d4a80-190">Special character variable names can contain these characters:</span></span>

- <span data-ttu-id="d4a80-191">Ein beliebiges Unicode-Zeichen mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="d4a80-191">Any Unicode character, with the following exceptions:</span></span>
  - <span data-ttu-id="d4a80-192">Das schließende geschweifte Klammer `}` Zeichen () (U + 007d).</span><span class="sxs-lookup"><span data-stu-id="d4a80-192">The closing curly brace (`}`) character (U+007D).</span></span>
  - <span data-ttu-id="d4a80-193">Das Graviszeichen ( `` ` `` )-Zeichen (U + 0060).</span><span class="sxs-lookup"><span data-stu-id="d4a80-193">The backtick (`` ` ``) character (U+0060).</span></span> <span data-ttu-id="d4a80-194">Mit dem Graviszeichen werden Unicode-Zeichen mit Escapezeichen versehen, sodass Sie als Literale behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="d4a80-194">The backtick is used to escape Unicode characters so they're treated as literals.</span></span>

<span data-ttu-id="d4a80-195">PowerShell verfügt über reservierte Variablen `$$` , wie z `$?` . b.,, und, `$^` `$_` die alphanumerische Zeichen und Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4a80-195">PowerShell has reserved variables such as `$$`, `$?`, `$^`, and `$_` that contain alphanumeric and special characters.</span></span> <span data-ttu-id="d4a80-196">Weitere Informationen finden Sie unter [about_Automatic_Variables](about_automatic_variables.md).</span><span class="sxs-lookup"><span data-stu-id="d4a80-196">For more information, see [about_Automatic_Variables](about_automatic_variables.md).</span></span>

<span data-ttu-id="d4a80-197">Der folgende Befehl erstellt beispielsweise die-Variable mit dem Namen `save-items` .</span><span class="sxs-lookup"><span data-stu-id="d4a80-197">For example, the following command creates the variable named `save-items`.</span></span> <span data-ttu-id="d4a80-198">Die geschweiften Klammern ( `{}` ) sind erforderlich, da der Variablenname ein Bindestrich ( `-` )-Sonderzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="d4a80-198">The curly braces (`{}`) are needed because variable name includes a hyphen (`-`) special character.</span></span>

```powershell
${save-items} = "a", "b", "c"
${save-items}
```

```Output
a
b
c
```

<span data-ttu-id="d4a80-199">Der folgende Befehl ruft die untergeordneten Elemente in dem Verzeichnis ab, das durch die `ProgramFiles(x86)` Umgebungsvariable dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d4a80-199">The following command gets the child items in the directory that is represented by the `ProgramFiles(x86)` environment variable.</span></span>

```powershell
Get-ChildItem ${env:ProgramFiles(x86)}
```

<span data-ttu-id="d4a80-200">Um auf einen Variablennamen zu verweisen, der geschweifte Klammern enthält, schließen Sie den Variablennamen in geschweifte Klammern ein, und verwenden Sie das Graviszeichen-Zeichen, um die Klammern zu</span><span class="sxs-lookup"><span data-stu-id="d4a80-200">To reference a variable name that includes braces, enclose the variable name in braces, and use the backtick character to escape the braces.</span></span> <span data-ttu-id="d4a80-201">So erstellen Sie z. b. eine Variable namens `this{value}is` Type:</span><span class="sxs-lookup"><span data-stu-id="d4a80-201">For example, to create a variable named `this{value}is` type:</span></span>

```powershell
${this`{value`}is} = "This variable name uses braces and backticks."
${this`{value`}is}
```

```Output
This variable name uses braces and backticks.
```

## <a name="variables-and-scope"></a><span data-ttu-id="d4a80-202">Variablen und Bereich</span><span class="sxs-lookup"><span data-stu-id="d4a80-202">Variables and scope</span></span>

<span data-ttu-id="d4a80-203">Standardmäßig sind Variablen nur in dem Bereich verfügbar, in dem Sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d4a80-203">By default, variables are only available in the scope in which they're created.</span></span>

<span data-ttu-id="d4a80-204">Beispielsweise ist eine Variable, die Sie in einer Funktion erstellen, nur innerhalb der-Funktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d4a80-204">For example, a variable that you create in a function is available only within the function.</span></span> <span data-ttu-id="d4a80-205">Eine Variable, die Sie in einem Skript erstellen, ist nur innerhalb des Skripts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d4a80-205">A variable that you create in a script is available only within the script.</span></span> <span data-ttu-id="d4a80-206">Wenn Sie das Skript mit einem Punkt versehen, wird die Variable dem aktuellen Gültigkeitsbereich hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d4a80-206">If you dot-source the script, the variable is added to the current scope.</span></span> <span data-ttu-id="d4a80-207">Weitere Informationen finden Sie unter [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="d4a80-207">For more information, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="d4a80-208">Sie können einen bereichsmodifizierer verwenden, um den Standardbereich der Variablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d4a80-208">You can use a scope modifier to change the default scope of the variable.</span></span> <span data-ttu-id="d4a80-209">Der folgende Ausdruck erstellt eine Variable mit dem Namen `Computers` .</span><span class="sxs-lookup"><span data-stu-id="d4a80-209">The following expression creates a variable named `Computers`.</span></span> <span data-ttu-id="d4a80-210">Die Variable verfügt über einen globalen Gültigkeitsbereich, auch wenn Sie in einem Skript oder einer Funktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d4a80-210">The variable has a global scope, even when it's created in a script or function.</span></span>

```powershell
$Global:Computers = "Server01"
```

<span data-ttu-id="d4a80-211">Für Skripts oder Befehle, die außerhalb der Sitzung ausgeführt werden, müssen Sie den bereichsmodifizierer `Using` zum Einbetten von Variablen Werten aus dem aufrufenden Sitzungs Bereich benötigen, damit der Sitzungscode darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d4a80-211">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span>

<span data-ttu-id="d4a80-212">Weitere Informationen finden Sie unter [about_Remote_Variables](about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d4a80-212">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="saving-variables"></a><span data-ttu-id="d4a80-213">Speichern von Variablen</span><span class="sxs-lookup"><span data-stu-id="d4a80-213">Saving variables</span></span>

<span data-ttu-id="d4a80-214">Die von Ihnen erstellten Variablen sind nur in der Sitzung verfügbar, in der Sie Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-214">Variables that you create are available only in the session in which you create them.</span></span> <span data-ttu-id="d4a80-215">Sie gehen verloren, wenn Sie die Sitzung schließen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-215">They're lost when you close your session.</span></span>

<span data-ttu-id="d4a80-216">Um die Variable in jeder PowerShell-Sitzung zu erstellen, die Sie starten, fügen Sie die Variable Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="d4a80-216">To create the variable in every PowerShell session that you start, add the variable to your PowerShell profile.</span></span>

<span data-ttu-id="d4a80-217">Fügen Sie z. b. den folgenden Befehl in das PowerShell-Profil ein, um den Wert der `$VerbosePreference` Variablen in jeder PowerShell-Sitzung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d4a80-217">For example, to change the value of the `$VerbosePreference` variable in every PowerShell session, add the following command to your PowerShell profile.</span></span>

```powershell
$VerbosePreference = "Continue"
```

<span data-ttu-id="d4a80-218">Sie können diesen Befehl zu Ihrem PowerShell-Profil hinzufügen, indem Sie die `$PROFILE` Datei in einem Text-Editor öffnen, z. b. **notepad.exe**.</span><span class="sxs-lookup"><span data-stu-id="d4a80-218">You can add this command to your PowerShell profile by opening the `$PROFILE` file in a text editor, such as **notepad.exe**.</span></span> <span data-ttu-id="d4a80-219">Weitere Informationen zu PowerShell-Profilen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d4a80-219">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="the-variable-drive"></a><span data-ttu-id="d4a80-220">Das Variable:-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="d4a80-220">The Variable: drive</span></span>

<span data-ttu-id="d4a80-221">Der PowerShell-Variablen Anbieter erstellt ein `Variable:` Laufwerk, das wie ein Dateisystem Laufwerk aussieht und verhält, aber die Variablen in der Sitzung und deren Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="d4a80-221">The PowerShell Variable provider creates a `Variable:` drive that looks and acts like a file system drive, but it contains the variables in your session and their values.</span></span>

<span data-ttu-id="d4a80-222">Verwenden Sie den folgenden Befehl, um zum Laufwerk zu wechseln `Variable:` :</span><span class="sxs-lookup"><span data-stu-id="d4a80-222">To change to the `Variable:` drive, use the following command:</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="d4a80-223">Um die Elemente und Variablen im Laufwerk aufzulisten `Variable:` , verwenden Sie die `Get-Item` `Get-ChildItem` Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="d4a80-223">To list the items and variables in the `Variable:` drive, use the `Get-Item` or `Get-ChildItem` cmdlets.</span></span>

```powershell
Get-ChildItem Variable:
```

<span data-ttu-id="d4a80-224">Um den Wert einer bestimmten Variablen zu erhalten, geben Sie mit der Dateisystem Notation den Namen des Laufwerks und den Namen der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="d4a80-224">To get the value of a particular variable, use file system notation to specify the name of the drive and the name of the variable.</span></span> <span data-ttu-id="d4a80-225">Um z. b. die `$PSCulture` Automatische Variable zu erhalten, verwenden Sie den folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="d4a80-225">For example, to get the `$PSCulture` automatic variable, use the following command.</span></span>

```powershell
Get-Item Variable:\PSCulture
```

```Output
Name                           Value
----                           -----
PSCulture                      en-US
```

<span data-ttu-id="d4a80-226">Geben Sie Folgendes ein, um weitere Informationen zum `Variable:` Laufwerk und zum PowerShell-Variablen Anbieter anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d4a80-226">To display more information about the `Variable:` drive and the PowerShell Variable provider, type:</span></span>

```powershell
Get-Help Variable
```

## <a name="variable-syntax-with-provider-paths"></a><span data-ttu-id="d4a80-227">Variablen Syntax mit Anbieter Pfaden</span><span class="sxs-lookup"><span data-stu-id="d4a80-227">Variable syntax with provider paths</span></span>

<span data-ttu-id="d4a80-228">Sie können einem Anbieter Pfad das Dollarzeichen () als Präfix voranstellen `$` und auf den Inhalt eines beliebigen Anbieters zugreifen, der die [icontentcmdletprovider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="d4a80-228">You can prefix a provider path with the dollar (`$`) sign, and access the content of any provider that implements the [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) interface.</span></span>

<span data-ttu-id="d4a80-229">Die folgenden integrierten PowerShell-Anbieter unterstützen diese Notation:</span><span class="sxs-lookup"><span data-stu-id="d4a80-229">The following built-in PowerShell providers support this notation:</span></span>

- [<span data-ttu-id="d4a80-230">about_Environment_Provider</span><span class="sxs-lookup"><span data-stu-id="d4a80-230">about_Environment_Provider</span></span>](about_Environment_Provider.md)
- [<span data-ttu-id="d4a80-231">about_Variable_Provider</span><span class="sxs-lookup"><span data-stu-id="d4a80-231">about_Variable_Provider</span></span>](about_Variable_Provider.md)
- [<span data-ttu-id="d4a80-232">about_Function_Provider</span><span class="sxs-lookup"><span data-stu-id="d4a80-232">about_Function_Provider</span></span>](about_Function_Provider.md)
- [<span data-ttu-id="d4a80-233">about_Alias_Provider</span><span class="sxs-lookup"><span data-stu-id="d4a80-233">about_Alias_Provider</span></span>](about_Alias_Provider.md)

## <a name="the-variable-cmdlets"></a><span data-ttu-id="d4a80-234">Die Variablen-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d4a80-234">The variable cmdlets</span></span>

<span data-ttu-id="d4a80-235">PowerShell umfasst einen Satz von Cmdlets, die zum Verwalten von Variablen entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="d4a80-235">PowerShell includes a set of cmdlets that are designed to manage variables.</span></span>

<span data-ttu-id="d4a80-236">Geben Sie Folgendes ein, um die Cmdlets aufzulisten:</span><span class="sxs-lookup"><span data-stu-id="d4a80-236">To list the cmdlets, type:</span></span>

```powershell
Get-Command -Noun Variable
```

<span data-ttu-id="d4a80-237">Um Hilfe zu einem bestimmten Cmdlet zu erhalten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d4a80-237">To get help for a specific cmdlet, type:</span></span>

```powershell
Get-Help <cmdlet-name>
```

| <span data-ttu-id="d4a80-238">Cmdlet-Name</span><span class="sxs-lookup"><span data-stu-id="d4a80-238">Cmdlet Name</span></span>       | <span data-ttu-id="d4a80-239">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4a80-239">Description</span></span>                                |
| ---------------   | ------------------------------------------ |
| `Clear-Variable`  | <span data-ttu-id="d4a80-240">Löscht den Wert einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-240">Deletes the value of a variable.</span></span>           |
| `Get-Variable`    | <span data-ttu-id="d4a80-241">Ruft die Variablen in der aktuellen Konsole ab.</span><span class="sxs-lookup"><span data-stu-id="d4a80-241">Gets the variables in the current console.</span></span> |
| `New-Variable`    | <span data-ttu-id="d4a80-242">Erstellt eine neue Variable.</span><span class="sxs-lookup"><span data-stu-id="d4a80-242">Creates a new variable.</span></span>                    |
| `Remove-Variable` | <span data-ttu-id="d4a80-243">Löscht eine Variable und ihren Wert.</span><span class="sxs-lookup"><span data-stu-id="d4a80-243">Deletes a variable and its value.</span></span>          |
| `Set-Variable`    | <span data-ttu-id="d4a80-244">Ändert den Wert einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="d4a80-244">Changes the value of a variable.</span></span>           |

## <a name="see-also"></a><span data-ttu-id="d4a80-245">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4a80-245">See also</span></span>

[<span data-ttu-id="d4a80-246">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="d4a80-246">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="d4a80-247">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="d4a80-247">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="d4a80-248">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="d4a80-248">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="d4a80-249">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="d4a80-249">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="d4a80-250">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="d4a80-250">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="d4a80-251">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="d4a80-251">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="d4a80-252">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="d4a80-252">about_Remote_Variables</span></span>](about_Remote_Variables.md)
