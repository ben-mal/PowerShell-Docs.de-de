---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen eines Cmdlet ohne Parameter
description: Erstellen eines Cmdlet ohne Parameter
ms.openlocfilehash: 5df27ac4c1f6dfcc3e7596d93f8db0f97aae71c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646552"
---
# <a name="creating-a-cmdlet-without-parameters"></a><span data-ttu-id="0b9a4-103">Erstellen eines Cmdlet ohne Parameter</span><span class="sxs-lookup"><span data-stu-id="0b9a4-103">Creating a Cmdlet without Parameters</span></span>

<span data-ttu-id="0b9a4-104">In diesem Abschnitt wird beschrieben, wie Sie ein Cmdlet erstellen, das Informationen vom lokalen Computer abruft, ohne Parameter zu verwenden, und dann die Informationen in die Pipeline schreibt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-104">This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span> <span data-ttu-id="0b9a4-105">Das hier beschriebene Cmdlet ist ein Get-Proc Cmdlet, das Informationen zu den Prozessen des lokalen Computers abruft und diese Informationen dann in der Befehlszeile anzeigt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-105">The cmdlet described here is a Get-Proc cmdlet that retrieves information about the processes of the local computer, and then displays that information at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="0b9a4-106">Beachten Sie, dass beim Schreiben von Cmdlets die Windows PowerShell-® Verweisassemblys auf den Datenträger heruntergeladen werden (standardmäßig unter "c:\Programme\Reference assemblies\microsoft\windowspowershell\v1.0").</span><span class="sxs-lookup"><span data-stu-id="0b9a4-106">Be aware that when writing cmdlets, the Windows PowerShell® reference assemblies are downloaded onto disk (by default at C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).</span></span> <span data-ttu-id="0b9a4-107">Sie sind nicht im globalen Assemblycache (GAC) installiert.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-107">They are not installed in the Global Assembly Cache (GAC).</span></span>

## <a name="naming-the-cmdlet"></a><span data-ttu-id="0b9a4-108">Benennen des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0b9a4-108">Naming the Cmdlet</span></span>

<span data-ttu-id="0b9a4-109">Ein Cmdlet-Name besteht aus einem Verb, das die Aktion angibt, die das Cmdlet annimmt, und einem Substantiv, das die Elemente angibt, auf die das Cmdlet angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-109">A cmdlet name consists of a verb that indicates the action the cmdlet takes and a noun that indicates the items that the cmdlet acts upon.</span></span> <span data-ttu-id="0b9a4-110">Da dieses Beispiel Get-Proc Cmdlet Prozess Objekte abruft, verwendet es das Verb "Get", das von der [System. Management. Automation. verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) -Enumeration definiert wird, und das Substantiv "proc", um anzugeben, dass das Cmdlet für Prozesselemente funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-110">Because this sample Get-Proc cmdlet retrieves process objects, it uses the verb "Get", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) enumeration, and the noun "Proc" to indicate that the cmdlet works on process items.</span></span>

<span data-ttu-id="0b9a4-111">Verwenden Sie beim Benennen von Cmdlets keines der folgenden Zeichen: #, () {} [] &-/\ $;: "' <> &#124; ?</span><span class="sxs-lookup"><span data-stu-id="0b9a4-111">When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ?</span></span> <span data-ttu-id="0b9a4-112">@ \` .</span><span class="sxs-lookup"><span data-stu-id="0b9a4-112">@ \` .</span></span>

### <a name="choosing-a-noun"></a><span data-ttu-id="0b9a4-113">Auswählen eines Substantivs</span><span class="sxs-lookup"><span data-stu-id="0b9a4-113">Choosing a Noun</span></span>

<span data-ttu-id="0b9a4-114">Sie sollten ein bestimmtes Substantiv auswählen.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-114">You should choose a noun that is specific.</span></span> <span data-ttu-id="0b9a4-115">Es empfiehlt sich, ein Singular-Substantiv zu verwenden, das mit einer verkürzten Version des Produkt namens versehen ist.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-115">It is best to use a singular noun prefixed with a shortened version of the product name.</span></span> <span data-ttu-id="0b9a4-116">Ein Beispiel für einen Cmdlet-Namen dieses Typs ist " `Get-SQLServer` ".</span><span class="sxs-lookup"><span data-stu-id="0b9a4-116">An example cmdlet name of this type is "`Get-SQLServer`".</span></span>

