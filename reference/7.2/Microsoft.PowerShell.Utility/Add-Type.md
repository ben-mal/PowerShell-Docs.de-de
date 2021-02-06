---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: d55925b0580542459e62e60108f855508232f232
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599432"
---
# <span data-ttu-id="64297-102">Add-Type</span><span class="sxs-lookup"><span data-stu-id="64297-102">Add-Type</span></span>

## <span data-ttu-id="64297-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="64297-103">SYNOPSIS</span></span>
<span data-ttu-id="64297-104">Fügt einer PowerShell-Sitzung eine Microsoft .net Core-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="64297-104">Adds a Microsoft .NET Core class to a PowerShell session.</span></span>

## <span data-ttu-id="64297-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="64297-105">SYNTAX</span></span>

### <span data-ttu-id="64297-106">Fromsource (Standard)</span><span class="sxs-lookup"><span data-stu-id="64297-106">FromSource (Default)</span></span>

```
Add-Type [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="64297-107">Frommember</span><span class="sxs-lookup"><span data-stu-id="64297-107">FromMember</span></span>

```
Add-Type [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>]
 [-UsingNamespace <String[]>] [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="64297-108">Frompath</span><span class="sxs-lookup"><span data-stu-id="64297-108">FromPath</span></span>

```
Add-Type [-Path] <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="64297-109">Fromliteralpath</span><span class="sxs-lookup"><span data-stu-id="64297-109">FromLiteralPath</span></span>

```
Add-Type -LiteralPath <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="64297-110">Fromassemblyname</span><span class="sxs-lookup"><span data-stu-id="64297-110">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="64297-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="64297-111">DESCRIPTION</span></span>

<span data-ttu-id="64297-112">Mit dem- `Add-Type` Cmdlet können Sie in ihrer PowerShell-Sitzung eine Microsoft .net Core-Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="64297-112">The `Add-Type` cmdlet lets you define a Microsoft .NET Core class in your PowerShell session.</span></span> <span data-ttu-id="64297-113">Anschließend können Sie Objekte mit dem `New-Object` Cmdlet instanziieren und die Objekte wie jedes beliebige .net Core-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="64297-113">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Core object.</span></span> <span data-ttu-id="64297-114">Wenn Sie `Add-Type` Ihrem PowerShell-Profil einen Befehl hinzufügen, ist die Klasse in allen PowerShell-Sitzungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="64297-114">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="64297-115">Sie können den Typ angeben, indem Sie eine vorhandene Assembly oder Quellcodedateien angeben, oder Sie können den Quellcode inline oder in einer Variablen gespeichert angeben.</span><span class="sxs-lookup"><span data-stu-id="64297-115">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="64297-116">Sie können sogar nur eine-Methode angeben und `Add-Type` die-Klasse definieren und generieren.</span><span class="sxs-lookup"><span data-stu-id="64297-116">You can even specify only a method and `Add-Type` defines and generates the class.</span></span> <span data-ttu-id="64297-117">Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="64297-117">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="64297-118">Wenn Sie Quellcode angeben, `Add-Type` kompiliert den angegebenen Quellcode und generiert eine in-Memory-Assembly, die die neuen .net Core-Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="64297-118">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Core types.</span></span>

<span data-ttu-id="64297-119">Sie können die Parameter von verwenden, `Add-Type` um eine alternative Sprache und einen anderen Compiler anzugeben, c# ist die Standardeinstellung, Compileroptionen, Assemblyabhängigkeiten, den Klassen Namespace, die Namen des Typs und die resultierende Assembly.</span><span class="sxs-lookup"><span data-stu-id="64297-119">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

<span data-ttu-id="64297-120">Ab PowerShell 7 kompiliert keinen `Add-Type` Typ, wenn bereits ein Typ mit demselben Namen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="64297-120">Beginning in PowerShell 7, `Add-Type` does not compile a type if a type with the same name already exists.</span></span> <span data-ttu-id="64297-121">Sucht auch nach Assemblys `Add-Type` in einem `ref` Ordner unter dem Ordner, der enthält `pwsh.dll` .</span><span class="sxs-lookup"><span data-stu-id="64297-121">Also, `Add-Type` looks for assemblies in a `ref` folder under the folder that contains `pwsh.dll`.</span></span>

## <span data-ttu-id="64297-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="64297-122">EXAMPLES</span></span>

### <span data-ttu-id="64297-123">Beispiel 1: Hinzufügen eines .net-Typs zu einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="64297-123">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="64297-124">In diesem Beispiel wird die **basictest** -Klasse der Sitzung hinzugefügt, indem Quellcode angegeben wird, der in einer Variablen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="64297-124">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="64297-125">Die **basictest** -Klasse wird verwendet, um ganze Zahlen hinzuzufügen, ein Objekt zu erstellen und ganze Zahlen zu multiplizieren.</span><span class="sxs-lookup"><span data-stu-id="64297-125">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

<span data-ttu-id="64297-126">Die- `$Source` Variable speichert den Quellcode für die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="64297-126">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="64297-127">Der-Typ verfügt über eine statische Methode mit dem Namen `Add` und eine nicht statische Methode mit dem Namen `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="64297-127">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="64297-128">Mit dem- `Add-Type` Cmdlet wird die-Klasse der Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="64297-128">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="64297-129">Da es Inline Quellcode verwendet, verwendet der Befehl den **typeDefinition** -Parameter, um den Code in der `$Source` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="64297-129">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="64297-130">Die `Add` statische-Methode der **basictest** -Klasse verwendet die doppelten Doppelpunkte ( `::` ), um einen statischen Member der-Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="64297-130">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="64297-131">Die ganzen Zahlen werden hinzugefügt, und die Summe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64297-131">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="64297-132">Das- `New-Object` Cmdlet instanziiert eine Instanz der **basictest** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="64297-132">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="64297-133">Das neue Objekt wird in der `$BasicTestObject` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="64297-133">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="64297-134">`$BasicTestObject` verwendet die- `Multiply` Methode.</span><span class="sxs-lookup"><span data-stu-id="64297-134">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="64297-135">Die ganzen Zahlen werden multipliziert, und das Produkt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64297-135">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="64297-136">Beispiel 2: Untersuchen eines hinzugefügten Typs</span><span class="sxs-lookup"><span data-stu-id="64297-136">Example 2: Examine an added type</span></span>

<span data-ttu-id="64297-137">In diesem Beispiel wird das `Get-Member` -Cmdlet verwendet, um die Objekte zu überprüfen, die `Add-Type` `New-Object` in **Beispiel 1** erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="64297-137">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1**.</span></span>

```powershell
[BasicTest] | Get-Member
```

```Output
   TypeName: System.RuntimeType

Name                 MemberType Definition
----                 ---------- ----------
AsType               Method     type AsType()
Clone                Method     System.Object Clone(), System.Object ICloneable.Clone()
Equals               Method     bool Equals(System.Object obj), bool Equals(type o)
FindInterfaces       Method     type[] FindInterfaces(System.Reflection.TypeFilter filter...
...
```

```powershell
[BasicTest] | Get-Member -Static
```

```Output
  TypeName: BasicTest

Name            MemberType Definition
----            ---------- ----------
Add             Method     static int Add(int a, int b)
Equals          Method     static bool Equals(System.Object objA, System.Object objB)
new             Method     BasicTest new()
ReferenceEquals Method     static bool ReferenceEquals(System.Object objA, System.Object objB)
```

```powershell
$BasicTestObject | Get-Member
```

```Output
   TypeName: BasicTest

Name        MemberType Definition
----        ---------- ----------
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
Multiply    Method     int Multiply(int a, int b)
ToString    Method     string ToString()
```

<span data-ttu-id="64297-138">`Get-Member`Mit dem-Cmdlet werden der Typ und die Member der **basictest** -Klasse abgerufen, die `Add-Type` der Sitzung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="64297-138">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="64297-139">Der `Get-Member` Befehl zeigt, dass es sich um ein **System. RuntimeType** -Objekt handelt, das von der **System. Object** -Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="64297-139">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="64297-140">Der `Get-Member` **static** -Parameter ruft die statischen Eigenschaften und Methoden der **basictest** -Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="64297-140">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="64297-141">Die Ausgabe zeigt, dass die- `Add` Methode enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="64297-141">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="64297-142">Das- `Get-Member` Cmdlet ruft die Member des-Objekts ab, das in der Variablen gespeichert ist `$BasicTestObject` .</span><span class="sxs-lookup"><span data-stu-id="64297-142">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="64297-143">`$BasicTestObject` wurde mithilfe des `New-Object` Cmdlets mit der **basictest** -Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="64297-143">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="64297-144">Die Ausgabe zeigt, dass der Wert der `$BasicTestObject` Variablen eine Instanz der **basictest** -Klasse ist und einen Member mit dem Namen enthält `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="64297-144">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="64297-145">Beispiel 3: Hinzufügen von Typen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="64297-145">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="64297-146">In diesem Beispiel werden die Klassen der- `NJsonSchema.dll` Assembly der aktuellen Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="64297-146">This example adds the classes from the `NJsonSchema.dll` assembly to the current session.</span></span>

```powershell
Set-Location -Path $PSHOME
$AccType = Add-Type -AssemblyName *jsonschema* -PassThru
```

<span data-ttu-id="64297-147">`Set-Location` verwendet den **path** -Parameter, um die `$PSHOME` Variable anzugeben.</span><span class="sxs-lookup"><span data-stu-id="64297-147">`Set-Location` uses the **Path** parameter to specify the `$PSHOME` variable.</span></span> <span data-ttu-id="64297-148">Die Variable verweist auf das PowerShell-Installationsverzeichnis, in dem sich die DLL-Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="64297-148">The variable references the PowerShell installation directory where the DLL file is located.</span></span>

<span data-ttu-id="64297-149">Die- `$AccType` Variable speichert ein mit dem- `Add-Type` Cmdlet erstelltes Objekt.</span><span class="sxs-lookup"><span data-stu-id="64297-149">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="64297-150">`Add-Type` verwendet den **AssemblyName** -Parameter, um den Namen der Assembly anzugeben.</span><span class="sxs-lookup"><span data-stu-id="64297-150">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="64297-151">Mit dem Platzhalter Zeichen Sternchen ( `*` ) können Sie die richtige Assembly auch dann erhalten, wenn Sie den Namen oder die Schreibweise nicht sicher sind.</span><span class="sxs-lookup"><span data-stu-id="64297-151">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="64297-152">Der **passthru** -Parameter generiert-Objekte, die die Klassen darstellen, die der Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="64297-152">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="64297-153">Beispiel 4: Abrufen von systemeigenen Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="64297-153">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="64297-154">In diesem Beispiel wird veranschaulicht, wie Native Windows-APIs in PowerShell aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="64297-154">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="64297-155">`Add-Type` verwendet den Platt Form Aufruf-Mechanismus (P/aufrufen), um eine Funktion in über `User32.dll` PowerShell aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="64297-155">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="64297-156">Dieses Beispiel funktioniert nur auf Computern, auf denen das Windows-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="64297-156">This example only works on computers running the Windows operating system.</span></span>

```powershell
$Signature = @"
[DllImport("user32.dll")]public static extern bool ShowWindowAsync(IntPtr hWnd, int nCmdShow);
"@

$ShowWindowAsync = Add-Type -MemberDefinition $Signature -Name "Win32ShowWindowAsync" -Namespace Win32Functions -PassThru

# Minimize the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $pid).MainWindowHandle, 2)

# Restore the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $Pid).MainWindowHandle, 4)
```

<span data-ttu-id="64297-157">Die `$Signature` Variable speichert die c#-Signatur der `ShowWindowAsync` Funktion.</span><span class="sxs-lookup"><span data-stu-id="64297-157">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="64297-158">Um sicherzustellen, dass die resultierende Methode in einer PowerShell-Sitzung sichtbar ist, `public` wurde das Schlüsselwort der Standard Signatur hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="64297-158">To ensure that the resulting method is visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="64297-159">Weitere Informationen finden Sie unter [ShowWindowAsync-Funktion](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span><span class="sxs-lookup"><span data-stu-id="64297-159">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="64297-160">Die- `$ShowWindowAsync` Variable speichert das-Objekt, das vom `Add-Type` **passthru** -Parameter erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="64297-160">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="64297-161">Das- `Add-Type` Cmdlet fügt die `ShowWindowAsync` Funktion als statische Methode zur PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="64297-161">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="64297-162">Der Befehl verwendet den Parameter " **Membership Definition** ", um die in der Variablen gespeicherte Methoden Definition anzugeben `$Signature` .</span><span class="sxs-lookup"><span data-stu-id="64297-162">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="64297-163">Der Befehl verwendet die Parameter **Name** und **Namespace**, um einen Namen und einen Namespace für die Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="64297-163">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="64297-164">Der **passthru** -Parameter generiert ein Objekt, das die Typen darstellt.</span><span class="sxs-lookup"><span data-stu-id="64297-164">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="64297-165">Die neue `ShowWindowAsync` statische Methode wird in den Befehlen verwendet, um die PowerShell-Konsole zu minimieren und wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="64297-165">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="64297-166">Die-Methode nimmt zwei Parameter an: das Fenster Handle und eine ganze Zahl, die angibt, wie das Fenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="64297-166">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="64297-167">Um die PowerShell-Konsole zu minimieren, `ShowWindowAsync` verwendet das `Get-Process` Cmdlet mit der `$PID` automatischen Variablen, um den Prozess zu erhalten, der die aktuelle PowerShell-Sitzung gehostet.</span><span class="sxs-lookup"><span data-stu-id="64297-167">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="64297-168">Anschließend wird die **MainWindowHandle** -Eigenschaft des aktuellen Prozesses und der Wert verwendet `2` , der den- `SW_MINIMIZE` Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="64297-168">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="64297-169">Um das Fenster wiederherzustellen, `ShowWindowAsync` verwendet den Wert `4` für die Fensterposition, die den `SW_RESTORE` Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="64297-169">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="64297-170">Um das Fenster zu maximieren, verwenden Sie den Wert von `3` , der darstellt `SW_MAXIMIZE` .</span><span class="sxs-lookup"><span data-stu-id="64297-170">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

## <span data-ttu-id="64297-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="64297-171">PARAMETERS</span></span>

### <span data-ttu-id="64297-172">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="64297-172">-AssemblyName</span></span>

<span data-ttu-id="64297-173">Gibt den Namen einer Assembly an, die die Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="64297-173">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="64297-174">`Add-Type` nimmt die Typen aus der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="64297-174">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="64297-175">Dieser Parameter ist erforderlich, wenn Sie Typen auf der Grundlage eines Assemblynamens erstellen.</span><span class="sxs-lookup"><span data-stu-id="64297-175">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="64297-176">Geben Sie den vollständigen oder einfachen Namen einer Assembly ein, die auch als partieller Name bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="64297-176">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="64297-177">Der Assemblyname darf Platzhalterzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="64297-177">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="64297-178">Wenn Sie einen einfachen oder partiellen Namen eingeben, wird `Add-Type` dieser in den vollständigen Namen aufgelöst, und dann wird der vollständige Name verwendet, um die Assembly zu laden.</span><span class="sxs-lookup"><span data-stu-id="64297-178">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="64297-179">Dieser Parameter akzeptiert keinen Pfad oder Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="64297-179">This parameter doesn't accept a path or a filename.</span></span> <span data-ttu-id="64297-180">Um den Pfad zur DLL-Datei (Dynamic Link Library) der Assembly einzugeben, verwenden Sie den **path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="64297-180">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromAssemblyName
Aliases: AN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="64297-181">-CompilerOptions</span><span class="sxs-lookup"><span data-stu-id="64297-181">-CompilerOptions</span></span>

<span data-ttu-id="64297-182">Gibt die Optionen für den Quellcodecompiler an.</span><span class="sxs-lookup"><span data-stu-id="64297-182">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="64297-183">Diese Optionen werden ohne Revision an den Compiler gesendet.</span><span class="sxs-lookup"><span data-stu-id="64297-183">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="64297-184">Mit diesem Parameter können Sie den Compiler anweisen, eine ausführbare Datei zu generieren, Ressourcen einzubetten oder Befehlszeilenoptionen (z. b. die Option) festzulegen `/unsafe` .</span><span class="sxs-lookup"><span data-stu-id="64297-184">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span>

<span data-ttu-id="64297-185">Der **compilerOptions** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64297-185">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-186">-Ignorewarning</span><span class="sxs-lookup"><span data-stu-id="64297-186">-IgnoreWarnings</span></span>

<span data-ttu-id="64297-187">Ignoriert Compilerwarnungen.</span><span class="sxs-lookup"><span data-stu-id="64297-187">Ignores compiler warnings.</span></span> <span data-ttu-id="64297-188">Verwenden Sie diesen Parameter, um zu verhindern, dass `Add-Type` Compilerwarnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="64297-188">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-189">-Sprache</span><span class="sxs-lookup"><span data-stu-id="64297-189">-Language</span></span>

<span data-ttu-id="64297-190">Gibt die Sprache an, die im Quellcode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="64297-190">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="64297-191">Der zulässige Wert für diesen Parameter ist " **CSharp**".</span><span class="sxs-lookup"><span data-stu-id="64297-191">The acceptable value for this parameter is **CSharp**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-192">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="64297-192">-LiteralPath</span></span>

<span data-ttu-id="64297-193">Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="64297-193">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="64297-194">Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="64297-194">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="64297-195">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="64297-195">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="64297-196">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="64297-196">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="64297-197">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="64297-197">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-198">-Mitglieddefinition</span><span class="sxs-lookup"><span data-stu-id="64297-198">-MemberDefinition</span></span>

<span data-ttu-id="64297-199">Gibt neue Eigenschaften oder Methoden für die Klasse an.</span><span class="sxs-lookup"><span data-stu-id="64297-199">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="64297-200">`Add-Type` generiert den Vorlagen Code, der zur Unterstützung der Eigenschaften oder Methoden erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="64297-200">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="64297-201">Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="64297-201">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-202">-Name</span><span class="sxs-lookup"><span data-stu-id="64297-202">-Name</span></span>

<span data-ttu-id="64297-203">Gibt den Namen der zu erstellenden Klasse an.</span><span class="sxs-lookup"><span data-stu-id="64297-203">Specifies the name of the class to create.</span></span> <span data-ttu-id="64297-204">Dieser Parameter ist beim Generieren eines Typs aus einer Memberdefinition erforderlich.</span><span class="sxs-lookup"><span data-stu-id="64297-204">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="64297-205">Der Typname und der Namespace müssen innerhalb einer Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="64297-205">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="64297-206">Ein Typ kann nicht entladen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="64297-206">You can't unload a type or change it.</span></span>
<span data-ttu-id="64297-207">Wenn Sie den Code für einen Typ ändern möchten, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="64297-207">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="64297-208">Andernfalls führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="64297-208">Otherwise, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-209">-Namespace</span><span class="sxs-lookup"><span data-stu-id="64297-209">-Namespace</span></span>

<span data-ttu-id="64297-210">Gibt einen Namespace für den Typ an.</span><span class="sxs-lookup"><span data-stu-id="64297-210">Specifies a namespace for the type.</span></span>

<span data-ttu-id="64297-211">Wenn dieser Parameter nicht im Befehl enthalten ist, wird der Typ im **Microsoft. PowerShell. Commands. AddType. autogeneratedtypes** -Namespace erstellt.</span><span class="sxs-lookup"><span data-stu-id="64297-211">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="64297-212">Wenn der Parameter im Befehl mit einem leeren Zeichen folgen Wert oder einem Wert von enthalten ist `$Null` , wird der Typ im globalen Namespace generiert.</span><span class="sxs-lookup"><span data-stu-id="64297-212">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-213">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="64297-213">-OutputAssembly</span></span>

<span data-ttu-id="64297-214">Generiert eine DLL-Datei für die Assembly mit dem angegebenen Namen an dem Speicherort.</span><span class="sxs-lookup"><span data-stu-id="64297-214">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="64297-215">Geben Sie einen optionalen Pfad und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="64297-215">Enter an optional path and filename.</span></span> <span data-ttu-id="64297-216">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="64297-216">Wildcard characters are permitted.</span></span> <span data-ttu-id="64297-217">Standardmäßig `Add-Type` generiert die Assembly nur im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="64297-217">By default, `Add-Type` generates the assembly only in memory.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="64297-218">-OutputType</span><span class="sxs-lookup"><span data-stu-id="64297-218">-OutputType</span></span>

<span data-ttu-id="64297-219">Gibt den Ausgabetyp der Ausgabeassembly an.</span><span class="sxs-lookup"><span data-stu-id="64297-219">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="64297-220">Standardmäßig wird kein Ausgabetyp angegeben.</span><span class="sxs-lookup"><span data-stu-id="64297-220">By default, no output type is specified.</span></span> <span data-ttu-id="64297-221">Dieser Parameter gilt nur, wenn eine Ausgabeassembly im Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="64297-221">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="64297-222">Weitere Informationen zu den Werten finden Sie unter [outputassemblytype-Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span><span class="sxs-lookup"><span data-stu-id="64297-222">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="64297-223">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="64297-223">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="64297-224">ConsoleApplication</span><span class="sxs-lookup"><span data-stu-id="64297-224">ConsoleApplication</span></span>
- <span data-ttu-id="64297-225">Bibliothek</span><span class="sxs-lookup"><span data-stu-id="64297-225">Library</span></span>
- <span data-ttu-id="64297-226">Datei WindowsApplication</span><span class="sxs-lookup"><span data-stu-id="64297-226">WindowsApplication</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64297-227">Ab PowerShell 7,1 `ConsoleApplication` `WindowsApplication` werden und nicht unterstützt, und PowerShell löst einen abschließenden Fehler aus, wenn beide als Werte für den **OutputType** -Parameter angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="64297-227">As of PowerShell 7.1, `ConsoleApplication` and `WindowsApplication` are not supported and PowerShell throws a terminating error if either are specified as values for the **OutputType** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputAssemblyType
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OT
Accepted values: ConsoleApplication, Library, WindowsApplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-228">-PassThru</span><span class="sxs-lookup"><span data-stu-id="64297-228">-PassThru</span></span>

<span data-ttu-id="64297-229">Gibt ein **System.Runtime**-Objekt zurück, das die Typen darstellt, die hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="64297-229">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="64297-230">Standardmäßig generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="64297-230">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-231">-Path</span><span class="sxs-lookup"><span data-stu-id="64297-231">-Path</span></span>

<span data-ttu-id="64297-232">Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="64297-232">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="64297-233">Wenn Sie Quell Code Dateien übermitteln, `Add-Type` kompiliert den Code in den Dateien und erstellt eine in-Memory-Assembly der Typen.</span><span class="sxs-lookup"><span data-stu-id="64297-233">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="64297-234">Die Dateierweiterung, die im Wert von **path** angegeben ist, bestimmt den Compiler, der von `Add-Type` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="64297-234">The file extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="64297-235">Wenn Sie eine Assemblydatei übermitteln, `Add-Type` übernimmt die Typen aus der Assembly.</span><span class="sxs-lookup"><span data-stu-id="64297-235">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="64297-236">Um eine speicherinterne Assembly oder den globalen Assemblycache anzugeben, verwenden Sie den **AssemblyName**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="64297-236">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-237">-Referencedassemblys</span><span class="sxs-lookup"><span data-stu-id="64297-237">-ReferencedAssemblies</span></span>

<span data-ttu-id="64297-238">Gibt die Assemblys an, von denen der Typ abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="64297-238">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="64297-239">Standardmäßig `Add-Type` verweist auf `System.dll` und `System.Management.Automation.dll` .</span><span class="sxs-lookup"><span data-stu-id="64297-239">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="64297-240">Auf die Assemblys, die Sie mithilfe dieses Parameters angeben, wird zusätzlich zu den Standardassemblys verwiesen.</span><span class="sxs-lookup"><span data-stu-id="64297-240">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="64297-241">Ab PowerShell 6 enthalten **referencedassemblys** nicht die standardmäßigen .NET-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="64297-241">Beginning in PowerShell 6, **ReferencedAssemblies** doesn't include the default .NET assemblies.</span></span> <span data-ttu-id="64297-242">Sie müssen in dem an diesen Parameter übergebenen Wert einen bestimmten Verweis darauf einschließen.</span><span class="sxs-lookup"><span data-stu-id="64297-242">You must include a specific reference to them in the value passed to this parameter.</span></span>

<span data-ttu-id="64297-243">Der **compilerOptions** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64297-243">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: RA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-244">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="64297-244">-TypeDefinition</span></span>

<span data-ttu-id="64297-245">Gibt den Quellcode an, der die Typdefinitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="64297-245">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="64297-246">Geben Sie den Quellcode in einer Zeichenfolge oder einer here-Zeichenfolge ein, oder geben Sie eine Variable ein, die den Quellcode enthält.</span><span class="sxs-lookup"><span data-stu-id="64297-246">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="64297-247">Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="64297-247">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="64297-248">Schließen Sie eine Namespacedeklaration in die Typdefinition ein.</span><span class="sxs-lookup"><span data-stu-id="64297-248">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="64297-249">Wenn Sie die Namespacedeklaration weglassen, kann der Typ denselben Namen wie ein anderer Typ oder die Verknüpfung für einen anderen Typ aufweisen, was zu einer unbeabsichtigten Überschreibung führen kann.</span><span class="sxs-lookup"><span data-stu-id="64297-249">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="64297-250">Wenn Sie z. b. einen Typ mit dem Namen " **Exception**" definieren, schlagen Skripts, die eine **Ausnahme** als Verknüpfung für **System. Exception** verwenden, fehl.</span><span class="sxs-lookup"><span data-stu-id="64297-250">For example, if you define a type called **Exception**, scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-251">-Usingnamespace</span><span class="sxs-lookup"><span data-stu-id="64297-251">-UsingNamespace</span></span>

<span data-ttu-id="64297-252">Gibt andere Namespaces an, die für die Klasse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="64297-252">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="64297-253">Dies ähnelt dem c#-Schlüsselwort `Using` .</span><span class="sxs-lookup"><span data-stu-id="64297-253">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="64297-254">Standardmäßig `Add-Type` verweist auf den **System** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="64297-254">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="64297-255">Wenn der Parameter " **Membership Definition** " verwendet wird, `Add-Type` verweist standardmäßig auch auf den **System. Runtime. InteropServices** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="64297-255">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="64297-256">Auf die Namespaces, die Sie mithilfe der **UsingNamespace**-Parameter hinzufügen, wird zusätzlich zu den standardmäßigen Namespaces verwiesen.</span><span class="sxs-lookup"><span data-stu-id="64297-256">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases: Using

Required: False
Position: Named
Default value: System namespace
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64297-257">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="64297-257">CommonParameters</span></span>

<span data-ttu-id="64297-258">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="64297-258">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="64297-259">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="64297-259">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="64297-260">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="64297-260">INPUTS</span></span>

### <span data-ttu-id="64297-261">Keine</span><span class="sxs-lookup"><span data-stu-id="64297-261">None</span></span>

<span data-ttu-id="64297-262">Objekte können nicht über die Pipeline an gesendet werden `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="64297-262">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="64297-263">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="64297-263">OUTPUTS</span></span>

### <span data-ttu-id="64297-264">None oder System. Type</span><span class="sxs-lookup"><span data-stu-id="64297-264">None or System.Type</span></span>

<span data-ttu-id="64297-265">Wenn Sie den **passthru** -Parameter verwenden, `Add-Type` gibt ein **System. Type** -Objekt zurück, das den neuen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="64297-265">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="64297-266">Andernfalls generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="64297-266">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="64297-267">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="64297-267">NOTES</span></span>

<span data-ttu-id="64297-268">Die Typen, die Sie hinzufügen, sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="64297-268">The types that you add exist only in the current session.</span></span> <span data-ttu-id="64297-269">Um die Typen in allen Sitzungen zu verwenden, fügen Sie Sie Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="64297-269">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="64297-270">Weitere Informationen zum Profil finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="64297-270">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="64297-271">Typnamen und Namespaces müssen innerhalb einer Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="64297-271">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="64297-272">Ein Typ kann nicht entladen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="64297-272">You can't unload a type or change it.</span></span> <span data-ttu-id="64297-273">Wenn Sie den Code für einen Typ ändern müssen, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="64297-273">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="64297-274">Andernfalls führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="64297-274">Otherwise, the command fails.</span></span>

<span data-ttu-id="64297-275">In Windows PowerShell (Version 5,1 und niedriger) müssen Sie `Add-Type` für alles verwenden, was nicht bereits geladen ist.</span><span class="sxs-lookup"><span data-stu-id="64297-275">In Windows PowerShell (version 5.1 and below), you need to use `Add-Type` for anything that isn't already loaded.</span></span> <span data-ttu-id="64297-276">Dies gilt in der Regel für Assemblys, die im globalen Assemblycache (GAC) gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="64297-276">Most commonly, this applies to assemblies found in the Global Assembly Cache (GAC).</span></span>
<span data-ttu-id="64297-277">In PowerShell 6 und höher gibt es keinen GAC, sodass PowerShell seine eigenen Assemblys in installiert `$PSHome` .</span><span class="sxs-lookup"><span data-stu-id="64297-277">In PowerShell 6 and higher, there is no GAC, so PowerShell installs its own assemblies in `$PSHome`.</span></span>
<span data-ttu-id="64297-278">Diese Assemblys werden automatisch bei der Anforderung geladen, daher ist es nicht erforderlich, `Add-Type` Sie zu laden.</span><span class="sxs-lookup"><span data-stu-id="64297-278">These assemblies are automatically loaded on request, so there's no need to use `Add-Type` to load them.</span></span> <span data-ttu-id="64297-279">`Add-Type`Die Verwendung von ist jedoch weiterhin zulässig, damit Skripts implizit mit jeder beliebigen PowerShell-Version kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="64297-279">However, using `Add-Type` is still permitted to allow scripts to be implicitly compatible with any version of PowerShell.</span></span>

<span data-ttu-id="64297-280">Assemblys im GAC können nach dem Typnamen und nicht nach dem Pfad geladen werden.</span><span class="sxs-lookup"><span data-stu-id="64297-280">Assemblies in the GAC can be loaded by type name, rather than by path.</span></span> <span data-ttu-id="64297-281">Das Laden von Assemblys aus einem beliebigen Pfad erfordert `Add-Type` , da diese Assemblys nicht automatisch geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="64297-281">Loading assemblies from an arbitrary path requires `Add-Type`, since those assemblies cannot not be loaded automatically.</span></span>

## <span data-ttu-id="64297-282">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="64297-282">RELATED LINKS</span></span>

[<span data-ttu-id="64297-283">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="64297-283">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="64297-284">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="64297-284">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="64297-285">Add-Member</span><span class="sxs-lookup"><span data-stu-id="64297-285">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="64297-286">New-Object</span><span class="sxs-lookup"><span data-stu-id="64297-286">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="64297-287">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="64297-287">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="64297-288">Plattformaufruf (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="64297-288">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="64297-289">Where-Object</span><span class="sxs-lookup"><span data-stu-id="64297-289">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
