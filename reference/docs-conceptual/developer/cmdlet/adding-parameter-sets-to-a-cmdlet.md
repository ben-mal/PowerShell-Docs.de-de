---
title: Hinzufügen von Parameter Sätzen zu einem Cmdlet | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- parameter sets [PowerShell Programmer's Guide]
ms.openlocfilehash: b1e808694b02676d81101a2678cbea341c7bd52c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774982"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a><span data-ttu-id="9bfd5-102">Hinzufügen von Parametersätzen zu einem Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9bfd5-102">Adding Parameter Sets to a Cmdlet</span></span>

## <a name="things-to-know-about-parameter-sets"></a><span data-ttu-id="9bfd5-103">Dinge, die Sie über Parameter Sätze wissen müssen</span><span class="sxs-lookup"><span data-stu-id="9bfd5-103">Things to Know About Parameter Sets</span></span>

<span data-ttu-id="9bfd5-104">Windows PowerShell definiert einen Parametersatz als eine Gruppe von Parametern, die zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-104">Windows PowerShell defines a parameter set as a group of parameters that operate together.</span></span> <span data-ttu-id="9bfd5-105">Indem Sie die Parameter eines Cmdlets gruppieren, können Sie ein einzelnes Cmdlet erstellen, das seine Funktionalität basierend auf der vom Benutzer festgelegten Gruppe von Parametern ändern kann.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-105">By grouping the parameters of a cmdlet, you can create a single cmdlet that can change its functionality based on what group of parameters the user specifies.</span></span>

<span data-ttu-id="9bfd5-106">Ein Beispiel für ein Cmdlet, das zwei Parametersätze verwendet, um unterschiedliche Funktionen zu definieren, ist das `Get-EventLog` Cmdlet, das von Windows PowerShell bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-106">An example of a cmdlet that uses two parameter sets to define different functionalities is the `Get-EventLog` cmdlet that is provided by Windows PowerShell.</span></span> <span data-ttu-id="9bfd5-107">Dieses Cmdlet gibt andere Informationen zurück, wenn der Benutzer den- `List` Parameter oder den- `LogName` Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-107">This cmdlet returns different information when the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="9bfd5-108">Wenn der- `LogName` Parameter angegeben wird, gibt das Cmdlet Informationen zu den Ereignissen in einem bestimmten Ereignisprotokoll zurück.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-108">If the `LogName` parameter is specified, the cmdlet returns information about the events in a given event log.</span></span> <span data-ttu-id="9bfd5-109">Wenn der- `List` Parameter angegeben wird, gibt das Cmdlet Informationen zu den Protokolldateien selbst zurück (nicht zu den darin enthaltenen Ereignis Informationen).</span><span class="sxs-lookup"><span data-stu-id="9bfd5-109">If the `List` parameter is specified, the cmdlet returns information about the log files themselves (not the event information they contain).</span></span> <span data-ttu-id="9bfd5-110">In diesem Fall identifizieren der `List` -Parameter und der- `LogName` Parameter zwei separate Parametersätze.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-110">In this case, the `List` and `LogName` parameters identify two separate parameter sets.</span></span>

<span data-ttu-id="9bfd5-111">Zwei wichtige Punkte, die bei Parametersätzen beachtet werden sollten, besteht darin, dass die Windows PowerShell-Runtime nur einen Parametersatz für eine bestimmte Eingabe verwendet und jeder Parametersatz mindestens einen Parameter aufweisen muss, der für diesen Parametersatz eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-111">Two important things to remember about parameter sets is that the Windows PowerShell runtime uses only one parameter set for a particular input, and that each parameter set must have at least one parameter that is unique for that parameter set.</span></span>

<span data-ttu-id="9bfd5-112">Um den letzten Punkt zu veranschaulichen, verwendet dieses Cmdlet "Break-proc" drei Parametersätze: `ProcessName` , `ProcessId` und `InputObject` .</span><span class="sxs-lookup"><span data-stu-id="9bfd5-112">To illustrate that last point, this Stop-Proc cmdlet uses three parameter sets: `ProcessName`, `ProcessId`, and `InputObject`.</span></span> <span data-ttu-id="9bfd5-113">Jeder dieser Parametersätze verfügt über einen Parameter, der nicht in den anderen Parametersätzen liegt.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-113">Each of these parameter sets has one parameter that is not in the other parameter sets.</span></span> <span data-ttu-id="9bfd5-114">Die Parametersätze können andere Parameter gemeinsam verwenden, aber das Cmdlet verwendet die eindeutigen Parameter, `ProcessName` `ProcessId` und, `InputObject` um zu ermitteln, welche Parametergruppe von der Windows PowerShell-Laufzeit verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-114">The parameter sets could share other parameters, but the cmdlet uses the unique parameters `ProcessName`, `ProcessId`, and `InputObject` to identify which set of parameters that the Windows PowerShell runtime should use.</span></span>

## <a name="declaring-the-cmdlet-class"></a><span data-ttu-id="9bfd5-115">Deklarieren der Cmdlet-Klasse</span><span class="sxs-lookup"><span data-stu-id="9bfd5-115">Declaring the Cmdlet Class</span></span>

<span data-ttu-id="9bfd5-116">Der erste Schritt bei der Cmdlet-Erstellung ist die Benennung des Cmdlets und das Deklarieren der .NET-Klasse, die das Cmdlet implementiert.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-116">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="9bfd5-117">Für dieses Cmdlet wird das Lebenszyklus Verb "Stopp" verwendet, da das Cmdlet System Prozesse stoppt.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-117">For this cmdlet, the lifecycle verb "Stop" is used because the cmdlet stops system processes.</span></span> <span data-ttu-id="9bfd5-118">Der Nomen Name "proc" wird verwendet, da das Cmdlet an Prozessen arbeitet.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-118">The noun name "Proc" is used because the cmdlet works on processes.</span></span> <span data-ttu-id="9bfd5-119">Beachten Sie in der folgenden Deklaration, dass das Cmdlet-Verb und der nominale Name in den Namen der Cmdlet-Klasse reflektiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-119">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span>

> [!NOTE]
> <span data-ttu-id="9bfd5-120">Weitere Informationen zu genehmigten Cmdlet-Verb Namen finden Sie unter [Cmdlet-Verb Namen](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="9bfd5-120">For more information about approved cmdlet verb names, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="9bfd5-121">Der folgende Code stellt die Klassendefinition für dieses Cmdlet "Pause-proc" dar.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-121">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        DefaultParameterSetName = "ProcessId",
        SupportsShouldProcess = true)]