### <a name="choosing-a-verb"></a><span data-ttu-id="0b9a4-117">Auswählen eines Verbs</span><span class="sxs-lookup"><span data-stu-id="0b9a4-117">Choosing a Verb</span></span>

<span data-ttu-id="0b9a4-118">Sie sollten ein Verb aus dem Satz genehmigter Cmdlet-Verb Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-118">You should use a verb from the set of approved cmdlet verb names.</span></span> <span data-ttu-id="0b9a4-119">Weitere Informationen zu den genehmigten Cmdlet-Verben finden Sie unter [Cmdlet-Verb Namen](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-119">For more information about the approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="0b9a4-120">Definieren der Cmdlet-Klasse</span><span class="sxs-lookup"><span data-stu-id="0b9a4-120">Defining the Cmdlet Class</span></span>

<span data-ttu-id="0b9a4-121">Nachdem Sie einen Cmdlet-Namen ausgewählt haben, definieren Sie eine .NET-Klasse, um das Cmdlet zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-121">Once you have chosen a cmdlet name, define a .NET class to implement the cmdlet.</span></span> <span data-ttu-id="0b9a4-122">Im folgenden finden Sie die Klassendefinition für dieses Beispiel Get-Proc Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0b9a4-122">Here is the class definition for this sample Get-Proc cmdlet:</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

<span data-ttu-id="0b9a4-123">Beachten Sie, dass das [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) -Attribut mit der-Syntax vor der Klassendefinition `[Cmdlet(verb, noun, ...)]` verwendet wird, um diese Klasse als Cmdlet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-123">Notice that previous to the class definition, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute, with the syntax `[Cmdlet(verb, noun, ...)]`, is used to identify this class as a cmdlet.</span></span> <span data-ttu-id="0b9a4-124">Dies ist das einzige erforderliche Attribut für alle Cmdlets und ermöglicht es der Windows PowerShell-Laufzeit, Sie ordnungsgemäß aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-124">This is the only required attribute for all cmdlets, and it allows the Windows PowerShell runtime to call them correctly.</span></span> <span data-ttu-id="0b9a4-125">Sie können Attribut Schlüsselwörter festlegen, um die Klasse bei Bedarf weiter zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-125">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="0b9a4-126">Beachten Sie, dass die Attribut Deklaration für die getproccommand-Beispiel Klasse nur die Substantiv-und Verb Namen für das Get-Proc-Cmdlet deklariert.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-126">Be aware that the attribute declaration for our sample GetProcCommand class declares only the noun and verb names for the Get-Proc cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="0b9a4-127">Für alle Windows PowerShell-Attribut Klassen entsprechen die Schlüsselwörter, die Sie festlegen können, den Eigenschaften der Attribut Klasse.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-127">For all Windows PowerShell attribute classes, the keywords that you can set correspond to properties of the attribute class.</span></span>

