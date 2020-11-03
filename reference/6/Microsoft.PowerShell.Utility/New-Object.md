---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Object
ms.openlocfilehash: 3246d33174f39bf52dfa68b2dbe1e7b76a320b61
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216575"
---
# <span data-ttu-id="216c4-103">New-Object</span><span class="sxs-lookup"><span data-stu-id="216c4-103">New-Object</span></span>

## <span data-ttu-id="216c4-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="216c4-104">SYNOPSIS</span></span>
<span data-ttu-id="216c4-105">Erstellt eine Instanz eines Microsoft .NET Framework- oder COM-Objekts.</span><span class="sxs-lookup"><span data-stu-id="216c4-105">Creates an instance of a Microsoft .NET Framework or COM object.</span></span>

## <span data-ttu-id="216c4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="216c4-106">SYNTAX</span></span>

### <span data-ttu-id="216c4-107">NET (Standard)</span><span class="sxs-lookup"><span data-stu-id="216c4-107">Net (Default)</span></span>

```
New-Object [-TypeName] <String> [[-ArgumentList] <Object[]>] [-Property <IDictionary>] [<CommonParameters>]
```

### <span data-ttu-id="216c4-108">KOM</span><span class="sxs-lookup"><span data-stu-id="216c4-108">Com</span></span>

```
New-Object [-ComObject] <String> [-Strict] [-Property <IDictionary>] [<CommonParameters>]
```

## <span data-ttu-id="216c4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="216c4-109">DESCRIPTION</span></span>

<span data-ttu-id="216c4-110">Das- `New-Object` Cmdlet erstellt eine Instanz eines .NET Framework-oder COM-Objekts.</span><span class="sxs-lookup"><span data-stu-id="216c4-110">The `New-Object` cmdlet creates an instance of a .NET Framework or COM object.</span></span>

<span data-ttu-id="216c4-111">Sie können entweder den Typ einer .NET Framework-Klasse oder eine ProgID eines COM-Objekts angeben.</span><span class="sxs-lookup"><span data-stu-id="216c4-111">You can specify either the type of a .NET Framework class or a ProgID of a COM object.</span></span> <span data-ttu-id="216c4-112">Standardmäßig geben Sie den vollqualifizierten Namen einer .NET Framework-Klasse ein, und das Cmdlet gibt einen Verweis auf eine Instanz dieser Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="216c4-112">By default, you type the fully qualified name of a .NET Framework class and the cmdlet returns a reference to an instance of that class.</span></span> <span data-ttu-id="216c4-113">Um eine Instanz eines COM-Objekts zu erstellen, verwenden Sie den **ComObject** -Parameter, und geben Sie die ProgID des Objekts als Wert an.</span><span class="sxs-lookup"><span data-stu-id="216c4-113">To create an instance of a COM object, use the **ComObject** parameter and specify the ProgID of the object as its value.</span></span>

## <span data-ttu-id="216c4-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="216c4-114">EXAMPLES</span></span>

### <span data-ttu-id="216c4-115">Beispiel 1: Erstellen eines System. Version-Objekts</span><span class="sxs-lookup"><span data-stu-id="216c4-115">Example 1: Create a System.Version object</span></span>

<span data-ttu-id="216c4-116">In diesem Beispiel wird ein **System. Version** -Objekt mit der Zeichenfolge "1.2.3.4" als Konstruktor erstellt.</span><span class="sxs-lookup"><span data-stu-id="216c4-116">This example creates a **System.Version** object using the "1.2.3.4" string as the constructor.</span></span>

```powershell
New-Object -TypeName System.Version -ArgumentList "1.2.3.4"
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
1      2      3      4
```

### <span data-ttu-id="216c4-117">Beispiel 2: Erstellen eines COM-Objekts in Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="216c4-117">Example 2: Create an Internet Explorer COM object</span></span>

<span data-ttu-id="216c4-118">In diesem Beispiel werden zwei Instanzen des COM-Objekts erstellt, das die Internet Explorer-Anwendung darstellt.</span><span class="sxs-lookup"><span data-stu-id="216c4-118">This example creates two instances of the COM object that represents the Internet Explorer application.</span></span> <span data-ttu-id="216c4-119">Die erste Instanz verwendet die Hash Tabelle der **Eigenschaften** Parameter, um die **Navigate2** -Methode aufzurufen, und legt die **Visible** -Eigenschaft des-Objekts auf fest, `$True` um die Anwendung sichtbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="216c4-119">The first instance uses the **Property** parameter hash table to call the **Navigate2** method and set the **Visible** property of the object to `$True` to make the application visible.</span></span>
<span data-ttu-id="216c4-120">Die zweite Instanz erhält dieselben Ergebnisse mit einzelnen Befehlen.</span><span class="sxs-lookup"><span data-stu-id="216c4-120">The second instance gets the same results with individual commands.</span></span>

