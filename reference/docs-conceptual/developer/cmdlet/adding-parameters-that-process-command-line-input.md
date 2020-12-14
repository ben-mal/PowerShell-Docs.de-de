---
ms.date: 09/13/2016
ms.topic: reference
title: Hinzufügen von Parametern, die Befehlszeileneingaben verarbeiten
description: Hinzufügen von Parametern, die Befehlszeileneingaben verarbeiten
ms.openlocfilehash: f20469d366330aa787fbc16e4f0a76e67fc7c6db
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "93354608"
---
# <a name="adding-parameters-that-process-command-line-input"></a><span data-ttu-id="43d82-103">Hinzufügen von Parametern, die Befehlszeileneingaben verarbeiten</span><span class="sxs-lookup"><span data-stu-id="43d82-103">Adding Parameters That Process Command-Line Input</span></span>

<span data-ttu-id="43d82-104">Eine Eingabe Quelle für ein Cmdlet ist die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="43d82-104">One source of input for a cmdlet is the command line.</span></span> <span data-ttu-id="43d82-105">In diesem Thema wird beschrieben, wie Sie dem Cmdlet einen Parameter hinzufügen `Get-Proc` (der unter [Erstellen des ersten Cmdlets](./creating-a-cmdlet-without-parameters.md)beschrieben wird), damit das Cmdlet Eingaben vom lokalen Computer auf der Grundlage von expliziten Objekten verarbeiten kann, die an das Cmdlet übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="43d82-105">This topic describes how to add a parameter to the `Get-Proc` cmdlet (which is described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process input from the local computer based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="43d82-106">Das `Get-Proc` hier beschriebene Cmdlet ruft die Prozesse auf der Grundlage ihrer Namen ab und zeigt dann Informationen zu den Prozessen an einer Eingabeaufforderung an.</span><span class="sxs-lookup"><span data-stu-id="43d82-106">The `Get-Proc` cmdlet described here retrieves processes based on their names, and then displays information about the processes at a command prompt.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="43d82-107">Definieren der Cmdlet-Klasse</span><span class="sxs-lookup"><span data-stu-id="43d82-107">Defining the Cmdlet Class</span></span>

<span data-ttu-id="43d82-108">Der erste Schritt bei der Cmdlet-Erstellung ist die Cmdlet-Benennung und die Deklaration der .NET Framework Klasse, die das Cmdlet implementiert.</span><span class="sxs-lookup"><span data-stu-id="43d82-108">The first step in cmdlet creation is cmdlet naming and the declaration of the .NET Framework class that implements the cmdlet.</span></span> <span data-ttu-id="43d82-109">Dieses Cmdlet ruft Prozessinformationen ab, sodass der hier gewählte Verb Name "Get" lautet.</span><span class="sxs-lookup"><span data-stu-id="43d82-109">This cmdlet retrieves process information, so the verb name chosen here is "Get."</span></span> <span data-ttu-id="43d82-110">(Fast jede Art von Cmdlet, das Informationen abrufen kann, kann die Befehlszeilen Eingabe verarbeiten.) Weitere Informationen zu genehmigten Cmdlet-Verben finden Sie unter [Cmdlet-Verb Namen](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="43d82-110">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="43d82-111">Hier ist die Klassen Deklaration für das `Get-Proc` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43d82-111">Here's the class declaration for the `Get-Proc` cmdlet.</span></span> <span data-ttu-id="43d82-112">Details zu dieser Definition finden Sie unter [Erstellen des ersten Cmdlets](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="43d82-112">Details about this definition are provided in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a><span data-ttu-id="43d82-113">Deklarieren der Parameter</span><span class="sxs-lookup"><span data-stu-id="43d82-113">Declaring Parameters</span></span>

<span data-ttu-id="43d82-114">Mit einem Cmdlet-Parameter kann der Benutzereingaben für das Cmdlet bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="43d82-114">A cmdlet parameter enables the user to provide input to the cmdlet.</span></span> <span data-ttu-id="43d82-115">Im folgenden Beispiel `Get-Proc` `Get-Member` sind und die Namen von Pipeline-Cmdlets, und `MemberType` ist ein Parameter für das `Get-Member` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="43d82-115">In the following example, `Get-Proc` and `Get-Member` are the names of pipelined cmdlets, and `MemberType` is a parameter for the `Get-Member` cmdlet.</span></span> <span data-ttu-id="43d82-116">Der-Parameter hat das Argument "Property".</span><span class="sxs-lookup"><span data-stu-id="43d82-116">The parameter has the argument "property."</span></span>

<span data-ttu-id="43d82-117">**PS> Get-proc; `get-member` -Membership Type (Eigenschaft)**</span><span class="sxs-lookup"><span data-stu-id="43d82-117">**PS> get-proc ; `get-member` -membertype property**</span></span>

<span data-ttu-id="43d82-118">Um Parameter für ein Cmdlet zu deklarieren, müssen Sie zunächst die Eigenschaften definieren, die die Parameter darstellen.</span><span class="sxs-lookup"><span data-stu-id="43d82-118">To declare parameters for a cmdlet, you must first define the properties that represent the parameters.</span></span> <span data-ttu-id="43d82-119">Im `Get-Proc` Cmdlet ist der einzige Parameter, der `Name` in diesem Fall den Namen des abzurufenden .NET Framework Prozess Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="43d82-119">In the `Get-Proc` cmdlet, the only parameter is `Name`, which in this case represents the name of the .NET Framework process object to retrieve.</span></span> <span data-ttu-id="43d82-120">Daher definiert die Cmdlet-Klasse eine Eigenschaft vom Typ "String", um ein Array von Namen zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="43d82-120">Therefore, the cmdlet class defines a property of type string to accept an array of names.</span></span>

<span data-ttu-id="43d82-121">Hier ist die Parameter Deklaration für den- `Name` Parameter des `Get-Proc` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="43d82-121">Here's the parameter declaration for the `Name` parameter of the `Get-Proc` cmdlet.</span></span>

```csharp
/// <summary>
/// Specify the cmdlet Name parameter.
/// </summary>
  [Parameter(Position = 0)]
  [ValidateNotNullOrEmpty]
  public string[] Name
  {
    get { return processNames; }
    set { processNames = value; }
  }
  private string[] processNames;

  #endregion Parameters
```

```vb
<Parameter(Position:=0), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

<span data-ttu-id="43d82-122">Um die Windows PowerShell-Laufzeit darüber zu informieren, dass diese Eigenschaft der- `Name` Parameter ist, wird der Eigenschafts Definition ein [System. Management. Automation. Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) -Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="43d82-122">To inform the Windows PowerShell runtime that this property is the `Name` parameter, a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute is added to the property definition.</span></span> <span data-ttu-id="43d82-123">Die grundlegende Syntax zum Deklarieren dieses Attributs ist `[Parameter()]` .</span><span class="sxs-lookup"><span data-stu-id="43d82-123">The basic syntax for declaring this attribute is `[Parameter()]`.</span></span>

> [!NOTE]
> <span data-ttu-id="43d82-124">Ein Parameter muss explizit als public gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="43d82-124">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="43d82-125">Parameter, die nicht als öffentlich gekennzeichnet sind, sind standardmäßig intern und werden von der Windows PowerShell-Laufzeit nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="43d82-125">Parameters that are not marked as public default to internal and are not found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="43d82-126">Dieses Cmdlet verwendet ein Zeichen folgen Array für den `Name` Parameter.</span><span class="sxs-lookup"><span data-stu-id="43d82-126">This cmdlet uses an array of strings for the `Name` parameter.</span></span> <span data-ttu-id="43d82-127">Wenn möglich, sollte Ihr Cmdlet auch einen Parameter als Array definieren, da das Cmdlet somit mehr als ein Element annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="43d82-127">If possible, your cmdlet should also define a parameter as an array, because this allows the cmdlet to accept more than one item.</span></span>

#### <a name="things-to-remember-about-parameter-definitions"></a><span data-ttu-id="43d82-128">Dinge, die Sie über Parameter Definitionen merken müssen</span><span class="sxs-lookup"><span data-stu-id="43d82-128">Things to Remember About Parameter Definitions</span></span>

- <span data-ttu-id="43d82-129">Vordefinierte Windows PowerShell-Parameternamen und-Datentypen sollten so weit wie möglich wieder verwendet werden, um sicherzustellen, dass Ihr Cmdlet mit Windows PowerShell-Cmdlets kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="43d82-129">Predefined Windows PowerShell parameter names and data types should be reused as much as possible to ensure that your cmdlet is compatible with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="43d82-130">Wenn beispielsweise alle Cmdlets den vordefinierten `Id` Parameternamen verwenden, um eine Ressource zu identifizieren, kann der Benutzer leicht die Bedeutung des Parameters erkennen, unabhängig davon, welches Cmdlet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="43d82-130">For example, if all cmdlets use the predefined `Id` parameter name to identify a resource, user will easily understand the meaning of the parameter, regardless of what cmdlet they are using.</span></span> <span data-ttu-id="43d82-131">Im Grunde folgen Parameternamen denselben Regeln wie die, die für Variablennamen im Common Language Runtime (CLR) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43d82-131">Basically, parameter names follow the same rules as those used for variable names in the common language runtime (CLR).</span></span> <span data-ttu-id="43d82-132">Weitere Informationen zum Benennen von Parametern finden [Sie unter Cmdlet-Parameternamen](/previous-versions/ms714468(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="43d82-132">For more information about parameter naming, see [Cmdlet Parameter Names](/previous-versions/ms714468(v=vs.85)).</span></span>

- <span data-ttu-id="43d82-133">Windows PowerShell reserviert einige Parameternamen, um eine konsistente Benutzer Leistung zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="43d82-133">Windows PowerShell reserves a few parameter names to provide a consistent user experience.</span></span> <span data-ttu-id="43d82-134">Verwenden Sie diese Parameternamen nicht: `WhatIf` , `Confirm` , `Verbose` , `Debug` , `Warn` , `ErrorAction` , `ErrorVariable` , `OutVariable` und `OutBuffer` .</span><span class="sxs-lookup"><span data-stu-id="43d82-134">Do not use these parameter names: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`, and `OutBuffer`.</span></span> <span data-ttu-id="43d82-135">Außerdem sind die folgenden Aliase für diese Parameternamen reserviert: `vb` , `db` , `ea` , `ev` , `ov` und `ob` .</span><span class="sxs-lookup"><span data-stu-id="43d82-135">Additionally, the following aliases for these parameter names are reserved: `vb`, `db`, `ea`, `ev`, `ov`, and `ob`.</span></span>

- <span data-ttu-id="43d82-136">`Name` bei handelt es sich um einen einfachen und allgemeinen Parameternamen, der für die Verwendung in ihren Cmdlets empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="43d82-136">`Name` is a simple and common parameter name, recommended for use in your cmdlets.</span></span> <span data-ttu-id="43d82-137">Es empfiehlt sich, einen Parameternamen wie diesen als einen komplexen Namen auszuwählen, der für ein bestimmtes Cmdlet eindeutig ist und schwer zu merken ist.</span><span class="sxs-lookup"><span data-stu-id="43d82-137">It is better to choose a parameter name like this than a complex name that is unique to a specific cmdlet and hard to remember.</span></span>

- <span data-ttu-id="43d82-138">Bei Parametern wird in Windows PowerShell die Groß-/Kleinschreibung nicht beachtet, obwohl die Shell standardmäßig die groß-</span><span class="sxs-lookup"><span data-stu-id="43d82-138">Parameters are case-insensitive in Windows PowerShell, although by default the shell preserves case.</span></span> <span data-ttu-id="43d82-139">Die Groß-/Kleinschreibung der Argumente hängt von der Operation des Cmdlets ab.</span><span class="sxs-lookup"><span data-stu-id="43d82-139">Case-sensitivity of the arguments depends on the operation of the cmdlet.</span></span> <span data-ttu-id="43d82-140">Argumente werden an einen Parameter übergeben, wie in der Befehlszeile angegeben.</span><span class="sxs-lookup"><span data-stu-id="43d82-140">Arguments are passed to a parameter as specified at the command line.</span></span>

- <span data-ttu-id="43d82-141">Beispiele für andere Parameter Deklarationen finden Sie unter [Cmdlet-Parameter](./cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="43d82-141">For examples of other parameter declarations, see [Cmdlet Parameters](./cmdlet-parameters.md).</span></span>

## <a name="declaring-parameters-as-positional-or-named"></a><span data-ttu-id="43d82-142">Deklarieren von Parametern als Positions-oder benannte Parameter</span><span class="sxs-lookup"><span data-stu-id="43d82-142">Declaring Parameters as Positional or Named</span></span>

<span data-ttu-id="43d82-143">Ein Cmdlet muss jeden Parameter entweder als Positions Parameter oder als benannten Parameter festlegen.</span><span class="sxs-lookup"><span data-stu-id="43d82-143">A cmdlet must set each parameter as either a positional or named parameter.</span></span> <span data-ttu-id="43d82-144">Beide Arten von Parametern akzeptieren einzelne Argumente, mehrere durch Kommas getrennte Argumente und boolesche Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="43d82-144">Both kinds of parameters accept single arguments, multiple arguments separated by commas, and Boolean settings.</span></span> <span data-ttu-id="43d82-145">Bei einem booleschen Parameter, der auch als *Switch* bezeichnet wird, werden nur boolesche Einstellungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="43d82-145">A Boolean parameter, also called a *switch*, handles only Boolean settings.</span></span> <span data-ttu-id="43d82-146">Der-Schalter wird verwendet, um das vorhanden sein des-Parameters zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="43d82-146">The switch is used to determine the presence of the parameter.</span></span> <span data-ttu-id="43d82-147">Der empfohlene Standardwert ist `false` .</span><span class="sxs-lookup"><span data-stu-id="43d82-147">The recommended default is `false`.</span></span>

<span data-ttu-id="43d82-148">Das `Get-Proc` Cmdlet "Sample" definiert den `Name` Parameter als Positions Parameter mit der Position.</span><span class="sxs-lookup"><span data-stu-id="43d82-148">The sample `Get-Proc` cmdlet defines the `Name` parameter as a positional parameter with position</span></span>
0. <span data-ttu-id="43d82-149">Dies bedeutet, dass das erste Argument, das der Benutzer in der Befehlszeile eingibt, automatisch für diesen Parameter eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="43d82-149">This means that the first argument the user enters on the command line is automatically inserted for this parameter.</span></span> <span data-ttu-id="43d82-150">Wenn Sie einen benannten Parameter definieren möchten, für den der Benutzer den Parameternamen in der Befehlszeile angeben muss, lassen Sie das `Position` Schlüsselwort aus der Attribut Deklaration aus.</span><span class="sxs-lookup"><span data-stu-id="43d82-150">If you want to define a named parameter, for which the user must specify the parameter name from the command line, leave the `Position` keyword out of the attribute declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="43d82-151">Wenn Parameter nicht benannt werden müssen, empfiehlt es sich, die am häufigsten verwendeten Parameter positionell zu machen, damit Benutzer den Parameternamen nicht eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="43d82-151">Unless parameters must be named, we recommend that you make the most-used parameters positional so that users will not have to type the parameter name.</span></span>

## <a name="declaring-parameters-as-mandatory-or-optional"></a><span data-ttu-id="43d82-152">Deklarieren von Parametern als obligatorisch oder optional</span><span class="sxs-lookup"><span data-stu-id="43d82-152">Declaring Parameters as Mandatory or Optional</span></span>

<span data-ttu-id="43d82-153">Ein Cmdlet muss jeden Parameter entweder als optionalen oder als obligatorischen Parameter festlegen.</span><span class="sxs-lookup"><span data-stu-id="43d82-153">A cmdlet must set each parameter as either an optional or a mandatory parameter.</span></span> <span data-ttu-id="43d82-154">Im-Beispiel- `Get-Proc` Cmdlet wird der- `Name` Parameter als optional definiert, da das- `Mandatory` Schlüsselwort nicht in der Attribut Deklaration festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="43d82-154">In the sample `Get-Proc` cmdlet, the `Name` parameter is defined as optional because the `Mandatory` keyword is not set in the attribute declaration.</span></span>

## <a name="supporting-parameter-validation"></a><span data-ttu-id="43d82-155">Unterstützende Parameter Validierung</span><span class="sxs-lookup"><span data-stu-id="43d82-155">Supporting Parameter Validation</span></span>

<span data-ttu-id="43d82-156">Das Beispiel- `Get-Proc` Cmdlet fügt dem-Parameter ein Eingabe Validierungs Attribut ( [System. Management. Automation. validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute)) hinzu, `Name` um die Validierung zu aktivieren, dass die Eingabe weder `null` noch leer ist.</span><span class="sxs-lookup"><span data-stu-id="43d82-156">The sample `Get-Proc` cmdlet adds an input validation attribute, [System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), to the `Name` parameter to enable validation that the input is neither `null` nor empty.</span></span> <span data-ttu-id="43d82-157">Dieses Attribut ist eines von mehreren Validierungs Attributen, die von Windows PowerShell bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="43d82-157">This attribute is one of several validation attributes provided by Windows PowerShell.</span></span> <span data-ttu-id="43d82-158">Beispiele für andere Validierungs Attribute finden Sie unter [Validieren von Parameter Eingaben](./validating-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="43d82-158">For examples of other validation attributes, see [Validating Parameter Input](./validating-parameter-input.md).</span></span>

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="43d82-159">Überschreiben einer Eingabe Verarbeitungsmethode</span><span class="sxs-lookup"><span data-stu-id="43d82-159">Overriding an Input Processing Method</span></span>

<span data-ttu-id="43d82-160">Wenn das Cmdlet die Befehlszeilen Eingabe verarbeiten soll, müssen die entsprechenden Eingabe Verarbeitungsmethoden überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="43d82-160">If your cmdlet is to handle command-line input, it must override the appropriate input processing methods.</span></span> <span data-ttu-id="43d82-161">Die grundlegenden Eingabe Verarbeitungsmethoden werden beim [Erstellen des ersten Cmdlets](./creating-a-cmdlet-without-parameters.md)eingeführt.</span><span class="sxs-lookup"><span data-stu-id="43d82-161">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="43d82-162">Das- `Get-Proc` Cmdlet überschreibt die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode, um die `Name` vom Benutzer oder einem Skript bereitgestellten Parameter Eingaben zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="43d82-162">The `Get-Proc` cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="43d82-163">Diese Methode ruft die Prozesse für die einzelnen angeforderten Prozessnamen ab oder alle für Prozesse, wenn kein Name angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="43d82-163">This method gets the processes for each requested process name, or all for processes if no name is provided.</span></span> <span data-ttu-id="43d82-164">Beachten Sie, dass in " [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)" der [System. Management. Automation. Cmdlet. Write-Object% 28system. Object% 2csystem. Boolean %29](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) aufgerufen wird. Dies ist der Ausgabe Mechanismus zum Senden von Ausgabe Objekten an die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="43d82-164">Notice that in [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="43d82-165">Der zweite Parameter dieses `enumerateCollection` Aufrufes,, ist auf festgelegt, `true` um die Windows PowerShell-Laufzeit anzuweisen, das Ausgabe Array von Prozess Objekten aufzulisten und jeweils einen Prozess in die Befehlszeile zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="43d82-165">The second parameter of this call, `enumerateCollection`, is set to `true` to inform the Windows PowerShell runtime to enumerate the output array of process objects and write one process at a time to the command line.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
    // Write the processes to the pipeline making them available
    // to the next cmdlet. The second argument of this call tells
    // PowerShell to enumerate the array, and send one process at a
    // time to the pipeline.
    WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    }
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        Dim processes As Process()
        processes = Process.GetProcesses()
    End If

    '/ If process names are specified, write the processes to the
    '/ pipeline to display them or make them available to the next cmdlet.

    For Each name As String In processNames
        '/ The second parameter of this call tells PowerShell to enumerate the
        '/ array, and send one process at a time to the pipeline.
        WriteObject(Process.GetProcessesByName(name), True)
    Next

End Sub 'ProcessRecord
```

## <a name="code-sample"></a><span data-ttu-id="43d82-166">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="43d82-166">Code Sample</span></span>

<span data-ttu-id="43d82-167">Den gesamten c#-Beispielcode finden Sie unter [GetProcessSample02 Sample](./getprocesssample02-sample.md).</span><span class="sxs-lookup"><span data-stu-id="43d82-167">For the complete C# sample code, see [GetProcessSample02 Sample](./getprocesssample02-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="43d82-168">Definieren von Objekttypen und Formatierung</span><span class="sxs-lookup"><span data-stu-id="43d82-168">Defining Object Types and Formatting</span></span>

<span data-ttu-id="43d82-169">Windows PowerShell übergibt mithilfe .NET Framework-Objekten Informationen zwischen Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="43d82-169">Windows PowerShell passes information between cmdlets by using .NET Framework objects.</span></span> <span data-ttu-id="43d82-170">Folglich muss ein Cmdlet möglicherweise seinen eigenen Typ definieren, oder ein Cmdlet muss möglicherweise einen vorhandenen Typ erweitern, der von einem anderen Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="43d82-170">Consequently, a cmdlet might need to define its own type, or a cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="43d82-171">Weitere Informationen zum Definieren neuer Typen oder zum Erweitern vorhandener Typen finden Sie unter [Erweitern von Objekttypen und Formatierung](/previous-versions/ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="43d82-171">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="43d82-172">Cmdlet wird aufgebaut</span><span class="sxs-lookup"><span data-stu-id="43d82-172">Building the Cmdlet</span></span>

<span data-ttu-id="43d82-173">Nachdem Sie ein Cmdlet implementiert haben, müssen Sie es mithilfe eines Windows PowerShell-Snap-Ins bei Windows PowerShell registrieren.</span><span class="sxs-lookup"><span data-stu-id="43d82-173">After you implement a cmdlet, you must register it with Windows PowerShell by using a Windows PowerShell snap-in.</span></span> <span data-ttu-id="43d82-174">Weitere Informationen zum Registrieren von Cmdlets finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions/ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="43d82-174">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="43d82-175">Testen des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="43d82-175">Testing the Cmdlet</span></span>

<span data-ttu-id="43d82-176">Wenn Ihr Cmdlet bei Windows PowerShell registriert ist, können Sie es in der Befehlszeile testen.</span><span class="sxs-lookup"><span data-stu-id="43d82-176">When your cmdlet is registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="43d82-177">Im folgenden finden Sie zwei Möglichkeiten, den Code für das-Beispiel-Cmdlet zu testen.</span><span class="sxs-lookup"><span data-stu-id="43d82-177">Here are two ways to test the code for the sample cmdlet.</span></span> <span data-ttu-id="43d82-178">Weitere Informationen zur Verwendung von Cmdlets über die Befehlszeile finden Sie unter [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="43d82-178">For more information about using cmdlets from the command line, see [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="43d82-179">Führen Sie an der Windows PowerShell-Eingabeaufforderung den folgenden Befehl aus, um den Internet Explorer-Prozess mit dem Namen "Iexplore" aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="43d82-179">At the Windows PowerShell prompt, use the following command to list the Internet Explorer process, which is named "IEXPLORE."</span></span>

  ```powershell
  get-proc -name iexplore
  ```

  <span data-ttu-id="43d82-180">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="43d82-180">The following output appears.</span></span>

  ```Output
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----   ------ --   -----------
      354      11  10036   18992    85   0.67   3284   iexplore
  ```

- <span data-ttu-id="43d82-181">Verwenden Sie den folgenden Befehl, um die Internet Explorer-, Outlook-und Notepad-Prozesse mit dem Namen "Iexplore", "Outlook" und "Notepad" aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="43d82-181">To list the Internet Explorer, Outlook, and Notepad processes named "IEXPLORE," "OUTLOOK," and "NOTEPAD," use the following command.</span></span> <span data-ttu-id="43d82-182">Wenn mehrere Prozesse vorhanden sind, werden alle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="43d82-182">If there are multiple processes, all of them are displayed.</span></span>

  ```powershell
  get-proc -name iexplore, outlook, notepad
  ```

  <span data-ttu-id="43d82-183">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="43d82-183">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----  ------   --   -----------
      732      21  24696    5000    138   2.25  2288   iexplore
      715      19  20556   14116    136   1.78  3860   iexplore
     3917      62  74096   58112    468 191.56  1848   OUTLOOK
       39       2   1024    3280     30   0.09  1444   notepad
       39       2   1024     356     30   0.08  3396   notepad
  ```

## <a name="see-also"></a><span data-ttu-id="43d82-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43d82-184">See Also</span></span>

[<span data-ttu-id="43d82-185">Hinzufügen von Parametern, die Pipelineeingaben verarbeiten</span><span class="sxs-lookup"><span data-stu-id="43d82-185">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="43d82-186">Erstellen Ihres ersten Cmdlets</span><span class="sxs-lookup"><span data-stu-id="43d82-186">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="43d82-187">[Erweitern von Objekttypen und Formatierung](/previous-versions/ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="43d82-187">[Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85))</span></span>

<span data-ttu-id="43d82-188">[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="43d82-188">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="43d82-189">Windows PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="43d82-189">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="43d82-190">Cmdlet-Beispiele</span><span class="sxs-lookup"><span data-stu-id="43d82-190">Cmdlet Samples</span></span>](./cmdlet-samples.md)
