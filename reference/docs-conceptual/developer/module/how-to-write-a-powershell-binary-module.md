---
ms.date: 09/13/2016
ms.topic: reference
title: Schreiben eines PowerShell-Binärmoduls
description: Schreiben eines PowerShell-Binärmoduls
ms.openlocfilehash: 1d5cea474ac418f78cc782360b7c23b7614d6669
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663060"
---
# <a name="how-to-write-a-powershell-binary-module"></a><span data-ttu-id="756ff-103">Schreiben eines PowerShell-Binärmoduls</span><span class="sxs-lookup"><span data-stu-id="756ff-103">How to Write a PowerShell Binary Module</span></span>

<span data-ttu-id="756ff-104">Ein binäres Modul kann eine beliebige Assembly (DLL-Datei) sein, die Cmdlet-Klassen enthält.</span><span class="sxs-lookup"><span data-stu-id="756ff-104">A binary module can be any assembly (.dll) that contains cmdlet classes.</span></span> <span data-ttu-id="756ff-105">Standardmäßig werden alle Cmdlets in der Assembly importiert, wenn das binäre Modul importiert wird.</span><span class="sxs-lookup"><span data-stu-id="756ff-105">By default, all the cmdlets in the assembly are imported when the binary module is imported.</span></span> <span data-ttu-id="756ff-106">Sie können jedoch die importierten Cmdlets einschränken, indem Sie ein Modul Manifest erstellen, dessen Stamm Modul die Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="756ff-106">However, you can restrict the cmdlets that are imported by creating a module manifest whose root module is the assembly.</span></span> <span data-ttu-id="756ff-107">(Beispielsweise kann der cmdletstoexport-Schlüssel des Manifests verwendet werden, um nur die benötigten Cmdlets zu exportieren.) Außerdem kann ein binäres Modul weitere Dateien, eine Verzeichnisstruktur und andere nützliche Verwaltungsinformationen enthalten, die ein einzelnes Cmdlet nicht.</span><span class="sxs-lookup"><span data-stu-id="756ff-107">(For example, the CmdletsToExport key of the manifest can be used to export only those cmdlets that are needed.) In addition, a binary module can contain additional files, a directory structure, and other pieces of useful management information that a single cmdlet cannot.</span></span>

<span data-ttu-id="756ff-108">Im folgenden Verfahren wird beschrieben, wie ein PowerShell-Binär Modul erstellt und installiert wird.</span><span class="sxs-lookup"><span data-stu-id="756ff-108">The following procedure describes how to create and install a PowerShell binary module.</span></span>

#### <a name="how-to-create-and-install-a-powershell-binary-module"></a><span data-ttu-id="756ff-109">Erstellen und Installieren eines binären PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="756ff-109">How to create and install a PowerShell binary module</span></span>

