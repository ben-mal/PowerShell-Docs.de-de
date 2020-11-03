---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: cfd6cac9c1dda0a86b5b2762be936dc5d77bf34e
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "93219892"
---
# <span data-ttu-id="572e5-103">Add-Type</span><span class="sxs-lookup"><span data-stu-id="572e5-103">Add-Type</span></span>

## <span data-ttu-id="572e5-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="572e5-104">SYNOPSIS</span></span>
<span data-ttu-id="572e5-105">Fügt einer PowerShell-Sitzung eine Microsoft .net Core-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="572e5-105">Adds a Microsoft .NET Core class to a PowerShell session.</span></span>

## <span data-ttu-id="572e5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="572e5-106">SYNTAX</span></span>

### <span data-ttu-id="572e5-107">Fromsource (Standard)</span><span class="sxs-lookup"><span data-stu-id="572e5-107">FromSource (Default)</span></span>

```
Add-Type [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="572e5-108">Frommember</span><span class="sxs-lookup"><span data-stu-id="572e5-108">FromMember</span></span>

```
Add-Type [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>]
 [-UsingNamespace <String[]>] [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="572e5-109">Frompath</span><span class="sxs-lookup"><span data-stu-id="572e5-109">FromPath</span></span>

```
Add-Type [-Path] <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="572e5-110">Fromliteralpath</span><span class="sxs-lookup"><span data-stu-id="572e5-110">FromLiteralPath</span></span>

```
Add-Type -LiteralPath <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="572e5-111">Fromassemblyname</span><span class="sxs-lookup"><span data-stu-id="572e5-111">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="572e5-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="572e5-112">DESCRIPTION</span></span>

<span data-ttu-id="572e5-113">Mit dem- `Add-Type` Cmdlet können Sie in ihrer PowerShell-Sitzung eine Microsoft .net Core-Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="572e5-113">The `Add-Type` cmdlet lets you define a Microsoft .NET Core class in your PowerShell session.</span></span> <span data-ttu-id="572e5-114">Anschließend können Sie Objekte mit dem `New-Object` Cmdlet instanziieren und die Objekte wie jedes beliebige .net Core-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="572e5-114">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Core object.</span></span> <span data-ttu-id="572e5-115">Wenn Sie `Add-Type` Ihrem PowerShell-Profil einen Befehl hinzufügen, ist die Klasse in allen PowerShell-Sitzungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="572e5-115">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="572e5-116">Sie können den Typ angeben, indem Sie eine vorhandene Assembly oder Quellcodedateien angeben, oder Sie können den Quellcode inline oder in einer Variablen gespeichert angeben.</span><span class="sxs-lookup"><span data-stu-id="572e5-116">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="572e5-117">Sie können sogar nur eine-Methode angeben und `Add-Type` die-Klasse definieren und generieren.</span><span class="sxs-lookup"><span data-stu-id="572e5-117">You can even specify only a method and `Add-Type` defines and generates the class.</span></span> <span data-ttu-id="572e5-118">Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="572e5-118">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="572e5-119">Wenn Sie Quellcode angeben, `Add-Type` kompiliert den angegebenen Quellcode und generiert eine in-Memory-Assembly, die die neuen .net Core-Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="572e5-119">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Core types.</span></span>

<span data-ttu-id="572e5-120">Sie können die Parameter von verwenden, `Add-Type` um eine alternative Sprache und einen anderen Compiler anzugeben, c# ist die Standardeinstellung, Compileroptionen, Assemblyabhängigkeiten, den Klassen Namespace, die Namen des Typs und die resultierende Assembly.</span><span class="sxs-lookup"><span data-stu-id="572e5-120">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

<span data-ttu-id="572e5-121">Ab PowerShell 7 kompiliert keinen `Add-Type` Typ, wenn bereits ein Typ mit demselben Namen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="572e5-121">Beginning in PowerShell 7, `Add-Type` does not compile a type if a type with the same name already exists.</span></span> <span data-ttu-id="572e5-122">Sucht auch nach Assemblys `Add-Type` in einem `ref` Ordner unter dem Ordner, der enthält `pwsh.dll` .</span><span class="sxs-lookup"><span data-stu-id="572e5-122">Also, `Add-Type` looks for assemblies in a `ref` folder under the folder that contains `pwsh.dll`.</span></span>

## <span data-ttu-id="572e5-123">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="572e5-123">EXAMPLES</span></span>

### <span data-ttu-id="572e5-124">Beispiel 1: Hinzufügen eines .net-Typs zu einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="572e5-124">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="572e5-125">In diesem Beispiel wird die **basictest** -Klasse der Sitzung hinzugefügt, indem Quellcode angegeben wird, der in einer Variablen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="572e5-125">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="572e5-126">Die **basictest** -Klasse wird verwendet, um ganze Zahlen hinzuzufügen, ein Objekt zu erstellen und ganze Zahlen zu multiplizieren.</span><span class="sxs-lookup"><span data-stu-id="572e5-126">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

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

<span data-ttu-id="572e5-127">Die- `$Source` Variable speichert den Quellcode für die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="572e5-127">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="572e5-128">Der-Typ verfügt über eine statische Methode mit dem Namen `Add` und eine nicht statische Methode mit dem Namen `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="572e5-128">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="572e5-129">Mit dem- `Add-Type` Cmdlet wird die-Klasse der Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="572e5-129">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="572e5-130">Da es Inline Quellcode verwendet, verwendet der Befehl den **typeDefinition** -Parameter, um den Code in der `$Source` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="572e5-130">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="572e5-131">Die `Add` statische-Methode der **basictest** -Klasse verwendet die doppelten Doppelpunkte ( `::` ), um einen statischen Member der-Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="572e5-131">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="572e5-132">Die ganzen Zahlen werden hinzugefügt, und die Summe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="572e5-132">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="572e5-133">Das- `New-Object` Cmdlet instanziiert eine Instanz der **basictest** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="572e5-133">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="572e5-134">Das neue Objekt wird in der `$BasicTestObject` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="572e5-134">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="572e5-135">`$BasicTestObject` verwendet die- `Multiply` Methode.</span><span class="sxs-lookup"><span data-stu-id="572e5-135">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="572e5-136">Die ganzen Zahlen werden multipliziert, und das Produkt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="572e5-136">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="572e5-137">Beispiel 2: Untersuchen eines hinzugefügten Typs</span><span class="sxs-lookup"><span data-stu-id="572e5-137">Example 2: Examine an added type</span></span>

<span data-ttu-id="572e5-138">In diesem Beispiel wird das `Get-Member` -Cmdlet verwendet, um die Objekte zu überprüfen, die `Add-Type` `New-Object` in **Beispiel 1** erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="572e5-138">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1**.</span></span>

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

<span data-ttu-id="572e5-139">`Get-Member`Mit dem-Cmdlet werden der Typ und die Member der **basictest** -Klasse abgerufen, die `Add-Type` der Sitzung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="572e5-139">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="572e5-140">Der `Get-Member` Befehl zeigt, dass es sich um ein **System. RuntimeType** -Objekt handelt, das von der **System. Object** -Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="572e5-140">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="572e5-141">Der `Get-Member` **static** -Parameter ruft die statischen Eigenschaften und Methoden der **basictest** -Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="572e5-141">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="572e5-142">Die Ausgabe zeigt, dass die- `Add` Methode enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="572e5-142">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="572e5-143">Das- `Get-Member` Cmdlet ruft die Member des-Objekts ab, das in der Variablen gespeichert ist `$BasicTestObject` .</span><span class="sxs-lookup"><span data-stu-id="572e5-143">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="572e5-144">`$BasicTestObject` wurde mithilfe des `New-Object` Cmdlets mit der **basictest** -Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="572e5-144">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="572e5-145">Die Ausgabe zeigt, dass der Wert der `$BasicTestObject` Variablen eine Instanz der **basictest** -Klasse ist und einen Member mit dem Namen enthält `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="572e5-145">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="572e5-146">Beispiel 3: Hinzufügen von Typen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="572e5-146">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="572e5-147">In diesem Beispiel werden die Klassen der- `NJsonSchema.dll` Assembly der aktuellen Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="572e5-147">This example adds the classes from the `NJsonSchema.dll` assembly to the current session.</span></span>

```powershell
Set-Location -Path $PSHOME
$AccType = Add-Type -AssemblyName *jsonschema* -PassThru
```

<span data-ttu-id="572e5-148">`Set-Location` verwendet den **path** -Parameter, um die `$PSHOME` Variable anzugeben.</span><span class="sxs-lookup"><span data-stu-id="572e5-148">`Set-Location` uses the **Path** parameter to specify the `$PSHOME` variable.</span></span> <span data-ttu-id="572e5-149">Die Variable verweist auf das PowerShell-Installationsverzeichnis, in dem sich die DLL-Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="572e5-149">The variable references the PowerShell installation directory where the DLL file is located.</span></span>

<span data-ttu-id="572e5-150">Die- `$AccType` Variable speichert ein mit dem- `Add-Type` Cmdlet erstelltes Objekt.</span><span class="sxs-lookup"><span data-stu-id="572e5-150">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="572e5-151">`Add-Type` verwendet den **AssemblyName** -Parameter, um den Namen der Assembly anzugeben.</span><span class="sxs-lookup"><span data-stu-id="572e5-151">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="572e5-152">Mit dem Platzhalter Zeichen Sternchen ( `*` ) können Sie die richtige Assembly auch dann erhalten, wenn Sie den Namen oder die Schreibweise nicht sicher sind.</span><span class="sxs-lookup"><span data-stu-id="572e5-152">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="572e5-153">Der **passthru** -Parameter generiert-Objekte, die die Klassen darstellen, die der Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="572e5-153">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="572e5-154">Beispiel 4: Abrufen von systemeigenen Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="572e5-154">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="572e5-155">In diesem Beispiel wird veranschaulicht, wie Native Windows-APIs in PowerShell aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="572e5-155">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="572e5-156">`Add-Type` verwendet den Platt Form Aufruf-Mechanismus (P/aufrufen), um eine Funktion in über `User32.dll` PowerShell aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="572e5-156">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="572e5-157">Dieses Beispiel funktioniert nur auf Computern, auf denen das Windows-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="572e5-157">This example only works on computers running the Windows operating system.</span></span>

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

<span data-ttu-id="572e5-158">Die `$Signature` Variable speichert die c#-Signatur der `ShowWindowAsync` Funktion.</span><span class="sxs-lookup"><span data-stu-id="572e5-158">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="572e5-159">Um sicherzustellen, dass die resultierende Methode in einer PowerShell-Sitzung sichtbar ist, `public` wurde das Schlüsselwort der Standard Signatur hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="572e5-159">To ensure that the resulting method is visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="572e5-160">Weitere Informationen finden Sie unter [ShowWindowAsync-Funktion](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span><span class="sxs-lookup"><span data-stu-id="572e5-160">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="572e5-161">Die- `$ShowWindowAsync` Variable speichert das-Objekt, das vom `Add-Type` **passthru** -Parameter erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="572e5-161">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="572e5-162">Das- `Add-Type` Cmdlet fügt die `ShowWindowAsync` Funktion als statische Methode zur PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="572e5-162">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="572e5-163">Der Befehl verwendet den Parameter " **Membership Definition** ", um die in der Variablen gespeicherte Methoden Definition anzugeben `$Signature` .</span><span class="sxs-lookup"><span data-stu-id="572e5-163">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="572e5-164">Der Befehl verwendet die Parameter **Name** und **Namespace** , um einen Namen und einen Namespace für die Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="572e5-164">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="572e5-165">Der **passthru** -Parameter generiert ein Objekt, das die Typen darstellt.</span><span class="sxs-lookup"><span data-stu-id="572e5-165">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="572e5-166">Die neue `ShowWindowAsync` statische Methode wird in den Befehlen verwendet, um die PowerShell-Konsole zu minimieren und wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="572e5-166">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="572e5-167">Die-Methode nimmt zwei Parameter an: das Fenster Handle und eine ganze Zahl, die angibt, wie das Fenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="572e5-167">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="572e5-168">Um die PowerShell-Konsole zu minimieren, `ShowWindowAsync` verwendet das `Get-Process` Cmdlet mit der `$PID` automatischen Variablen, um den Prozess zu erhalten, der die aktuelle PowerShell-Sitzung gehostet.</span><span class="sxs-lookup"><span data-stu-id="572e5-168">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="572e5-169">Anschließend wird die **MainWindowHandle** -Eigenschaft des aktuellen Prozesses und der Wert verwendet `2` , der den- `SW_MINIMIZE` Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="572e5-169">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="572e5-170">Um das Fenster wiederherzustellen, `ShowWindowAsync` verwendet den Wert `4` für die Fensterposition, die den `SW_RESTORE` Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="572e5-170">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="572e5-171">Um das Fenster zu maximieren, verwenden Sie den Wert von `3` , der darstellt `SW_MAXIMIZE` .</span><span class="sxs-lookup"><span data-stu-id="572e5-171">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

## <span data-ttu-id="572e5-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="572e5-172">PARAMETERS</span></span>

### <span data-ttu-id="572e5-173">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="572e5-173">-AssemblyName</span></span>

<span data-ttu-id="572e5-174">Gibt den Namen einer Assembly an, die die Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="572e5-174">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="572e5-175">`Add-Type` nimmt die Typen aus der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="572e5-175">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="572e5-176">Dieser Parameter ist erforderlich, wenn Sie Typen auf der Grundlage eines Assemblynamens erstellen.</span><span class="sxs-lookup"><span data-stu-id="572e5-176">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="572e5-177">Geben Sie den vollständigen oder einfachen Namen einer Assembly ein, die auch als partieller Name bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="572e5-177">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="572e5-178">Der Assemblyname darf Platzhalterzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="572e5-178">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="572e5-179">Wenn Sie einen einfachen oder partiellen Namen eingeben, wird `Add-Type` dieser in den vollständigen Namen aufgelöst, und dann wird der vollständige Name verwendet, um die Assembly zu laden.</span><span class="sxs-lookup"><span data-stu-id="572e5-179">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="572e5-180">Dieser Parameter akzeptiert keinen Pfad oder Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="572e5-180">This parameter doesn't accept a path or a filename.</span></span> <span data-ttu-id="572e5-181">Um den Pfad zur DLL-Datei (Dynamic Link Library) der Assembly einzugeben, verwenden Sie den **path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="572e5-181">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

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

### <span data-ttu-id="572e5-182">-CompilerOptions</span><span class="sxs-lookup"><span data-stu-id="572e5-182">-CompilerOptions</span></span>

<span data-ttu-id="572e5-183">Gibt die Optionen für den Quellcodecompiler an.</span><span class="sxs-lookup"><span data-stu-id="572e5-183">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="572e5-184">Diese Optionen werden ohne Revision an den Compiler gesendet.</span><span class="sxs-lookup"><span data-stu-id="572e5-184">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="572e5-185">Mit diesem Parameter können Sie den Compiler anweisen, eine ausführbare Datei zu generieren, Ressourcen einzubetten oder Befehlszeilenoptionen (z. b. die Option) festzulegen `/unsafe` .</span><span class="sxs-lookup"><span data-stu-id="572e5-185">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span>

<span data-ttu-id="572e5-186">Der **compilerOptions** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="572e5-186">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

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

### <span data-ttu-id="572e5-187">-Ignorewarning</span><span class="sxs-lookup"><span data-stu-id="572e5-187">-IgnoreWarnings</span></span>

<span data-ttu-id="572e5-188">Ignoriert Compilerwarnungen.</span><span class="sxs-lookup"><span data-stu-id="572e5-188">Ignores compiler warnings.</span></span> <span data-ttu-id="572e5-189">Verwenden Sie diesen Parameter, um zu verhindern, dass `Add-Type` Compilerwarnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="572e5-189">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

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

### <span data-ttu-id="572e5-190">-Sprache</span><span class="sxs-lookup"><span data-stu-id="572e5-190">-Language</span></span>

<span data-ttu-id="572e5-191">Gibt die Sprache an, die im Quellcode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="572e5-191">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="572e5-192">Der zulässige Wert für diesen Parameter ist " **CSharp** ".</span><span class="sxs-lookup"><span data-stu-id="572e5-192">The acceptable value for this parameter is **CSharp**.</span></span>

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

### <span data-ttu-id="572e5-193">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="572e5-193">-LiteralPath</span></span>

<span data-ttu-id="572e5-194">Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="572e5-194">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="572e5-195">Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="572e5-195">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="572e5-196">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="572e5-196">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="572e5-197">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="572e5-197">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="572e5-198">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="572e5-198">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="572e5-199">-Mitglieddefinition</span><span class="sxs-lookup"><span data-stu-id="572e5-199">-MemberDefinition</span></span>

<span data-ttu-id="572e5-200">Gibt neue Eigenschaften oder Methoden für die Klasse an.</span><span class="sxs-lookup"><span data-stu-id="572e5-200">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="572e5-201">`Add-Type` generiert den Vorlagen Code, der zur Unterstützung der Eigenschaften oder Methoden erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="572e5-201">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="572e5-202">Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="572e5-202">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

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

### <span data-ttu-id="572e5-203">-Name</span><span class="sxs-lookup"><span data-stu-id="572e5-203">-Name</span></span>

<span data-ttu-id="572e5-204">Gibt den Namen der zu erstellenden Klasse an.</span><span class="sxs-lookup"><span data-stu-id="572e5-204">Specifies the name of the class to create.</span></span> <span data-ttu-id="572e5-205">Dieser Parameter ist beim Generieren eines Typs aus einer Memberdefinition erforderlich.</span><span class="sxs-lookup"><span data-stu-id="572e5-205">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="572e5-206">Der Typname und der Namespace müssen innerhalb einer Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="572e5-206">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="572e5-207">Ein Typ kann nicht entladen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="572e5-207">You can't unload a type or change it.</span></span>
<span data-ttu-id="572e5-208">Wenn Sie den Code für einen Typ ändern möchten, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="572e5-208">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="572e5-209">Andernfalls führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="572e5-209">Otherwise, the command fails.</span></span>

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

### <span data-ttu-id="572e5-210">-Namespace</span><span class="sxs-lookup"><span data-stu-id="572e5-210">-Namespace</span></span>

<span data-ttu-id="572e5-211">Gibt einen Namespace für den Typ an.</span><span class="sxs-lookup"><span data-stu-id="572e5-211">Specifies a namespace for the type.</span></span>

<span data-ttu-id="572e5-212">Wenn dieser Parameter nicht im Befehl enthalten ist, wird der Typ im **Microsoft. PowerShell. Commands. AddType. autogeneratedtypes** -Namespace erstellt.</span><span class="sxs-lookup"><span data-stu-id="572e5-212">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="572e5-213">Wenn der Parameter im Befehl mit einem leeren Zeichen folgen Wert oder einem Wert von enthalten ist `$Null` , wird der Typ im globalen Namespace generiert.</span><span class="sxs-lookup"><span data-stu-id="572e5-213">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

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

### <span data-ttu-id="572e5-214">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="572e5-214">-OutputAssembly</span></span>

<span data-ttu-id="572e5-215">Generiert eine DLL-Datei für die Assembly mit dem angegebenen Namen an dem Speicherort.</span><span class="sxs-lookup"><span data-stu-id="572e5-215">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="572e5-216">Geben Sie einen optionalen Pfad und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="572e5-216">Enter an optional path and filename.</span></span> <span data-ttu-id="572e5-217">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="572e5-217">Wildcard characters are permitted.</span></span> <span data-ttu-id="572e5-218">Standardmäßig `Add-Type` generiert die Assembly nur im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="572e5-218">By default, `Add-Type` generates the assembly only in memory.</span></span>

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

### <span data-ttu-id="572e5-219">-OutputType</span><span class="sxs-lookup"><span data-stu-id="572e5-219">-OutputType</span></span>

<span data-ttu-id="572e5-220">Gibt den Ausgabetyp der Ausgabeassembly an.</span><span class="sxs-lookup"><span data-stu-id="572e5-220">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="572e5-221">Standardmäßig wird kein Ausgabetyp angegeben.</span><span class="sxs-lookup"><span data-stu-id="572e5-221">By default, no output type is specified.</span></span> <span data-ttu-id="572e5-222">Dieser Parameter gilt nur, wenn eine Ausgabeassembly im Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="572e5-222">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="572e5-223">Weitere Informationen zu den Werten finden Sie unter [outputassemblytype-Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span><span class="sxs-lookup"><span data-stu-id="572e5-223">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="572e5-224">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="572e5-224">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="572e5-225">ConsoleApplication</span><span class="sxs-lookup"><span data-stu-id="572e5-225">ConsoleApplication</span></span>
- <span data-ttu-id="572e5-226">Bibliothek</span><span class="sxs-lookup"><span data-stu-id="572e5-226">Library</span></span>
- <span data-ttu-id="572e5-227">Datei WindowsApplication</span><span class="sxs-lookup"><span data-stu-id="572e5-227">WindowsApplication</span></span>

> [!IMPORTANT]
> <span data-ttu-id="572e5-228">Ab PowerShell 7,1 `ConsoleApplication` `WindowsApplication` werden und nicht unterstützt, und PowerShell löst einen abschließenden Fehler aus, wenn beide als Werte für den **OutputType** -Parameter angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="572e5-228">As of PowerShell 7.1, `ConsoleApplication` and `WindowsApplication` are not supported and PowerShell throws a terminating error if either are specified as values for the **OutputType** parameter.</span></span>

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

### <span data-ttu-id="572e5-229">-PassThru</span><span class="sxs-lookup"><span data-stu-id="572e5-229">-PassThru</span></span>

<span data-ttu-id="572e5-230">Gibt ein **System.Runtime** -Objekt zurück, das die Typen darstellt, die hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="572e5-230">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="572e5-231">Standardmäßig generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="572e5-231">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="572e5-232">-Path</span><span class="sxs-lookup"><span data-stu-id="572e5-232">-Path</span></span>

<span data-ttu-id="572e5-233">Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="572e5-233">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="572e5-234">Wenn Sie Quell Code Dateien übermitteln, `Add-Type` kompiliert den Code in den Dateien und erstellt eine in-Memory-Assembly der Typen.</span><span class="sxs-lookup"><span data-stu-id="572e5-234">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="572e5-235">Die Dateierweiterung, die im Wert von **path** angegeben ist, bestimmt den Compiler, der von `Add-Type` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="572e5-235">The file extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="572e5-236">Wenn Sie eine Assemblydatei übermitteln, `Add-Type` übernimmt die Typen aus der Assembly.</span><span class="sxs-lookup"><span data-stu-id="572e5-236">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="572e5-237">Um eine speicherinterne Assembly oder den globalen Assemblycache anzugeben, verwenden Sie den **AssemblyName** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="572e5-237">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="572e5-238">-Referencedassemblys</span><span class="sxs-lookup"><span data-stu-id="572e5-238">-ReferencedAssemblies</span></span>

<span data-ttu-id="572e5-239">Gibt die Assemblys an, von denen der Typ abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="572e5-239">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="572e5-240">Standardmäßig `Add-Type` verweist auf `System.dll` und `System.Management.Automation.dll` .</span><span class="sxs-lookup"><span data-stu-id="572e5-240">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="572e5-241">Auf die Assemblys, die Sie mithilfe dieses Parameters angeben, wird zusätzlich zu den Standardassemblys verwiesen.</span><span class="sxs-lookup"><span data-stu-id="572e5-241">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="572e5-242">Ab PowerShell 6 enthalten **referencedassemblys** nicht die standardmäßigen .NET-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="572e5-242">Beginning in PowerShell 6, **ReferencedAssemblies** doesn't include the default .NET assemblies.</span></span> <span data-ttu-id="572e5-243">Sie müssen in dem an diesen Parameter übergebenen Wert einen bestimmten Verweis darauf einschließen.</span><span class="sxs-lookup"><span data-stu-id="572e5-243">You must include a specific reference to them in the value passed to this parameter.</span></span>

<span data-ttu-id="572e5-244">Der **compilerOptions** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="572e5-244">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

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

### <span data-ttu-id="572e5-245">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="572e5-245">-TypeDefinition</span></span>

<span data-ttu-id="572e5-246">Gibt den Quellcode an, der die Typdefinitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="572e5-246">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="572e5-247">Geben Sie den Quellcode in einer Zeichenfolge oder einer here-Zeichenfolge ein, oder geben Sie eine Variable ein, die den Quellcode enthält.</span><span class="sxs-lookup"><span data-stu-id="572e5-247">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="572e5-248">Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="572e5-248">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="572e5-249">Schließen Sie eine Namespacedeklaration in die Typdefinition ein.</span><span class="sxs-lookup"><span data-stu-id="572e5-249">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="572e5-250">Wenn Sie die Namespacedeklaration weglassen, kann der Typ denselben Namen wie ein anderer Typ oder die Verknüpfung für einen anderen Typ aufweisen, was zu einer unbeabsichtigten Überschreibung führen kann.</span><span class="sxs-lookup"><span data-stu-id="572e5-250">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="572e5-251">Wenn Sie z. b. einen Typ mit dem Namen " **Exception** " definieren, schlagen Skripts, die eine **Ausnahme** als Verknüpfung für **System. Exception** verwenden, fehl.</span><span class="sxs-lookup"><span data-stu-id="572e5-251">For example, if you define a type called **Exception** , scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

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

### <span data-ttu-id="572e5-252">-Usingnamespace</span><span class="sxs-lookup"><span data-stu-id="572e5-252">-UsingNamespace</span></span>

<span data-ttu-id="572e5-253">Gibt andere Namespaces an, die für die Klasse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="572e5-253">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="572e5-254">Dies ähnelt dem c#-Schlüsselwort `Using` .</span><span class="sxs-lookup"><span data-stu-id="572e5-254">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="572e5-255">Standardmäßig `Add-Type` verweist auf den **System** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="572e5-255">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="572e5-256">Wenn der Parameter " **Membership Definition** " verwendet wird, `Add-Type` verweist standardmäßig auch auf den **System. Runtime. InteropServices** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="572e5-256">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="572e5-257">Auf die Namespaces, die Sie mithilfe der **UsingNamespace** -Parameter hinzufügen, wird zusätzlich zu den standardmäßigen Namespaces verwiesen.</span><span class="sxs-lookup"><span data-stu-id="572e5-257">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

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

### <span data-ttu-id="572e5-258">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="572e5-258">CommonParameters</span></span>

<span data-ttu-id="572e5-259">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="572e5-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="572e5-260">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="572e5-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="572e5-261">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="572e5-261">INPUTS</span></span>

### <span data-ttu-id="572e5-262">Keine</span><span class="sxs-lookup"><span data-stu-id="572e5-262">None</span></span>

<span data-ttu-id="572e5-263">Objekte können nicht über die Pipeline an gesendet werden `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="572e5-263">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="572e5-264">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="572e5-264">OUTPUTS</span></span>

### <span data-ttu-id="572e5-265">None oder System. Type</span><span class="sxs-lookup"><span data-stu-id="572e5-265">None or System.Type</span></span>

<span data-ttu-id="572e5-266">Wenn Sie den **passthru** -Parameter verwenden, `Add-Type` gibt ein **System. Type** -Objekt zurück, das den neuen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="572e5-266">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="572e5-267">Andernfalls generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="572e5-267">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="572e5-268">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="572e5-268">NOTES</span></span>

<span data-ttu-id="572e5-269">Die Typen, die Sie hinzufügen, sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="572e5-269">The types that you add exist only in the current session.</span></span> <span data-ttu-id="572e5-270">Um die Typen in allen Sitzungen zu verwenden, fügen Sie Sie Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="572e5-270">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="572e5-271">Weitere Informationen zum Profil finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="572e5-271">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="572e5-272">Typnamen und Namespaces müssen innerhalb einer Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="572e5-272">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="572e5-273">Ein Typ kann nicht entladen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="572e5-273">You can't unload a type or change it.</span></span> <span data-ttu-id="572e5-274">Wenn Sie den Code für einen Typ ändern müssen, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="572e5-274">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="572e5-275">Andernfalls führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="572e5-275">Otherwise, the command fails.</span></span>

<span data-ttu-id="572e5-276">In Windows PowerShell (Version 5,1 und niedriger) müssen Sie `Add-Type` für alles verwenden, was nicht bereits geladen ist.</span><span class="sxs-lookup"><span data-stu-id="572e5-276">In Windows PowerShell (version 5.1 and below), you need to use `Add-Type` for anything that isn't already loaded.</span></span> <span data-ttu-id="572e5-277">Dies gilt in der Regel für Assemblys, die im globalen Assemblycache (GAC) gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="572e5-277">Most commonly, this applies to assemblies found in the Global Assembly Cache (GAC).</span></span>
<span data-ttu-id="572e5-278">In PowerShell 6 und höher gibt es keinen GAC, sodass PowerShell seine eigenen Assemblys in installiert `$PSHome` .</span><span class="sxs-lookup"><span data-stu-id="572e5-278">In PowerShell 6 and higher, there is no GAC, so PowerShell installs its own assemblies in `$PSHome`.</span></span>
<span data-ttu-id="572e5-279">Diese Assemblys werden automatisch bei der Anforderung geladen, daher ist es nicht erforderlich, `Add-Type` Sie zu laden.</span><span class="sxs-lookup"><span data-stu-id="572e5-279">These assemblies are automatically loaded on request, so there's no need to use `Add-Type` to load them.</span></span> <span data-ttu-id="572e5-280">`Add-Type`Die Verwendung von ist jedoch weiterhin zulässig, damit Skripts implizit mit jeder beliebigen PowerShell-Version kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="572e5-280">However, using `Add-Type` is still permitted to allow scripts to be implicitly compatible with any version of PowerShell.</span></span>

<span data-ttu-id="572e5-281">Assemblys im GAC können nach dem Typnamen und nicht nach dem Pfad geladen werden.</span><span class="sxs-lookup"><span data-stu-id="572e5-281">Assemblies in the GAC can be loaded by type name, rather than by path.</span></span> <span data-ttu-id="572e5-282">Das Laden von Assemblys aus einem beliebigen Pfad erfordert `Add-Type` , da diese Assemblys nicht automatisch geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="572e5-282">Loading assemblies from an arbitrary path requires `Add-Type`, since those assemblies cannot not be loaded automatically.</span></span>

## <span data-ttu-id="572e5-283">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="572e5-283">RELATED LINKS</span></span>

[<span data-ttu-id="572e5-284">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="572e5-284">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="572e5-285">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="572e5-285">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="572e5-286">Add-Member</span><span class="sxs-lookup"><span data-stu-id="572e5-286">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="572e5-287">New-Object</span><span class="sxs-lookup"><span data-stu-id="572e5-287">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="572e5-288">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="572e5-288">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="572e5-289">Plattformaufruf (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="572e5-289">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="572e5-290">Where-Object</span><span class="sxs-lookup"><span data-stu-id="572e5-290">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