```powershell
$IE1 = New-Object -COMObject InternetExplorer.Application -Property @{Navigate2="www.microsoft.com"; Visible = $True}

# The following command gets the same results as the example above.
$IE2 = New-Object -COMObject InternetExplorer.Application`
$IE2.Navigate2("www.microsoft.com")`
$IE2.Visible = $True`
```

### <span data-ttu-id="216c4-121">Beispiel 3: Verwenden Sie den Strict-Parameter, um einen Fehler ohne Abbruch zu generieren.</span><span class="sxs-lookup"><span data-stu-id="216c4-121">Example 3: Use the Strict parameter to generate a non-terminating error</span></span>

<span data-ttu-id="216c4-122">In diesem Beispiel wird veranschaulicht, dass das Hinzufügen des **Strict** -Parameters bewirkt, dass das `New-Object` Cmdlet einen Fehler ohne Abbruch generiert, wenn das COM-Objekt eine Interop-Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="216c4-122">This example demonstrates that adding the **Strict** parameter causes the `New-Object` cmdlet to generate a non-terminating error when the COM object uses an interop assembly.</span></span>

```powershell
$A = New-Object -COMObject Word.Application -Strict -Property @{Visible = $True}
```

```Output
New-Object : The object written to the pipeline is an instance of the type
"Microsoft.Office.Interop.Word.ApplicationClass" from the component's primary interop assembly. If
this type exposes different members than the IDispatch members, scripts written to work with this
object might not work if the primary interop assembly is not installed.

At line:1 char:14
+ $A = New-Object  <<<< -COM Word.Application -Strict; $a.visible=$true
```

### <span data-ttu-id="216c4-123">Beispiel 4: Erstellen eines COM-Objekts zum Verwalten von Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="216c4-123">Example 4: Create a COM object to manage Windows desktop</span></span>

<span data-ttu-id="216c4-124">Dieses Beispiel zeigt das Erstellen und Verwenden eines COM-Objekts zur Verwaltung Ihres Windows-Desktops.</span><span class="sxs-lookup"><span data-stu-id="216c4-124">This example shows how to create and use a COM object to manage your Windows desktop.</span></span>

<span data-ttu-id="216c4-125">Der erste Befehl verwendet den **ComObject** -Parameter des `New-Object` Cmdlets zum Erstellen eines COM-Objekts mit der **Shell. Application** ProgID.</span><span class="sxs-lookup"><span data-stu-id="216c4-125">The first command uses the **ComObject** parameter of the `New-Object` cmdlet to create a COM object with the **Shell.Application** ProgID.</span></span> <span data-ttu-id="216c4-126">Das resultierende Objekt wird in der `$ObjShell` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="216c4-126">It stores the resulting object in the `$ObjShell` variable.</span></span> <span data-ttu-id="216c4-127">Mit dem zweiten Befehl `$ObjShell` wird die Variable an das `Get-Member` Cmdlet weitergeleitet, das die Eigenschaften und Methoden des COM-Objekts anzeigt.</span><span class="sxs-lookup"><span data-stu-id="216c4-127">The second command pipes the `$ObjShell` variable to the `Get-Member` cmdlet, which displays the properties and methods of the COM object.</span></span> <span data-ttu-id="216c4-128">Zu den Methoden gehört die Methode " **deggledesktop** ".</span><span class="sxs-lookup"><span data-stu-id="216c4-128">Among the methods is the **ToggleDesktop** method.</span></span> <span data-ttu-id="216c4-129">Der dritte Befehl ruft die **ToggleDesktop** -Methode des Objekts auf, um die geöffneten Fenster auf dem Desktop zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="216c4-129">The third command calls the **ToggleDesktop** method of the object to minimize the open windows on your desktop.</span></span>

```powershell
$Objshell = New-Object -COMObject "Shell.Application"
$objshell | Get-Member
$objshell.ToggleDesktop()
```

```Output
   TypeName: System.__ComObject#{866738b9-6cf2-4de8-8767-f794ebe74f4e}

