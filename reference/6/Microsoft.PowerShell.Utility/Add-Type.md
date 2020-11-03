---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: 9a51c97def7cddf45c391ed91ff67ad97fbedf77
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "93219903"
---
# <span data-ttu-id="6403e-103">Add-Type</span><span class="sxs-lookup"><span data-stu-id="6403e-103">Add-Type</span></span>

## <span data-ttu-id="6403e-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6403e-104">SYNOPSIS</span></span>
<span data-ttu-id="6403e-105">Fügt einer PowerShell-Sitzung eine Microsoft .net Core-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="6403e-105">Adds a Microsoft .NET Core class to a PowerShell session.</span></span>

## <span data-ttu-id="6403e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6403e-106">SYNTAX</span></span>

### <span data-ttu-id="6403e-107">Fromsource (Standard)</span><span class="sxs-lookup"><span data-stu-id="6403e-107">FromSource (Default)</span></span>

```
Add-Type [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6403e-108">Frommember</span><span class="sxs-lookup"><span data-stu-id="6403e-108">FromMember</span></span>

```
Add-Type [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>]
 [-UsingNamespace <String[]>] [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6403e-109">Frompath</span><span class="sxs-lookup"><span data-stu-id="6403e-109">FromPath</span></span>

```
Add-Type [-Path] <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="6403e-110">Fromliteralpath</span><span class="sxs-lookup"><span data-stu-id="6403e-110">FromLiteralPath</span></span>

```
Add-Type -LiteralPath <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="6403e-111">Fromassemblyname</span><span class="sxs-lookup"><span data-stu-id="6403e-111">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="6403e-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6403e-112">DESCRIPTION</span></span>

<span data-ttu-id="6403e-113">Mit dem- `Add-Type` Cmdlet können Sie in ihrer PowerShell-Sitzung eine Microsoft .net Core-Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="6403e-113">The `Add-Type` cmdlet lets you define a Microsoft .NET Core class in your PowerShell session.</span></span> <span data-ttu-id="6403e-114">Anschließend können Sie Objekte mit dem `New-Object` Cmdlet instanziieren und die Objekte wie jedes beliebige .net Core-Objekt verwenden.</span><span class="sxs-lookup"><span data-stu-id="6403e-114">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Core object.</span></span> <span data-ttu-id="6403e-115">Wenn Sie `Add-Type` Ihrem PowerShell-Profil einen Befehl hinzufügen, ist die Klasse in allen PowerShell-Sitzungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6403e-115">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="6403e-116">Sie können den Typ angeben, indem Sie eine vorhandene Assembly oder Quellcodedateien angeben, oder Sie können den Quellcode inline oder in einer Variablen gespeichert angeben.</span><span class="sxs-lookup"><span data-stu-id="6403e-116">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="6403e-117">Sie können sogar nur eine-Methode angeben und `Add-Type` die-Klasse definieren und generieren.</span><span class="sxs-lookup"><span data-stu-id="6403e-117">You can even specify only a method and `Add-Type` defines and generates the class.</span></span> <span data-ttu-id="6403e-118">Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="6403e-118">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="6403e-119">Wenn Sie Quellcode angeben, `Add-Type` kompiliert den angegebenen Quellcode und generiert eine in-Memory-Assembly, die die neuen .net Core-Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="6403e-119">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Core types.</span></span>

<span data-ttu-id="6403e-120">Sie können die Parameter von verwenden, `Add-Type` um eine alternative Sprache und einen anderen Compiler anzugeben, c# ist die Standardeinstellung, Compileroptionen, Assemblyabhängigkeiten, den Klassen Namespace, die Namen des Typs und die resultierende Assembly.</span><span class="sxs-lookup"><span data-stu-id="6403e-120">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

## <span data-ttu-id="6403e-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6403e-121">EXAMPLES</span></span>

### <span data-ttu-id="6403e-122">Beispiel 1: Hinzufügen eines .net-Typs zu einer Sitzung</span><span class="sxs-lookup"><span data-stu-id="6403e-122">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="6403e-123">In diesem Beispiel wird die **basictest** -Klasse der Sitzung hinzugefügt, indem Quellcode angegeben wird, der in einer Variablen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="6403e-123">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="6403e-124">Die **basictest** -Klasse wird verwendet, um ganze Zahlen hinzuzufügen, ein Objekt zu erstellen und ganze Zahlen zu multiplizieren.</span><span class="sxs-lookup"><span data-stu-id="6403e-124">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

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

<span data-ttu-id="6403e-125">Die- `$Source` Variable speichert den Quellcode für die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6403e-125">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="6403e-126">Der-Typ verfügt über eine statische Methode mit dem Namen `Add` und eine nicht statische Methode mit dem Namen `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="6403e-126">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="6403e-127">Mit dem- `Add-Type` Cmdlet wird die-Klasse der Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6403e-127">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="6403e-128">Da es Inline Quellcode verwendet, verwendet der Befehl den **typeDefinition** -Parameter, um den Code in der `$Source` Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6403e-128">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="6403e-129">Die `Add` statische-Methode der **basictest** -Klasse verwendet die doppelten Doppelpunkte ( `::` ), um einen statischen Member der-Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6403e-129">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="6403e-130">Die ganzen Zahlen werden hinzugefügt, und die Summe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6403e-130">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="6403e-131">Das- `New-Object` Cmdlet instanziiert eine Instanz der **basictest** -Klasse.</span><span class="sxs-lookup"><span data-stu-id="6403e-131">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="6403e-132">Das neue Objekt wird in der `$BasicTestObject` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6403e-132">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="6403e-133">`$BasicTestObject` verwendet die- `Multiply` Methode.</span><span class="sxs-lookup"><span data-stu-id="6403e-133">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="6403e-134">Die ganzen Zahlen werden multipliziert, und das Produkt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6403e-134">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="6403e-135">Beispiel 2: Untersuchen eines hinzugefügten Typs</span><span class="sxs-lookup"><span data-stu-id="6403e-135">Example 2: Examine an added type</span></span>

<span data-ttu-id="6403e-136">In diesem Beispiel wird das `Get-Member` -Cmdlet verwendet, um die Objekte zu überprüfen, die `Add-Type` `New-Object` in **Beispiel 1** erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6403e-136">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1**.</span></span>

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

<span data-ttu-id="6403e-137">`Get-Member`Mit dem-Cmdlet werden der Typ und die Member der **basictest** -Klasse abgerufen, die `Add-Type` der Sitzung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="6403e-137">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="6403e-138">Der `Get-Member` Befehl zeigt, dass es sich um ein **System. RuntimeType** -Objekt handelt, das von der **System. Object** -Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="6403e-138">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="6403e-139">Der `Get-Member` **static** -Parameter ruft die statischen Eigenschaften und Methoden der **basictest** -Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="6403e-139">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="6403e-140">Die Ausgabe zeigt, dass die- `Add` Methode enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6403e-140">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="6403e-141">Das- `Get-Member` Cmdlet ruft die Member des-Objekts ab, das in der Variablen gespeichert ist `$BasicTestObject` .</span><span class="sxs-lookup"><span data-stu-id="6403e-141">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="6403e-142">`$BasicTestObject` wurde mithilfe des `New-Object` Cmdlets mit der **basictest** -Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="6403e-142">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="6403e-143">Die Ausgabe zeigt, dass der Wert der `$BasicTestObject` Variablen eine Instanz der **basictest** -Klasse ist und einen Member mit dem Namen enthält `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="6403e-143">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="6403e-144">Beispiel 3: Hinzufügen von Typen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="6403e-144">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="6403e-145">In diesem Beispiel werden die Klassen der- `NJsonSchema.dll` Assembly der aktuellen Sitzung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6403e-145">This example adds the classes from the `NJsonSchema.dll` assembly to the current session.</span></span>

```powershell
Set-Location -Path $PSHOME
$AccType = Add-Type -AssemblyName *jsonschema* -PassThru
```

<span data-ttu-id="6403e-146">`Set-Location` verwendet den **path** -Parameter, um die `$PSHOME` Variable anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6403e-146">`Set-Location` uses the **Path** parameter to specify the `$PSHOME` variable.</span></span> <span data-ttu-id="6403e-147">Die Variable verweist auf das PowerShell-Installationsverzeichnis, in dem sich die DLL-Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="6403e-147">The variable references the PowerShell installation directory where the DLL file is located.</span></span>

<span data-ttu-id="6403e-148">Die- `$AccType` Variable speichert ein mit dem- `Add-Type` Cmdlet erstelltes Objekt.</span><span class="sxs-lookup"><span data-stu-id="6403e-148">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="6403e-149">`Add-Type` verwendet den **AssemblyName** -Parameter, um den Namen der Assembly anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6403e-149">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="6403e-150">Mit dem Platzhalter Zeichen Sternchen ( `*` ) können Sie die richtige Assembly auch dann erhalten, wenn Sie den Namen oder die Schreibweise nicht sicher sind.</span><span class="sxs-lookup"><span data-stu-id="6403e-150">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="6403e-151">Der **passthru** -Parameter generiert-Objekte, die die Klassen darstellen, die der Sitzung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-151">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="6403e-152">Beispiel 4: Abrufen von systemeigenen Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="6403e-152">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="6403e-153">In diesem Beispiel wird veranschaulicht, wie Native Windows-APIs in PowerShell aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-153">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="6403e-154">`Add-Type` verwendet den Platt Form Aufruf-Mechanismus (P/aufrufen), um eine Funktion in über `User32.dll` PowerShell aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6403e-154">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="6403e-155">Dieses Beispiel funktioniert nur auf Computern, auf denen das Windows-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6403e-155">This example only works on computers running the Windows operating system.</span></span>

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

<span data-ttu-id="6403e-156">Die `$Signature` Variable speichert die c#-Signatur der `ShowWindowAsync` Funktion.</span><span class="sxs-lookup"><span data-stu-id="6403e-156">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="6403e-157">Um sicherzustellen, dass die resultierende Methode in einer PowerShell-Sitzung sichtbar ist, `public` wurde das Schlüsselwort der Standard Signatur hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6403e-157">To ensure that the resulting method is visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="6403e-158">Weitere Informationen finden Sie unter [ShowWindowAsync-Funktion](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span><span class="sxs-lookup"><span data-stu-id="6403e-158">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="6403e-159">Die- `$ShowWindowAsync` Variable speichert das-Objekt, das vom `Add-Type` **passthru** -Parameter erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6403e-159">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="6403e-160">Das- `Add-Type` Cmdlet fügt die `ShowWindowAsync` Funktion als statische Methode zur PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="6403e-160">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="6403e-161">Der Befehl verwendet den Parameter " **Membership Definition** ", um die in der Variablen gespeicherte Methoden Definition anzugeben `$Signature` .</span><span class="sxs-lookup"><span data-stu-id="6403e-161">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="6403e-162">Der Befehl verwendet die Parameter **Name** und **Namespace** , um einen Namen und einen Namespace für die Klasse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6403e-162">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="6403e-163">Der **passthru** -Parameter generiert ein Objekt, das die Typen darstellt.</span><span class="sxs-lookup"><span data-stu-id="6403e-163">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="6403e-164">Die neue `ShowWindowAsync` statische Methode wird in den Befehlen verwendet, um die PowerShell-Konsole zu minimieren und wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="6403e-164">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="6403e-165">Die-Methode nimmt zwei Parameter an: das Fenster Handle und eine ganze Zahl, die angibt, wie das Fenster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6403e-165">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="6403e-166">Um die PowerShell-Konsole zu minimieren, `ShowWindowAsync` verwendet das `Get-Process` Cmdlet mit der `$PID` automatischen Variablen, um den Prozess zu erhalten, der die aktuelle PowerShell-Sitzung gehostet.</span><span class="sxs-lookup"><span data-stu-id="6403e-166">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="6403e-167">Anschließend wird die **MainWindowHandle** -Eigenschaft des aktuellen Prozesses und der Wert verwendet `2` , der den- `SW_MINIMIZE` Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="6403e-167">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="6403e-168">Um das Fenster wiederherzustellen, `ShowWindowAsync` verwendet den Wert `4` für die Fensterposition, die den `SW_RESTORE` Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="6403e-168">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="6403e-169">Um das Fenster zu maximieren, verwenden Sie den Wert von `3` , der darstellt `SW_MAXIMIZE` .</span><span class="sxs-lookup"><span data-stu-id="6403e-169">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

## <span data-ttu-id="6403e-170">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6403e-170">PARAMETERS</span></span>

### <span data-ttu-id="6403e-171">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="6403e-171">-AssemblyName</span></span>

<span data-ttu-id="6403e-172">Gibt den Namen einer Assembly an, die die Typen enthält.</span><span class="sxs-lookup"><span data-stu-id="6403e-172">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="6403e-173">`Add-Type` nimmt die Typen aus der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="6403e-173">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="6403e-174">Dieser Parameter ist erforderlich, wenn Sie Typen auf der Grundlage eines Assemblynamens erstellen.</span><span class="sxs-lookup"><span data-stu-id="6403e-174">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="6403e-175">Geben Sie den vollständigen oder einfachen Namen einer Assembly ein, die auch als partieller Name bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="6403e-175">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="6403e-176">Der Assemblyname darf Platzhalterzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6403e-176">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="6403e-177">Wenn Sie einen einfachen oder partiellen Namen eingeben, wird `Add-Type` dieser in den vollständigen Namen aufgelöst, und dann wird der vollständige Name verwendet, um die Assembly zu laden.</span><span class="sxs-lookup"><span data-stu-id="6403e-177">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="6403e-178">Dieser Parameter akzeptiert keinen Pfad oder Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="6403e-178">This parameter doesn't accept a path or a filename.</span></span> <span data-ttu-id="6403e-179">Um den Pfad zur DLL-Datei (Dynamic Link Library) der Assembly einzugeben, verwenden Sie den **path** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="6403e-179">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

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

### <span data-ttu-id="6403e-180">-CompilerOptions</span><span class="sxs-lookup"><span data-stu-id="6403e-180">-CompilerOptions</span></span>

<span data-ttu-id="6403e-181">Gibt die Optionen für den Quellcodecompiler an.</span><span class="sxs-lookup"><span data-stu-id="6403e-181">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="6403e-182">Diese Optionen werden ohne Revision an den Compiler gesendet.</span><span class="sxs-lookup"><span data-stu-id="6403e-182">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="6403e-183">Mit diesem Parameter können Sie den Compiler anweisen, eine ausführbare Datei zu generieren, Ressourcen einzubetten oder Befehlszeilenoptionen (z. b. die Option) festzulegen `/unsafe` .</span><span class="sxs-lookup"><span data-stu-id="6403e-183">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span>

<span data-ttu-id="6403e-184">Der **compilerOptions** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-184">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

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

### <span data-ttu-id="6403e-185">-Ignorewarning</span><span class="sxs-lookup"><span data-stu-id="6403e-185">-IgnoreWarnings</span></span>

<span data-ttu-id="6403e-186">Ignoriert Compilerwarnungen.</span><span class="sxs-lookup"><span data-stu-id="6403e-186">Ignores compiler warnings.</span></span> <span data-ttu-id="6403e-187">Verwenden Sie diesen Parameter, um zu verhindern, dass `Add-Type` Compilerwarnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-187">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

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

### <span data-ttu-id="6403e-188">-Sprache</span><span class="sxs-lookup"><span data-stu-id="6403e-188">-Language</span></span>

<span data-ttu-id="6403e-189">Gibt die Sprache an, die im Quellcode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6403e-189">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="6403e-190">Der zulässige Wert für diesen Parameter ist " **CSharp** ".</span><span class="sxs-lookup"><span data-stu-id="6403e-190">The acceptable value for this parameter is **CSharp**.</span></span>

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

### <span data-ttu-id="6403e-191">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="6403e-191">-LiteralPath</span></span>

<span data-ttu-id="6403e-192">Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6403e-192">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="6403e-193">Im Gegensatz zu **path** wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6403e-193">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="6403e-194">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="6403e-194">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6403e-195">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="6403e-195">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="6403e-196">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="6403e-196">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="6403e-197">-Mitglieddefinition</span><span class="sxs-lookup"><span data-stu-id="6403e-197">-MemberDefinition</span></span>

<span data-ttu-id="6403e-198">Gibt neue Eigenschaften oder Methoden für die Klasse an.</span><span class="sxs-lookup"><span data-stu-id="6403e-198">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="6403e-199">`Add-Type` generiert den Vorlagen Code, der zur Unterstützung der Eigenschaften oder Methoden erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6403e-199">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="6403e-200">Unter Windows können Sie diese Funktion verwenden, um Platt Form Aufrufe (P/aufrufen) von nicht verwalteten Funktionen in PowerShell durchführen.</span><span class="sxs-lookup"><span data-stu-id="6403e-200">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

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

### <span data-ttu-id="6403e-201">-Name</span><span class="sxs-lookup"><span data-stu-id="6403e-201">-Name</span></span>

<span data-ttu-id="6403e-202">Gibt den Namen der zu erstellenden Klasse an.</span><span class="sxs-lookup"><span data-stu-id="6403e-202">Specifies the name of the class to create.</span></span> <span data-ttu-id="6403e-203">Dieser Parameter ist beim Generieren eines Typs aus einer Memberdefinition erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6403e-203">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="6403e-204">Der Typname und der Namespace müssen innerhalb einer Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="6403e-204">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="6403e-205">Ein Typ kann nicht entladen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-205">You can't unload a type or change it.</span></span>
<span data-ttu-id="6403e-206">Wenn Sie den Code für einen Typ ändern möchten, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="6403e-206">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="6403e-207">Andernfalls führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="6403e-207">Otherwise, the command fails.</span></span>

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

### <span data-ttu-id="6403e-208">-Namespace</span><span class="sxs-lookup"><span data-stu-id="6403e-208">-Namespace</span></span>

<span data-ttu-id="6403e-209">Gibt einen Namespace für den Typ an.</span><span class="sxs-lookup"><span data-stu-id="6403e-209">Specifies a namespace for the type.</span></span>

<span data-ttu-id="6403e-210">Wenn dieser Parameter nicht im Befehl enthalten ist, wird der Typ im **Microsoft. PowerShell. Commands. AddType. autogeneratedtypes** -Namespace erstellt.</span><span class="sxs-lookup"><span data-stu-id="6403e-210">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="6403e-211">Wenn der Parameter im Befehl mit einem leeren Zeichen folgen Wert oder einem Wert von enthalten ist `$Null` , wird der Typ im globalen Namespace generiert.</span><span class="sxs-lookup"><span data-stu-id="6403e-211">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

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

### <span data-ttu-id="6403e-212">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="6403e-212">-OutputAssembly</span></span>

<span data-ttu-id="6403e-213">Generiert eine DLL-Datei für die Assembly mit dem angegebenen Namen an dem Speicherort.</span><span class="sxs-lookup"><span data-stu-id="6403e-213">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="6403e-214">Geben Sie einen optionalen Pfad und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="6403e-214">Enter an optional path and filename.</span></span> <span data-ttu-id="6403e-215">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="6403e-215">Wildcard characters are permitted.</span></span> <span data-ttu-id="6403e-216">Standardmäßig `Add-Type` generiert die Assembly nur im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="6403e-216">By default, `Add-Type` generates the assembly only in memory.</span></span>

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

### <span data-ttu-id="6403e-217">-OutputType</span><span class="sxs-lookup"><span data-stu-id="6403e-217">-OutputType</span></span>

<span data-ttu-id="6403e-218">Gibt den Ausgabetyp der Ausgabeassembly an.</span><span class="sxs-lookup"><span data-stu-id="6403e-218">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="6403e-219">Standardmäßig wird kein Ausgabetyp angegeben.</span><span class="sxs-lookup"><span data-stu-id="6403e-219">By default, no output type is specified.</span></span> <span data-ttu-id="6403e-220">Dieser Parameter gilt nur, wenn eine Ausgabeassembly im Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6403e-220">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="6403e-221">Weitere Informationen zu den Werten finden Sie unter [outputassemblytype-Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span><span class="sxs-lookup"><span data-stu-id="6403e-221">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="6403e-222">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6403e-222">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="6403e-223">ConsoleApplication</span><span class="sxs-lookup"><span data-stu-id="6403e-223">ConsoleApplication</span></span>
- <span data-ttu-id="6403e-224">Bibliothek</span><span class="sxs-lookup"><span data-stu-id="6403e-224">Library</span></span>
- <span data-ttu-id="6403e-225">Datei WindowsApplication</span><span class="sxs-lookup"><span data-stu-id="6403e-225">WindowsApplication</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6403e-226">Der `ConsoleApplication` -Wert und der-Wert führen nicht zu einer `WindowsApplication` funktionierenden Ausgabe und sollten nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-226">The `ConsoleApplication` and `WindowsApplication` values don't produce working output and should not be used.</span></span>

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

### <span data-ttu-id="6403e-227">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6403e-227">-PassThru</span></span>

<span data-ttu-id="6403e-228">Gibt ein **System.Runtime** -Objekt zurück, das die Typen darstellt, die hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="6403e-228">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="6403e-229">Standardmäßig generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="6403e-229">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="6403e-230">-Path</span><span class="sxs-lookup"><span data-stu-id="6403e-230">-Path</span></span>

<span data-ttu-id="6403e-231">Gibt den Pfad zu Quellcodedateien oder Assembly-DLL-Dateien an, die die Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6403e-231">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="6403e-232">Wenn Sie Quell Code Dateien übermitteln, `Add-Type` kompiliert den Code in den Dateien und erstellt eine in-Memory-Assembly der Typen.</span><span class="sxs-lookup"><span data-stu-id="6403e-232">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="6403e-233">Die Dateierweiterung, die im Wert von **path** angegeben ist, bestimmt den Compiler, der von `Add-Type` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6403e-233">The file extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="6403e-234">Wenn Sie eine Assemblydatei übermitteln, `Add-Type` übernimmt die Typen aus der Assembly.</span><span class="sxs-lookup"><span data-stu-id="6403e-234">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="6403e-235">Um eine speicherinterne Assembly oder den globalen Assemblycache anzugeben, verwenden Sie den **AssemblyName** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="6403e-235">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="6403e-236">-Referencedassemblys</span><span class="sxs-lookup"><span data-stu-id="6403e-236">-ReferencedAssemblies</span></span>

<span data-ttu-id="6403e-237">Gibt die Assemblys an, von denen der Typ abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="6403e-237">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="6403e-238">Standardmäßig `Add-Type` verweist auf `System.dll` und `System.Management.Automation.dll` .</span><span class="sxs-lookup"><span data-stu-id="6403e-238">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="6403e-239">Auf die Assemblys, die Sie mithilfe dieses Parameters angeben, wird zusätzlich zu den Standardassemblys verwiesen.</span><span class="sxs-lookup"><span data-stu-id="6403e-239">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="6403e-240">Ab PowerShell 6 enthalten **referencedassemblys** nicht die standardmäßigen .NET-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="6403e-240">Beginning in PowerShell 6, **ReferencedAssemblies** doesn't include the default .NET assemblies.</span></span> <span data-ttu-id="6403e-241">Sie müssen in dem an diesen Parameter übergebenen Wert einen bestimmten Verweis darauf einschließen.</span><span class="sxs-lookup"><span data-stu-id="6403e-241">You must include a specific reference to them in the value passed to this parameter.</span></span>

<span data-ttu-id="6403e-242">Der **compilerOptions** -Parameter und der **referencedassemblyparameter** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-242">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

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

### <span data-ttu-id="6403e-243">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="6403e-243">-TypeDefinition</span></span>

<span data-ttu-id="6403e-244">Gibt den Quellcode an, der die Typdefinitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="6403e-244">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="6403e-245">Geben Sie den Quellcode in einer Zeichenfolge oder einer here-Zeichenfolge ein, oder geben Sie eine Variable ein, die den Quellcode enthält.</span><span class="sxs-lookup"><span data-stu-id="6403e-245">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="6403e-246">Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="6403e-246">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="6403e-247">Schließen Sie eine Namespacedeklaration in die Typdefinition ein.</span><span class="sxs-lookup"><span data-stu-id="6403e-247">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="6403e-248">Wenn Sie die Namespacedeklaration weglassen, kann der Typ denselben Namen wie ein anderer Typ oder die Verknüpfung für einen anderen Typ aufweisen, was zu einer unbeabsichtigten Überschreibung führen kann.</span><span class="sxs-lookup"><span data-stu-id="6403e-248">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="6403e-249">Wenn Sie z. b. einen Typ mit dem Namen " **Exception** " definieren, schlagen Skripts, die eine **Ausnahme** als Verknüpfung für **System. Exception** verwenden, fehl.</span><span class="sxs-lookup"><span data-stu-id="6403e-249">For example, if you define a type called **Exception** , scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

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

### <span data-ttu-id="6403e-250">-Usingnamespace</span><span class="sxs-lookup"><span data-stu-id="6403e-250">-UsingNamespace</span></span>

<span data-ttu-id="6403e-251">Gibt andere Namespaces an, die für die Klasse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6403e-251">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="6403e-252">Dies ähnelt dem c#-Schlüsselwort `Using` .</span><span class="sxs-lookup"><span data-stu-id="6403e-252">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="6403e-253">Standardmäßig `Add-Type` verweist auf den **System** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="6403e-253">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="6403e-254">Wenn der Parameter " **Membership Definition** " verwendet wird, `Add-Type` verweist standardmäßig auch auf den **System. Runtime. InteropServices** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="6403e-254">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="6403e-255">Auf die Namespaces, die Sie mithilfe der **UsingNamespace** -Parameter hinzufügen, wird zusätzlich zu den standardmäßigen Namespaces verwiesen.</span><span class="sxs-lookup"><span data-stu-id="6403e-255">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

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

### <span data-ttu-id="6403e-256">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6403e-256">CommonParameters</span></span>

<span data-ttu-id="6403e-257">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6403e-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6403e-258">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6403e-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6403e-259">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6403e-259">INPUTS</span></span>

### <span data-ttu-id="6403e-260">Keine</span><span class="sxs-lookup"><span data-stu-id="6403e-260">None</span></span>

<span data-ttu-id="6403e-261">Objekte können nicht über die Pipeline an gesendet werden `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="6403e-261">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="6403e-262">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6403e-262">OUTPUTS</span></span>

### <span data-ttu-id="6403e-263">None oder System. Type</span><span class="sxs-lookup"><span data-stu-id="6403e-263">None or System.Type</span></span>

<span data-ttu-id="6403e-264">Wenn Sie den **passthru** -Parameter verwenden, `Add-Type` gibt ein **System. Type** -Objekt zurück, das den neuen Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="6403e-264">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="6403e-265">Andernfalls generiert dieses Cmdlet keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="6403e-265">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="6403e-266">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6403e-266">NOTES</span></span>

<span data-ttu-id="6403e-267">Die Typen, die Sie hinzufügen, sind nur in der aktuellen Sitzung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6403e-267">The types that you add exist only in the current session.</span></span> <span data-ttu-id="6403e-268">Um die Typen in allen Sitzungen zu verwenden, fügen Sie Sie Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="6403e-268">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="6403e-269">Weitere Informationen zum Profil finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6403e-269">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="6403e-270">Typnamen und Namespaces müssen innerhalb einer Sitzung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="6403e-270">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="6403e-271">Ein Typ kann nicht entladen oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-271">You can't unload a type or change it.</span></span> <span data-ttu-id="6403e-272">Wenn Sie den Code für einen Typ ändern müssen, müssen Sie den Namen ändern oder eine neue PowerShell-Sitzung starten.</span><span class="sxs-lookup"><span data-stu-id="6403e-272">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="6403e-273">Andernfalls führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="6403e-273">Otherwise, the command fails.</span></span>

<span data-ttu-id="6403e-274">In Windows PowerShell (Version 5,1 und niedriger) müssen Sie `Add-Type` für alles verwenden, was nicht bereits geladen ist.</span><span class="sxs-lookup"><span data-stu-id="6403e-274">In Windows PowerShell (version 5.1 and below), you need to use `Add-Type` for anything that isn't already loaded.</span></span> <span data-ttu-id="6403e-275">Dies gilt in der Regel für Assemblys, die im globalen Assemblycache (GAC) gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-275">Most commonly, this applies to assemblies found in the Global Assembly Cache (GAC).</span></span>
<span data-ttu-id="6403e-276">In PowerShell 6 und höher gibt es keinen GAC, sodass PowerShell seine eigenen Assemblys in installiert `$PSHome` .</span><span class="sxs-lookup"><span data-stu-id="6403e-276">In PowerShell 6 and higher, there is no GAC, so PowerShell installs its own assemblies in `$PSHome`.</span></span>
<span data-ttu-id="6403e-277">Diese Assemblys werden automatisch bei der Anforderung geladen, daher ist es nicht erforderlich, `Add-Type` Sie zu laden.</span><span class="sxs-lookup"><span data-stu-id="6403e-277">These assemblies are automatically loaded on request, so there's no need to use `Add-Type` to load them.</span></span> <span data-ttu-id="6403e-278">`Add-Type`Die Verwendung von ist jedoch weiterhin zulässig, damit Skripts implizit mit jeder beliebigen PowerShell-Version kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="6403e-278">However, using `Add-Type` is still permitted to allow scripts to be implicitly compatible with any version of PowerShell.</span></span>

<span data-ttu-id="6403e-279">Assemblys im GAC können nach dem Typnamen und nicht nach dem Pfad geladen werden.</span><span class="sxs-lookup"><span data-stu-id="6403e-279">Assemblies in the GAC can be loaded by type name, rather than by path.</span></span> <span data-ttu-id="6403e-280">Das Laden von Assemblys aus einem beliebigen Pfad erfordert `Add-Type` , da diese Assemblys nicht automatisch geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="6403e-280">Loading assemblies from an arbitrary path requires `Add-Type`, since those assemblies cannot not be loaded automatically.</span></span>

## <span data-ttu-id="6403e-281">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6403e-281">RELATED LINKS</span></span>

[<span data-ttu-id="6403e-282">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="6403e-282">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="6403e-283">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="6403e-283">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="6403e-284">Add-Member</span><span class="sxs-lookup"><span data-stu-id="6403e-284">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="6403e-285">New-Object</span><span class="sxs-lookup"><span data-stu-id="6403e-285">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="6403e-286">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="6403e-286">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="6403e-287">Plattformaufruf (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="6403e-287">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="6403e-288">Where-Object</span><span class="sxs-lookup"><span data-stu-id="6403e-288">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