public class StopProcCommand : PSCmdlet
```

```vb
<Cmdlet(VerbsLifecycle.Stop, "Proc", DefaultParameterSetName:="ProcessId", _
SupportsShouldProcess:=True)> _
Public Class StopProcCommand
    Inherits PSCmdlet
```

## <a name="declaring-the-parameters-of-the-cmdlet"></a><span data-ttu-id="9bfd5-122">Deklarieren der Parameter des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9bfd5-122">Declaring the Parameters of the Cmdlet</span></span>

<span data-ttu-id="9bfd5-123">Dieses Cmdlet definiert drei Parameter, die als Eingabe für das Cmdlet erforderlich sind (diese Parameter definieren auch die Parametersätze), sowie einen Parameter, der `Force` das Cmdlet verwaltet, und einen `PassThru` Parameter, der bestimmt, ob das Cmdlet ein Ausgabe Objekt über die Pipeline sendet.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-123">This cmdlet defines three parameters needed as input to the cmdlet (these parameters also define the parameter sets), as well as a `Force` parameter that manages what the cmdlet does and a `PassThru` parameter that determines whether the cmdlet sends an output object through the pipeline.</span></span> <span data-ttu-id="9bfd5-124">Standardmäßig übergibt dieses Cmdlet ein Objekt nicht über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-124">By default, this cmdlet does not pass an object through the pipeline.</span></span> <span data-ttu-id="9bfd5-125">Weitere Informationen zu diesen beiden letzten Parametern finden Sie unter [Erstellen eines Cmdlets, das das System ändert](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="9bfd5-125">For more information about these last two parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

### <a name="declaring-the-name-parameter"></a><span data-ttu-id="9bfd5-126">Deklarieren des Name-Parameters</span><span class="sxs-lookup"><span data-stu-id="9bfd5-126">Declaring the Name Parameter</span></span>

<span data-ttu-id="9bfd5-127">Dieser Eingabeparameter ermöglicht es dem Benutzer, die Namen der zu beendenden Prozesse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-127">This input parameter allows the user to specify the names of the processes to be stopped.</span></span> <span data-ttu-id="9bfd5-128">Beachten Sie, dass das `ParameterSetName` Attribut Schlüsselwort des [System. Management. Automation. Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) -Attributs den `ProcessName` Parametersatz für diesen Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-128">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessName` parameter set for this parameter.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs" range="44-58":::