1. <span data-ttu-id="756ff-110">Erstellen Sie eine binäre PowerShell-Projekt Mappe (z. b. ein in c# geschriebenes Cmdlet) mit den benötigten Funktionen, und stellen Sie sicher, dass Sie ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="756ff-110">Create a binary PowerShell solution (such as a cmdlet written in C#), with the capabilities you need, and ensure that it runs properly.</span></span>

   <span data-ttu-id="756ff-111">Aus Sicht des Codes ist das Kernstück eines binären Moduls einfach eine Cmdlet-Assembly.</span><span class="sxs-lookup"><span data-stu-id="756ff-111">From a code perspective, the core of a binary module is simply a cmdlet assembly.</span></span> <span data-ttu-id="756ff-112">Tatsächlich behandelt PowerShell eine einzelne Cmdlet-Assembly als Modul im Hinblick auf das Laden und entladen, ohne zusätzlichen Aufwand für den Entwickler.</span><span class="sxs-lookup"><span data-stu-id="756ff-112">In fact, PowerShell will treat a single cmdlet assembly as a module, in terms of loading and unloading, with no additional effort on the part of the developer.</span></span> <span data-ttu-id="756ff-113">Weitere Informationen zum Schreiben eines Cmdlets finden Sie unter [Schreiben eines Windows PowerShell-Cmdlets](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="756ff-113">For more information about writing a cmdlet, see [Writing a Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md).</span></span>

2. <span data-ttu-id="756ff-114">Erstellen Sie ggf. den Rest der Lösung: (zusätzliche Cmdlets, XML-Dateien usw.), und beschreiben Sie Sie mit einem Modul Manifest.</span><span class="sxs-lookup"><span data-stu-id="756ff-114">If necessary, create the rest of your solution: (additional cmdlets, XML files, and so on) and describe them with a module manifest.</span></span>

   <span data-ttu-id="756ff-115">Neben der Beschreibung der Cmdlet-Assemblys in der Projekt Mappe kann ein Modul Manifest beschreiben, wie das Modul exportiert und importiert werden soll, welche Cmdlets verfügbar gemacht werden und welche zusätzlichen Dateien in das Modul gelangen.</span><span class="sxs-lookup"><span data-stu-id="756ff-115">In addition to describing the cmdlet assemblies in your solution, a module manifest can describe how you want your module exported and imported, what cmdlets will be exposed, and what additional files will go into the module.</span></span>
   <span data-ttu-id="756ff-116">Wie bereits erwähnt, kann PowerShell ein binäres Cmdlet wie ein Modul ohne zusätzlichen Aufwand behandeln.</span><span class="sxs-lookup"><span data-stu-id="756ff-116">As stated previously however, PowerShell can treat a binary cmdlet like a module with no additional effort.</span></span>
   <span data-ttu-id="756ff-117">Daher ist ein Modul Manifest besonders nützlich für das Kombinieren mehrerer Dateien in einem einzelnen Paket oder das explizite Steuern der Veröffentlichung für eine bestimmte Assembly.</span><span class="sxs-lookup"><span data-stu-id="756ff-117">As such, a module manifest is useful mainly for combining multiple files into a single package, or for explicitly controlling publication for a given assembly.</span></span>
   <span data-ttu-id="756ff-118">Weitere Informationen finden Sie unter Gewusst [wie: Schreiben eines PowerShell-Modul Manifests](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="756ff-118">For more information, see [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

   <span data-ttu-id="756ff-119">Der folgende Code ist ein äußerst einfacher c#-Codeblock, der drei Cmdlets in der gleichen Datei enthält, die als Modul verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="756ff-119">The following code is an extremely simple C# code block that contains three cmdlets in the same file that can be used as a module.</span></span>

   ```csharp
   using System.Management.Automation;           // Windows PowerShell namespace.

   namespace ModuleCmdlets
   {
     [Cmdlet(VerbsDiagnostic.Test,"BinaryModuleCmdlet1")]
     public class TestBinaryModuleCmdlet1Command : Cmdlet
     {
       protected override void BeginProcessing()
       {
         WriteObject("BinaryModuleCmdlet1 exported by the ModuleCmdlets module.");
       }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet2")]
     public class TestBinaryModuleCmdlet2Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet2 exported by the ModuleCmdlets module.");
         }
     }

     [Cmdlet(VerbsDiagnostic.Test, "BinaryModuleCmdlet3")]
     public class TestBinaryModuleCmdlet3Command : Cmdlet
     {
         protected override void BeginProcessing()
         {
             WriteObject("BinaryModuleCmdlet3 exported by the ModuleCmdlets module.");
         }
     }

   }
   ```

3. <span data-ttu-id="756ff-120">Packen Sie die Projekt Mappe, und speichern Sie das Paket an einer beliebigen Stelle im PowerShell-Modulpfad.</span><span class="sxs-lookup"><span data-stu-id="756ff-120">Package your solution, and save the package to somewhere in the PowerShell module path.</span></span>

   <span data-ttu-id="756ff-121">Die `PSModulePath` globale Umgebungsvariable beschreibt die Standard Pfade, die von PowerShell verwendet werden, um das Modul zu suchen.</span><span class="sxs-lookup"><span data-stu-id="756ff-121">The `PSModulePath` global environment variable describes the default paths that PowerShell will use to locate your module.</span></span> <span data-ttu-id="756ff-122">Beispielsweise wäre ein allgemeiner Pfad zum Speichern eines Moduls auf einem System `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>` .</span><span class="sxs-lookup"><span data-stu-id="756ff-122">For example, a common path to save a module on a system would be `%SystemRoot%\users\<user>\Documents\WindowsPowerShell\Modules\<moduleName>`.</span></span> <span data-ttu-id="756ff-123">Wenn Sie nicht die Standard Pfade verwenden, müssen Sie den Speicherort des Moduls während der Installation explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="756ff-123">If you do not use the default paths, you will need to explicitly state the location of your module during installation.</span></span> <span data-ttu-id="756ff-124">Stellen Sie sicher, dass Sie einen Ordner erstellen, in dem das Modul gespeichert werden kann, da Sie möglicherweise den Ordner zum Speichern mehrerer Assemblys und Dateien für die Projekt Mappe benötigen.</span><span class="sxs-lookup"><span data-stu-id="756ff-124">Be sure to create a folder to save your module in, as you may need the folder to store multiple assemblies and files for your solution.</span></span>

   <span data-ttu-id="756ff-125">Beachten Sie, dass Sie das Modul nicht an einer beliebigen Stelle im installieren müssen `PSModulePath` . diese sind einfach die Standard Speicherorte, die von PowerShell nach Ihrem Modul gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="756ff-125">Note that technically you do not need to install your module anywhere on the `PSModulePath` - those are simply the default locations that PowerShell will look for your module.</span></span> <span data-ttu-id="756ff-126">Es wird jedoch empfohlen, dies zu tun, es sei denn, Sie haben einen guten Grund, das Modul an anderer Stelle zu speichern.</span><span class="sxs-lookup"><span data-stu-id="756ff-126">However, it is considered best practice to do so, unless you have a good reason for storing your module somewhere else.</span></span> <span data-ttu-id="756ff-127">Weitere Informationen finden Sie unter [Installieren eines PowerShell-Moduls](./installing-a-powershell-module.md) und [Ändern des Installations Pfads des PowerShell-Moduls](./modifying-the-psmodulepath-installation-path.md).</span><span class="sxs-lookup"><span data-stu-id="756ff-127">For more information, see [Installing a PowerShell Module](./installing-a-powershell-module.md) and [Modifying the PowerShell Module Installation Path](./modifying-the-psmodulepath-installation-path.md).</span></span>

4. <span data-ttu-id="756ff-128">Importieren Sie das Modul mit einem [Import-Module-](/powershell/module/Microsoft.PowerShell.Core/Import-Module)Befehl in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="756ff-128">Import your module into PowerShell with a call to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).</span></span>

   <span data-ttu-id="756ff-129">Wenn Sie " [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) " aufrufen, wird das Modul in den aktiven Arbeitsspeicher geladen.</span><span class="sxs-lookup"><span data-stu-id="756ff-129">Calling to [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) will load your module into active memory.</span></span> <span data-ttu-id="756ff-130">Wenn Sie PowerShell 3,0 und höher verwenden, wird das einfache Aufrufen des Namens Ihres Moduls im Code ebenfalls importiert. Weitere Informationen finden Sie unter [Importieren eines PowerShell-Moduls](./importing-a-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="756ff-130">If you are using PowerShell 3.0 and later, simply calling the name of your module in code will also import it; for more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).</span></span>

## <a name="importing-snap-in-assemblies-as-modules"></a><span data-ttu-id="756ff-131">Importieren von Snap-in-Assemblys als Module</span><span class="sxs-lookup"><span data-stu-id="756ff-131">Importing Snap-in Assemblies as Modules</span></span>

<span data-ttu-id="756ff-132">Cmdlets und Anbieter, die in Snap-in-Assemblys vorhanden sind, können als binäre Module geladen werden.</span><span class="sxs-lookup"><span data-stu-id="756ff-132">Cmdlets and providers that exist in snap-in assemblies can be loaded as binary modules.</span></span> <span data-ttu-id="756ff-133">Wenn die Snap-in-Assemblys als binäre Module geladen werden, sind die Cmdlets und Anbieter im Snap-in für den Benutzer verfügbar, aber die Snap-in-Klasse in der Assembly wird ignoriert, und das Snap-in wird nicht registriert.</span><span class="sxs-lookup"><span data-stu-id="756ff-133">When the snap-in assemblies are loaded as binary modules, the cmdlets and providers in the snap-in are available to the user, but the snap-in class in the assembly is ignored, and the snap-in is not registered.</span></span> <span data-ttu-id="756ff-134">Folglich können die von Windows PowerShell bereitgestellten Snap-in-Cmdlets das Snap-in nicht erkennen, obwohl die Cmdlets und Anbieter für die Sitzung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="756ff-134">As a result, the snap-in cmdlets provided by Windows PowerShell cannot detect the snap-in even though the cmdlets and providers are available to the session.</span></span>

<span data-ttu-id="756ff-135">Außerdem können alle Formatierungs-oder Typen Dateien, auf die durch das Snap-in verwiesen wird, nicht als Teil eines binären Moduls importiert werden.</span><span class="sxs-lookup"><span data-stu-id="756ff-135">In addition, any formatting or types files that are referenced by the snap-in cannot be imported as part of a binary module.</span></span>
<span data-ttu-id="756ff-136">Zum Importieren der Formatierungs-und Typen Dateien müssen Sie ein Modul Manifest erstellen.</span><span class="sxs-lookup"><span data-stu-id="756ff-136">To import the formatting and types files you must create a module manifest.</span></span>
<span data-ttu-id="756ff-137">Weitere Informationen finden Sie unter Gewusst [wie: Schreiben eines PowerShell-Modul Manifests](how-to-write-a-powershell-module-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="756ff-137">See, [How to Write a PowerShell Module Manifest](how-to-write-a-powershell-module-manifest.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="756ff-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="756ff-138">See Also</span></span>

[<span data-ttu-id="756ff-139">Schreiben eines Windows PowerShell-Moduls</span><span class="sxs-lookup"><span data-stu-id="756ff-139">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)