<span data-ttu-id="0b9a4-128">Wenn Sie die Klasse des Cmdlets benennen, empfiehlt es sich, den Cmdlet-Namen im Klassennamen widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-128">When naming the class of the cmdlet, it is a good practice to reflect the cmdlet name in the class name.</span></span> <span data-ttu-id="0b9a4-129">Verwenden Sie hierzu das Format "verbnouncommand", und ersetzen Sie "Verb" und "Substantiv" durch das Verb und das Substantiv, das im Cmdlet-Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-129">To do this, use the form "VerbNounCommand" and replace "Verb" and "Noun" with the verb and noun used in the cmdlet name.</span></span> <span data-ttu-id="0b9a4-130">Wie in der vorherigen Klassendefinition gezeigt, definiert das Cmdlet "Sample Get-Proc" eine Klasse mit dem Namen "getproccommand", die von der Basisklasse " [System. Management. Automation. Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) " abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-130">As is shown in the previous class definition, the sample Get-Proc cmdlet defines a class called GetProcCommand, which derives from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) base class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b9a4-131">Wenn Sie ein Cmdlet definieren möchten, das direkt auf die Windows PowerShell-Laufzeit zugreift, sollte Ihre .NET-Klasse von der Basisklasse " [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) " abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-131">If you want to define a cmdlet that accesses the Windows PowerShell runtime directly, your .NET class should derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span> <span data-ttu-id="0b9a4-132">Weitere Informationen zu dieser Klasse finden Sie unter [Erstellen eines Cmdlets zum Definieren von Parameter Sätzen](./adding-parameter-sets-to-a-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-132">For more information about this class, see [Creating a Cmdlet that Defines Parameter Sets](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0b9a4-133">Die-Klasse für ein Cmdlet muss explizit als public gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-133">The class for a cmdlet must be explicitly marked as public.</span></span> <span data-ttu-id="0b9a4-134">Klassen, die nicht als public gekennzeichnet sind, werden standardmäßig intern verwendet und werden von der Windows PowerShell-Laufzeit nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-134">Classes that are not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="0b9a4-135">Windows PowerShell verwendet den [Microsoft. PowerShell. Commands](/dotnet/api/Microsoft.PowerShell.Commands) -Namespace für die Cmdlet-Klassen.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-135">Windows PowerShell uses the [Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) namespace for its cmdlet classes.</span></span> <span data-ttu-id="0b9a4-136">Es wird empfohlen, die Cmdlet-Klassen in einem Befehle-Namespace ihres API-Namespace zu platzieren, z. b. xxx. PS. Commands.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-136">It is recommended to place your cmdlet classes in a Commands namespace of your API namespace, for example, xxx.PS.Commands.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="0b9a4-137">Überschreiben einer Eingabe Verarbeitungsmethode</span><span class="sxs-lookup"><span data-stu-id="0b9a4-137">Overriding an Input Processing Method</span></span>

<span data-ttu-id="0b9a4-138">Die [System. Management. Automation. Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) -Klasse stellt drei Haupt Eingabe-Verarbeitungsmethoden bereit, von denen das Cmdlet überschrieben werden muss.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-138">The [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class provides three main input processing methods, at least one of which your cmdlet must override.</span></span> <span data-ttu-id="0b9a4-139">Weitere Informationen zur Verarbeitung von Datensätzen in Windows PowerShell finden Sie unter [Funktionsweise von Windows PowerShell](/previous-versions//ms714658(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-139">For more information about how Windows PowerShell processes records, see [How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85)).</span></span>

<span data-ttu-id="0b9a4-140">Für alle Typen von Eingaben Ruft die Windows PowerShell-Runtime [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) auf, um die Verarbeitung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-140">For all types of input, the Windows PowerShell runtime calls [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) to enable processing.</span></span> <span data-ttu-id="0b9a4-141">Wenn das Cmdlet einige Vorverarbeitungs-oder Setup Vorgänge ausführen muss, kann dies durch Überschreiben dieser Methode durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-141">If your cmdlet must perform some preprocessing or setup, it can do this by overriding this method.</span></span>

> [!NOTE]
> <span data-ttu-id="0b9a4-142">Windows PowerShell verwendet den Begriff "Datensatz", um den Satz von Parameterwerten zu beschreiben, die beim Aufrufen eines Cmdlets bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-142">Windows PowerShell uses the term "record" to describe the set of parameter values supplied when a cmdlet is called.</span></span>

<span data-ttu-id="0b9a4-143">Wenn das Cmdlet Pipeline Eingaben annimmt, muss es die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode und optional die [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) -Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-143">If your cmdlet accepts pipeline input, it must override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, and optionally the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="0b9a4-144">Beispielsweise kann ein Cmdlet beide Methoden überschreiben, wenn es die gesamte Eingabe mithilfe von [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) sammelt und dann die Eingabe als Ganzes anstelle eines Elements, wie das `Sort-Object` Cmdlet, bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-144">For example, a cmdlet might override both methods if it gathers all input using [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) and then operates on the input as a whole rather than one element at a time, as the `Sort-Object` cmdlet does.</span></span>