```vb
<Parameter(Position:=0, ParameterSetName:="ProcessName", _
Mandatory:=True, _
ValueFromPipeline:=True, ValueFromPipelineByPropertyName:=True, _
HelpMessage:="The name of one or more processes to stop. " & _
    "Wildcards are permitted."), [Alias]("ProcessName")> _
Public Property Name() As String()
    Get
        Return processNames
    End Get
    Set(ByVal value As String())
        processNames = value
    End Set
End Property

Private processNames() As String
```

<span data-ttu-id="9bfd5-129">Beachten Sie auch, dass der Alias "ProcessName" an diesen Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-129">Note also that the alias "ProcessName" is given to this parameter.</span></span>

### <a name="declaring-the-id-parameter"></a><span data-ttu-id="9bfd5-130">Deklarieren des ID-Parameters</span><span class="sxs-lookup"><span data-stu-id="9bfd5-130">Declaring the Id Parameter</span></span>

<span data-ttu-id="9bfd5-131">Dieser Eingabeparameter ermöglicht es dem Benutzer, die Bezeichner der zu beendenden Prozesse anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-131">This input parameter allows the user to specify the identifiers of the processes to be stopped.</span></span> <span data-ttu-id="9bfd5-132">Beachten Sie, dass das `ParameterSetName` Attribut Schlüsselwort des [System. Management. Automation. Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) -Attributs den `ProcessId` Parametersatz angibt.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-132">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessId` parameter set.</span></span>

```csharp
[Parameter(
           ParameterSetName = "ProcessId",
           Mandatory = true,
           ValueFromPipelineByPropertyName = true,
           ValueFromPipeline = true
)]
[Alias("ProcessId")]
public int[] Id
{
  get { return processIds; }
  set { processIds = value; }
}
private int[] processIds;
```

```vb
<Parameter(ParameterSetName:="ProcessId", _
Mandatory:=True, _
ValueFromPipelineByPropertyName:=True, _
ValueFromPipeline:=True), [Alias]("ProcessId")> _
Public Property Id() As Integer()
    Get
        Return processIds
    End Get
    Set(ByVal value As Integer())
        processIds = value
    End Set
End Property
Private processIds() As Integer
```

<span data-ttu-id="9bfd5-133">Beachten Sie auch, dass der Alias "ProcessId" an diesen Parameter übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-133">Note also that the alias "ProcessId" is given to this parameter.</span></span>

### <a name="declaring-the-inputobject-parameter"></a><span data-ttu-id="9bfd5-134">Deklarieren des Inputobject-Parameters</span><span class="sxs-lookup"><span data-stu-id="9bfd5-134">Declaring the InputObject Parameter</span></span>

<span data-ttu-id="9bfd5-135">Dieser Eingabeparameter ermöglicht es dem Benutzer, ein Eingabe Objekt anzugeben, das Informationen über die zu beendenden Prozesse enthält.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-135">This input parameter allows the user to specify an input object that contains information about the processes to be stopped.</span></span> <span data-ttu-id="9bfd5-136">Beachten Sie, dass das `ParameterSetName` Attribut Schlüsselwort des [System. Management. Automation. Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) -Attributs den `InputObject` Parametersatz für diesen Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-136">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `InputObject` parameter set for this parameter.</span></span>

```csharp
[Parameter(
           ParameterSetName = "InputObject",
           Mandatory = true,
           ValueFromPipeline = true)]