Name                 MemberType Definition
----                 ---------- ----------
AddToRecent          Method     void AddToRecent (Variant, string)
BrowseForFolder      Method     Folder BrowseForFolder (int, string, int, Variant)
CanStartStopService  Method     Variant CanStartStopService (string)
CascadeWindows       Method     void CascadeWindows ()
ControlPanelItem     Method     void ControlPanelItem (string)
EjectPC              Method     void EjectPC ()
Explore              Method     void Explore (Variant)
ExplorerPolicy       Method     Variant ExplorerPolicy (string)
FileRun              Method     void FileRun ()
FindComputer         Method     void FindComputer ()
FindFiles            Method     void FindFiles ()
FindPrinter          Method     void FindPrinter (string, string, string)
GetSetting           Method     bool GetSetting (int)
GetSystemInformation Method     Variant GetSystemInformation (string)
Help                 Method     void Help ()
IsRestricted         Method     int IsRestricted (string, string)
IsServiceRunning     Method     Variant IsServiceRunning (string)
MinimizeAll          Method     void MinimizeAll ()
NameSpace            Method     Folder NameSpace (Variant)
Open                 Method     void Open (Variant)
RefreshMenu          Method     void RefreshMenu ()
ServiceStart         Method     Variant ServiceStart (string, Variant)
ServiceStop          Method     Variant ServiceStop (string, Variant)
SetTime              Method     void SetTime ()
ShellExecute         Method     void ShellExecute (string, Variant, Variant, Variant, Variant)
ShowBrowserBar       Method     Variant ShowBrowserBar (string, Variant)
ShutdownWindows      Method     void ShutdownWindows ()
Suspend              Method     void Suspend ()
TileHorizontally     Method     void TileHorizontally ()
TileVertically       Method     void TileVertically ()
ToggleDesktop        Method     void ToggleDesktop ()
TrayProperties       Method     void TrayProperties ()
UndoMinimizeALL      Method     void UndoMinimizeALL ()
Windows              Method     IDispatch Windows ()
WindowsSecurity      Method     void WindowsSecurity ()
WindowSwitcher       Method     void WindowSwitcher ()
Application          Property   IDispatch Application () {get}
Parent               Property   IDispatch Parent () {get}
```

### <span data-ttu-id="216c4-130">Beispiel 5: übergeben von mehreren Argumenten an einen Konstruktor</span><span class="sxs-lookup"><span data-stu-id="216c4-130">Example 5: Pass multiple arguments to a constructor</span></span>

<span data-ttu-id="216c4-131">In diesem Beispiel wird gezeigt, wie ein-Objekt mit einem Konstruktor erstellt wird, der mehrere Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="216c4-131">This example shows how to create an object with a constructor that takes multiple parameters.</span></span> <span data-ttu-id="216c4-132">Die Parameter müssen in ein Array eingefügt werden, wenn der Argument **List** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="216c4-132">The parameters must be put in an array when using **ArgumentList** parameter.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
$parameters = @{
    TypeName = 'System.Collections.Generic.HashSet[string]'
    ArgumentList = ([string[]]$array, [System.StringComparer]::OrdinalIgnoreCase)
}
$set = New-Object @parameters
```

<span data-ttu-id="216c4-133">PowerShell bindet jeden Member des Arrays an einen Parameter des Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="216c4-133">PowerShell binds each member of the array to a parameter of the constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="216c4-134">In diesem Beispiel werden Parameter-Verteilung zur besseren Lesbarkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="216c4-134">This example uses parameter splatting for readability.</span></span> <span data-ttu-id="216c4-135">Weitere Informationen finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="216c4-135">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

### <span data-ttu-id="216c4-136">Beispiel 6: Aufrufen eines Konstruktors, der ein Array als einzelnen Parameter annimmt</span><span class="sxs-lookup"><span data-stu-id="216c4-136">Example 6: Calling a constructor that takes an array as a single parameter</span></span>

<span data-ttu-id="216c4-137">Dieses Beispiel zeigt, wie ein Objekt mit einem Konstruktor erstellt wird, der einen Parameter annimmt, bei dem es sich um ein Array oder eine Auflistung handelt.</span><span class="sxs-lookup"><span data-stu-id="216c4-137">This example shows how to create an object with a constructor that takes a parameter that is an array or collection.</span></span> <span data-ttu-id="216c4-138">Der Array Parameter muss in ein anderes Array eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="216c4-138">The array parameter must be put in wrapped inside another array.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
# This command throws an exception.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList $array
# This command succeeds.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList (,[string[]]$array)
$set
```

```Output
New-Object : Cannot find an overload for "HashSet`1" and the argument count: "3".
At line:1 char:8
+ $set = New-Object -TypeName 'System.Collections.Generic.HashSet[strin ...
+        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidOperation: (:) [New-Object], MethodException
+ FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Commands.NewObjectCommand