<span data-ttu-id="0b9a4-145">Wenn das Cmdlet keine Pipeline Eingaben annimmt, sollte es die [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) -Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-145">If your cmdlet does not take pipeline input, it should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="0b9a4-146">Beachten Sie, dass diese Methode häufig anstelle von [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) verwendet wird, wenn das Cmdlet nicht gleichzeitig auf einem Element agieren kann, wie es bei einem Sortierungs-Cmdlet der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-146">Be aware that this method is frequently used in place of [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) when the cmdlet cannot operate on one element at a time, as is the case for a sorting cmdlet.</span></span>

<span data-ttu-id="0b9a4-147">Da dieses Beispiel Get-Proc Cmdlet Pipeline Eingaben empfangen muss, überschreibt es die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode und verwendet die Standard Implementierungen für [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) und [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-147">Because this sample Get-Proc cmdlet must receive pipeline input, it overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method and uses the default implementations for [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) and [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span></span> <span data-ttu-id="0b9a4-148">Die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Überschreibung ruft Prozesse ab und schreibt Sie mithilfe der [System. Management. Automation. Cmdlet. Write-Object](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) -Methode in die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-148">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override retrieves processes and writes them to the command line using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Get the current processes
  Process[] processes = Process.GetProcesses();

  // Write the processes to the pipeline making them available
  // to the next cmdlet. The second parameter of this call tells
  // PowerShell to enumerate the array, and send one process at a
  // time to the pipeline.
  WriteObject(processes, true);
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ Get the current processes.
    Dim processes As Process()
    processes = Process.GetProcesses()

    '/ Write the processes to the pipeline making them available
    '/ to the next cmdlet. The second parameter of this call tells
    '/ PowerShell to enumerate the array, and send one process at a
    '/ time to the pipeline.
    WriteObject(processes, True)

End Sub 'ProcessRecord
```

#### <a name="things-to-remember-about-input-processing"></a><span data-ttu-id="0b9a4-149">Dinge, die bei der Eingabe Verarbeitung beachtet werden sollten</span><span class="sxs-lookup"><span data-stu-id="0b9a4-149">Things to Remember About Input Processing</span></span>

- <span data-ttu-id="0b9a4-150">Die Standard Quelle für die Eingabe ist ein explizites Objekt (z. b. eine Zeichenfolge), das vom Benutzer in der Befehlszeile bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-150">The default source for input is an explicit object (for example, a string) provided by the user on the command line.</span></span> <span data-ttu-id="0b9a4-151">Weitere Informationen finden Sie unter [Erstellen eines Cmdlets zum Verarbeiten von Befehlszeilen Eingaben](./adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-151">For more information, see [Creating a Cmdlet to Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

- <span data-ttu-id="0b9a4-152">Eine Eingabe Verarbeitungsmethode kann auch Eingaben vom Ausgabe Objekt eines upstreamcmdlets in der Pipeline empfangen.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-152">An input processing method can also receive input from the output object of an upstream cmdlet on the pipeline.</span></span> <span data-ttu-id="0b9a4-153">Weitere Informationen finden Sie unter [Erstellen eines Cmdlets für die Verarbeitung von Pipeline Eingaben](./adding-parameters-that-process-pipeline-input.md).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-153">For more information, see [Creating a Cmdlet to Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="0b9a4-154">Beachten Sie, dass das Cmdlet Eingaben von einer Kombination von Befehlszeilen-und Pipeline Quellen empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-154">Be aware that your cmdlet can receive input from a combination of command-line and pipeline sources.</span></span>

- <span data-ttu-id="0b9a4-155">Das downstreamcmdlet gibt möglicherweise für längere Zeit oder gar nicht zurück.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-155">The downstream cmdlet might not return for a long time, or not at all.</span></span> <span data-ttu-id="0b9a4-156">Aus diesem Grund sollte die Eingabe Verarbeitungsmethode in Ihrem Cmdlet keine Sperren bei Aufrufen von [System. Management. Automation. Cmdlet. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)enthalten, insbesondere sperren, für die der Bereich die Cmdlet-Instanz überschreitet.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-156">For that reason, the input processing method in your cmdlet should not hold locks during calls to [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especially locks for which the scope extends beyond the cmdlet instance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b9a4-157">Cmdlets sollten niemals [System. Console. Write teline \*](/dotnet/api/System.Console.WriteLine) oder die entsprechende-Entsprechung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-157">Cmdlets should never call [System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine) or its equivalent.</span></span>

- <span data-ttu-id="0b9a4-158">Wenn die Verarbeitung abgeschlossen ist, kann das Cmdlet Objektvariablen zum Bereinigen aufweisen (z. b., wenn ein Datei Handle in der [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) -Methode geöffnet wird und das Handle für die Verwendung durch [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)geöffnet bleibt).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-158">Your cmdlet might have object variables to clean up when it is finished processing (for example, if it opens a file handle in the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span></span> <span data-ttu-id="0b9a4-159">Beachten Sie, dass die Windows PowerShell-Laufzeit nicht immer die [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) -Methode aufruft, die die Objekt Bereinigung durchführen soll.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-159">It is important to remember that the Windows PowerShell runtime does not always call the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method, which should perform object cleanup.</span></span>

<span data-ttu-id="0b9a4-160">Beispielsweise kann " [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) " nicht aufgerufen werden, wenn das Cmdlet in der Mitte abgebrochen wird oder wenn in einem beliebigen Teil des Cmdlets ein Abbruch Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-160">For example, [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) might not be called if the cmdlet is canceled midway or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="0b9a4-161">Daher sollte ein Cmdlet, das die Objekt Bereinigung erfordert, das komplette [System. iverwerf-](/dotnet/api/System.IDisposable) Muster implementieren, einschließlich des Finalizers, damit die Laufzeit sowohl [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) als auch [System. iverwerf. verwerfen \*](/dotnet/api/System.IDisposable.Dispose) am Ende der Verarbeitung abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-161">Therefore, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including the finalizer, so that the runtime can call both [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) at the end of processing.</span></span>

## <a name="code-sample"></a><span data-ttu-id="0b9a4-162">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="0b9a4-162">Code Sample</span></span>

<span data-ttu-id="0b9a4-163">Den gesamten c#-Beispielcode finden Sie unter [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-163">For the complete C# sample code, see [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="0b9a4-164">Definieren von Objekttypen und Formatierung</span><span class="sxs-lookup"><span data-stu-id="0b9a4-164">Defining Object Types and Formatting</span></span>

<span data-ttu-id="0b9a4-165">Windows PowerShell übergibt Informationen zwischen Cmdlets mithilfe von .NET-Objekten.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-165">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="0b9a4-166">Folglich muss ein Cmdlet möglicherweise seinen eigenen Typ definieren, oder das Cmdlet muss möglicherweise einen vorhandenen Typ erweitern, der von einem anderen Cmdlet bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-166">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="0b9a4-167">Weitere Informationen zum Definieren neuer Typen oder zum Erweitern vorhandener Typen finden Sie unter [Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-167">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="0b9a4-168">Cmdlet wird aufgebaut</span><span class="sxs-lookup"><span data-stu-id="0b9a4-168">Building the Cmdlet</span></span>

<span data-ttu-id="0b9a4-169">Nachdem Sie ein Cmdlet implementiert haben, müssen Sie es über ein Windows PowerShell-Snap-in bei Windows PowerShell registrieren.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-169">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="0b9a4-170">Weitere Informationen zum Registrieren von Cmdlets finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-170">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="0b9a4-171">Testen des Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0b9a4-171">Testing the Cmdlet</span></span>

<span data-ttu-id="0b9a4-172">Wenn das Cmdlet bei Windows PowerShell registriert wurde, können Sie es in der Befehlszeile testen.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-172">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="0b9a4-173">Der Code für das Cmdlet "Sample Get-Proc" ist klein, aber es werden immer noch die Windows PowerShell-Laufzeit und ein vorhandenes .NET-Objekt verwendet, das ausreichend ist, um es zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-173">The code for our sample Get-Proc cmdlet is small, but it still uses the Windows PowerShell runtime and an existing .NET object, which is enough to make it useful.</span></span> <span data-ttu-id="0b9a4-174">Testen Sie es, um besser zu verstehen, was Get-Proc können und wie seine Ausgabe verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-174">Let's test it to better understand what Get-Proc can do and how its output can be used.</span></span> <span data-ttu-id="0b9a4-175">Weitere Informationen zur Verwendung von Cmdlets über die Befehlszeile finden Sie unter [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0b9a4-175">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

1. <span data-ttu-id="0b9a4-176">Starten Sie Windows PowerShell, und holen Sie sich die aktuellen Prozesse, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-176">Start Windows PowerShell, and get the current processes running on the computer.</span></span>

    ```powershell
    get-proc
    ```

    <span data-ttu-id="0b9a4-177">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-177">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. <span data-ttu-id="0b9a4-178">Weisen Sie den Cmdlet-Ergebnissen eine Variable zu, um die Bearbeitung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-178">Assign a variable to the cmdlet results for easier manipulation.</span></span>

    ```powershell
    $p=get-proc
    ```

3. <span data-ttu-id="0b9a4-179">Gibt die Anzahl der Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-179">Get the number of processes.</span></span>

    ```powershell
    $p.length
    ```

    <span data-ttu-id="0b9a4-180">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-180">The following output appears.</span></span>

    ```output
    63
    ```

4. <span data-ttu-id="0b9a4-181">Ruft einen bestimmten Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-181">Retrieve a specific process.</span></span>

    ```powershell
    $p[6]
    ```

    <span data-ttu-id="0b9a4-182">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-182">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. <span data-ttu-id="0b9a4-183">Hiermit wird die Startzeit dieses Prozesses angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-183">Get the start time of this process.</span></span>

    ```powershell
    $p[6].starttime
    ```

    <span data-ttu-id="0b9a4-184">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-184">The following output appears.</span></span>

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. <span data-ttu-id="0b9a4-185">Holen Sie die Prozesse, für die die Anzahl der Handles größer als 500 ist, und sortieren Sie das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-185">Get the processes for which the handle count is greater than 500, and sort the result.</span></span>

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    <span data-ttu-id="0b9a4-186">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-186">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. <span data-ttu-id="0b9a4-187">Verwenden `Get-Member` Sie das Cmdlet, um die für die einzelnen Prozesse verfügbaren Eigenschaften aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-187">Use the `Get-Member` cmdlet to list the properties available for each process.</span></span>

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    <span data-ttu-id="0b9a4-188">Die folgende Ausgabe wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b9a4-188">The following output appears.</span></span>

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a><span data-ttu-id="0b9a4-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b9a4-189">See Also</span></span>

[<span data-ttu-id="0b9a4-190">Erstellen eines Cmdlets zur Verarbeitung der Befehlszeilen Eingabe</span><span class="sxs-lookup"><span data-stu-id="0b9a4-190">Creating a Cmdlet to Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="0b9a4-191">Erstellen eines Cmdlets zum Verarbeiten von Pipeline Eingaben</span><span class="sxs-lookup"><span data-stu-id="0b9a4-191">Creating a Cmdlet to Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="0b9a4-192">Erstellen eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0b9a4-192">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="0b9a4-193">[Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="0b9a4-193">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="0b9a4-194">[Funktionsweise von Windows PowerShell](/previous-versions//ms714658(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="0b9a4-194">[How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85))</span></span>

<span data-ttu-id="0b9a4-195">[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="0b9a4-195">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="0b9a4-196">Windows PowerShell-Referenz</span><span class="sxs-lookup"><span data-stu-id="0b9a4-196">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="0b9a4-197">Cmdlet-Beispiele</span><span class="sxs-lookup"><span data-stu-id="0b9a4-197">Cmdlet Samples</span></span>](./cmdlet-samples.md)