public Process[] InputObject
{
  get { return inputObject; }
  set { inputObject = value; }
}
private Process[] inputObject;
```

```vb
<Parameter(ParameterSetName:="InputObject", _
Mandatory:=True, ValueFromPipeline:=True)> _
Public Property InputObject() As Process()
    Get
        Return myInputObject
    End Get
    Set(ByVal value As Process())
        myInputObject = value
    End Set
End Property
Private myInputObject() As Process
```

<span data-ttu-id="9bfd5-137">Beachten Sie auch, dass dieser Parameter über keinen Alias verfügt.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-137">Note also that this parameter has no alias.</span></span>

### <a name="declaring-parameters-in-multiple-parameter-sets"></a><span data-ttu-id="9bfd5-138">Deklarieren von Parametern in mehreren Parameter Sätzen</span><span class="sxs-lookup"><span data-stu-id="9bfd5-138">Declaring Parameters in Multiple Parameter Sets</span></span>

<span data-ttu-id="9bfd5-139">Obwohl für jeden Parametersatz ein eindeutiger Parameter vorhanden sein muss, können Parameter zu mehr als einem Parametersatz gehören.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-139">Although there must be a unique parameter for each parameter set, parameters can belong to more than one parameter set.</span></span> <span data-ttu-id="9bfd5-140">In diesen Fällen muss der Shared-Parameter für jeden Satz, zu dem der Parameter gehört, eine [System. Management. Automation. Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) -Attribut Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-140">In these cases, give the shared parameter a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration for each set to which that the parameter belongs.</span></span> <span data-ttu-id="9bfd5-141">Wenn ein Parameter in allen Parametersätzen enthalten ist, müssen Sie das Parameter Attribut nur einmal deklarieren und müssen nicht den Namen des Parameter Satzes angeben.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-141">If a parameter is in all parameter sets, you only have to declare the parameter attribute once and do not need to specify the parameter set name.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="9bfd5-142">Überschreiben einer Eingabe Verarbeitungsmethode</span><span class="sxs-lookup"><span data-stu-id="9bfd5-142">Overriding an Input Processing Method</span></span>

<span data-ttu-id="9bfd5-143">Jedes Cmdlet muss eine Eingabe Verarbeitungsmethode überschreiben, meistens handelt es sich hierbei um die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-143">Every cmdlet must override an input processing method, most often this will be the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="9bfd5-144">In diesem Cmdlet wird die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode überschrieben, sodass das Cmdlet eine beliebige Anzahl von Prozessen verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-144">In this cmdlet, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden so that the cmdlet can process any number of processes.</span></span> <span data-ttu-id="9bfd5-145">Sie enthält eine SELECT-Anweisung, die eine andere Methode aufruft, je nachdem, welchen Parametersatz der Benutzer angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-145">It contains a Select statement that calls a different method based on which parameter set the user has specified.</span></span>

```csharp
protected override void ProcessRecord()
{
  switch (ParameterSetName)
  {
    case "ProcessName":
         ProcessByName();
         break;

    case "ProcessId":
         ProcessById();
         break;

    case "InputObject":
         foreach (Process process in inputObject)
         {
           SafeStopProcess(process);
         }
         break;

    default:
         throw new ArgumentException("Bad ParameterSet Name");
  } // switch (ParameterSetName...
} // ProcessRecord
```

```vb
Protected Overrides Sub ProcessRecord()
    Select Case ParameterSetName
        Case "ProcessName"
            ProcessByName()

        Case "ProcessId"
            ProcessById()

        Case "InputObject"
            Dim process As Process
            For Each process In myInputObject
                SafeStopProcess(process)
            Next process

        Case Else
            Throw New ArgumentException("Bad ParameterSet Name")
    End Select