One
Two
Three
```

<span data-ttu-id="216c4-139">Beim ersten Versuch, das-Objekt in diesem Beispiel zu erstellen, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="216c4-139">The first attempt to create the object in this example fails.</span></span> <span data-ttu-id="216c4-140">PowerShell hat versucht, die drei Member von `$array` an Parameter des Konstruktors zu binden, aber der Konstruktor akzeptiert nicht drei Parameter.</span><span class="sxs-lookup"><span data-stu-id="216c4-140">PowerShell attempted to bind the three members of `$array` to parameters of the constructor but the constructor does not take three parameter.</span></span> <span data-ttu-id="216c4-141">`$array`Durch das umwickeln in ein anderes Array wird verhindert, dass PowerShell versucht, die drei Member von `$array` an Parameter des Konstruktors zu binden.</span><span class="sxs-lookup"><span data-stu-id="216c4-141">Wrapping `$array` in another array prevents PowerShell from attempting to bind the three members of `$array` to parameters of the constructor.</span></span>

## <span data-ttu-id="216c4-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="216c4-142">PARAMETERS</span></span>

### <span data-ttu-id="216c4-143">-Argumentlist</span><span class="sxs-lookup"><span data-stu-id="216c4-143">-ArgumentList</span></span>

<span data-ttu-id="216c4-144">Gibt ein Array von Argumenten an, die an den Konstruktor der .NET Framework Klasse übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="216c4-144">Specifies an array of arguments to pass to the constructor of the .NET Framework class.</span></span> <span data-ttu-id="216c4-145">Wenn der Konstruktor einen einzelnen Parameter annimmt, bei dem es sich um ein Array handelt, müssen Sie diesen Parameter in einem anderen Array einschließen.</span><span class="sxs-lookup"><span data-stu-id="216c4-145">If the constructor takes a single parameter that is an array, you must wrap that parameter inside another array.</span></span> <span data-ttu-id="216c4-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="216c4-146">For example:</span></span>

`$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList (,$bytes)`

<span data-ttu-id="216c4-147">Weitere Informationen zum Verhalten von **argumentlist** finden Sie unter [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="216c4-147">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="216c4-148">Der Alias für **ArgumentList** ist **Args** .</span><span class="sxs-lookup"><span data-stu-id="216c4-148">The alias for **ArgumentList** is **Args** .</span></span>

```yaml
Type: System.Object[]
Parameter Sets: Net
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="216c4-149">-ComObject</span><span class="sxs-lookup"><span data-stu-id="216c4-149">-ComObject</span></span>

<span data-ttu-id="216c4-150">Gibt den Programmbezeichner (ProgID) des COM-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="216c4-150">Specifies the programmatic identifier (ProgID) of the COM object.</span></span>