End Sub 'ProcessRecord ' ProcessRecord
```

<span data-ttu-id="9bfd5-146">Die Hilfsmethoden, die von der SELECT-Anweisung aufgerufen werden, werden hier nicht beschrieben, aber Sie können Ihre Implementierung im gesamten Codebeispiel im nächsten Abschnitt sehen.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-146">The Helper methods called by the Select statement are not described here, but you can see their implementation in the complete code sample in the next section.</span></span>

## <a name="code-sample"></a><span data-ttu-id="9bfd5-147">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="9bfd5-147">Code Sample</span></span>

<span data-ttu-id="9bfd5-148">Den gesamten c#-Beispielcode finden Sie unter [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9bfd5-148">For the complete C# sample code, see [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="9bfd5-149">Definieren von Objekttypen und Formatierung</span><span class="sxs-lookup"><span data-stu-id="9bfd5-149">Defining Object Types and Formatting</span></span>

<span data-ttu-id="9bfd5-150">Windows PowerShell übergibt Informationen zwischen Cmdlets mithilfe von .NET-Objekten.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-150">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="9bfd5-151">Folglich muss ein Cmdlet möglicherweise seinen eigenen Typ definieren, oder das Cmdlet muss möglicherweise einen vorhandenen Typ erweitern, der von einem anderen Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-151">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="9bfd5-152">Weitere Informationen zum Definieren neuer Typen oder zum Erweitern vorhandener Typen finden Sie unter [Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9bfd5-152">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="9bfd5-153">Cmdlet wird aufgebaut</span><span class="sxs-lookup"><span data-stu-id="9bfd5-153">Building the Cmdlet</span></span>

<span data-ttu-id="9bfd5-154">Nachdem Sie ein Cmdlet implementiert haben, müssen Sie es über ein Windows PowerShell-Snap-in bei Windows PowerShell registrieren.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-154">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="9bfd5-155">Weitere Informationen zum Registrieren von Cmdlets finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9bfd5-155">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="9bfd5-156">Testen des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9bfd5-156">Testing the Cmdlet</span></span>

<span data-ttu-id="9bfd5-157">Wenn das Cmdlet bei Windows PowerShell registriert wurde, testen Sie es, indem Sie es in der Befehlszeile ausführen.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-157">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="9bfd5-158">Im folgenden finden Sie einige Tests, die zeigen, wie die Parameter `ProcessId` und `InputObject` verwendet werden können, um Ihre Parametersätze zu testen, um einen Prozess zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-158">Here are some tests that show how the `ProcessId` and `InputObject` parameters can be used to test their parameter sets to stop a process.</span></span>

- <span data-ttu-id="9bfd5-159">Führen Sie bei der Ausführung von Windows PowerShell das Cmdlet "Break-proc" mit dem `ProcessId` festgelegten Parameter aus, um einen Prozess auf der Grundlage des Bezeichners anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-159">With Windows PowerShell started, run the Stop-Proc cmdlet with the `ProcessId` parameter set to stop a process based on its identifier.</span></span> <span data-ttu-id="9bfd5-160">In diesem Fall verwendet das Cmdlet den `ProcessId` Parametersatz, um den Prozess zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="9bfd5-160">In this case, the cmdlet is using the `ProcessId` parameter set to stop the process.</span></span>

  ```
  PS> stop-proc -Id 444
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
  ```

- <span data-ttu-id="9bfd5-161">Führen Sie in Windows PowerShell das Cmdlet "Break-proc" mit dem `InputObject` Parameter Set aus, um die Prozesse für das vom Befehl abgerufene Notepad-Objekt zu verhindern `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="9bfd5-161">With Windows PowerShell started, run the Stop-Proc cmdlet with the `InputObject` parameter set to stop processes on the Notepad object retrieved by the `Get-Process` command.</span></span>

  ```
  PS> get-process notepad | stop-proc
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
  ```

## <a name="see-also"></a><span data-ttu-id="9bfd5-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9bfd5-162">See Also</span></span>

[<span data-ttu-id="9bfd5-163">Erstellen eines Cmdlet, das das System ändert</span><span class="sxs-lookup"><span data-stu-id="9bfd5-163">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="9bfd5-164">Erstellen eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9bfd5-164">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="9bfd5-165">[Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9bfd5-165">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="9bfd5-166">[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9bfd5-166">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="9bfd5-167">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="9bfd5-167">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