```yaml
Type: System.String
Parameter Sets: Com
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="216c4-151">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="216c4-151">-Property</span></span>

<span data-ttu-id="216c4-152">Legt Eigenschaftswerte fest und ruft Methoden des neuen Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="216c4-152">Sets property values and invokes methods of the new object.</span></span>

<span data-ttu-id="216c4-153">Geben Sie eine Hashtabelle ein, in der die Schlüssel die Namen von Eigenschaften oder Methoden und die Werte Eigenschaftswerte oder Methodenargumente sind.</span><span class="sxs-lookup"><span data-stu-id="216c4-153">Enter a hash table in which the keys are the names of properties or methods and the values are property values or method arguments.</span></span> <span data-ttu-id="216c4-154">`New-Object` erstellt das-Objekt und legt die einzelnen Eigenschaftswerte fest und ruft jede Methode in der Reihenfolge auf, in der Sie in der Hash Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="216c4-154">`New-Object` creates the object and sets each property value and invokes each method in the order that they appear in the hash table.</span></span>

<span data-ttu-id="216c4-155">Wenn das neue Objekt von der **psobject** -Klasse abgeleitet wird und Sie eine Eigenschaft angeben, die im Objekt nicht vorhanden ist, `New-Object` fügt die angegebene Eigenschaft dem Objekt als NoteProperty hinzu.</span><span class="sxs-lookup"><span data-stu-id="216c4-155">If the new object is derived from the **PSObject** class, and you specify a property that does not exist on the object, `New-Object` adds the specified property to the object as a NoteProperty.</span></span> <span data-ttu-id="216c4-156">Wenn das Objekt kein **psobject** ist, generiert der Befehl einen Fehler ohne Abbruch.</span><span class="sxs-lookup"><span data-stu-id="216c4-156">If the object is not a **PSObject** , the command generates a non-terminating error.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="216c4-157">-Strict</span><span class="sxs-lookup"><span data-stu-id="216c4-157">-Strict</span></span>

<span data-ttu-id="216c4-158">Gibt an, dass das Cmdlet einen Fehler ohne Abbruch generiert, wenn ein COM-Objekt, das Sie zu erstellen versuchen, eine Interop-Assembly verwendet.</span><span class="sxs-lookup"><span data-stu-id="216c4-158">Indicates that the cmdlet generates a non-terminating error when a COM object that you attempt to create uses an interop assembly.</span></span> <span data-ttu-id="216c4-159">Dieses Feature unterscheidet tatsächliche COM-Objekte von .NET Framework-Objekten mit COM Callable Wrappers.</span><span class="sxs-lookup"><span data-stu-id="216c4-159">This feature distinguishes actual COM objects from .NET Framework objects with COM-callable wrappers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Com
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="216c4-160">-Typname</span><span class="sxs-lookup"><span data-stu-id="216c4-160">-TypeName</span></span>

<span data-ttu-id="216c4-161">Gibt den vollqualifizierten Namen der .NET Framework-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="216c4-161">Specifies the fully qualified name of the .NET Framework class.</span></span> <span data-ttu-id="216c4-162">Sie können nicht gleichzeitig den **tykame** -Parameter und den **ComObject** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="216c4-162">You cannot specify both the **TypeName** parameter and the **ComObject** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: Net
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="216c4-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="216c4-163">CommonParameters</span></span>

<span data-ttu-id="216c4-164">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="216c4-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="216c4-165">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="216c4-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="216c4-166">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="216c4-166">INPUTS</span></span>

### <span data-ttu-id="216c4-167">Keine</span><span class="sxs-lookup"><span data-stu-id="216c4-167">None</span></span>

<span data-ttu-id="216c4-168">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="216c4-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="216c4-169">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="216c4-169">OUTPUTS</span></span>

### <span data-ttu-id="216c4-170">Object</span><span class="sxs-lookup"><span data-stu-id="216c4-170">Object</span></span>

<span data-ttu-id="216c4-171">`New-Object` Gibt das-Objekt zurück, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="216c4-171">`New-Object` returns the object that is created.</span></span>

## <span data-ttu-id="216c4-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="216c4-172">NOTES</span></span>

- <span data-ttu-id="216c4-173">`New-Object` stellt die am häufigsten verwendete Funktionalität der VBScript-Funktion "deateobject" bereit.</span><span class="sxs-lookup"><span data-stu-id="216c4-173">`New-Object` provides the most commonly-used functionality of the VBScript CreateObject function.</span></span> <span data-ttu-id="216c4-174">Eine Anweisung wie `Set objShell = CreateObject("Shell.Application")` in VBScript kann `$objShell = New-Object -COMObject "Shell.Application"` in PowerShell in übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="216c4-174">A statement like `Set objShell = CreateObject("Shell.Application")` in VBScript can be translated to `$objShell = New-Object -COMObject "Shell.Application"` in PowerShell.</span></span>
- <span data-ttu-id="216c4-175">`New-Object` erweitert die Funktionen, die in der Windows Script Host-Umgebung verfügbar sind, indem die Arbeit mit .NET Framework-Objekten über die Befehlszeile und innerhalb von Skripts vereinfacht wird.</span><span class="sxs-lookup"><span data-stu-id="216c4-175">`New-Object` expands upon the functionality available in the Windows Script Host environment by making it easy to work with .NET Framework objects from the command line and within scripts.</span></span>

## <span data-ttu-id="216c4-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="216c4-176">RELATED LINKS</span></span>

[<span data-ttu-id="216c4-177">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="216c4-177">about_Object_Creation</span></span>](../Microsoft.PowerShell.Core/About/about_Object_Creation.md)

[<span data-ttu-id="216c4-178">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="216c4-178">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="216c4-179">Group-Object</span><span class="sxs-lookup"><span data-stu-id="216c4-179">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="216c4-180">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="216c4-180">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="216c4-181">Select-Object</span><span class="sxs-lookup"><span data-stu-id="216c4-181">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="216c4-182">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="216c4-182">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="216c4-183">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="216c4-183">Tee-Object</span></span>](Tee-Object.md)
