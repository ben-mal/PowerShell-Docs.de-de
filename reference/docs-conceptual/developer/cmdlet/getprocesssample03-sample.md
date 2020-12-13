---
ms.date: 09/13/2016
ms.topic: reference
title: GetProcessSample03-Beispiel
description: GetProcessSample03-Beispiel
ms.openlocfilehash: 7827247238f3dad2018b55e396b73d1fa434eb97
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660721"
---
# <a name="getprocesssample03-sample"></a><span data-ttu-id="2e76e-103">GetProcessSample03-Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e76e-103">GetProcessSample03 Sample</span></span>

<span data-ttu-id="2e76e-104">In diesem Beispiel wird gezeigt, wie ein Cmdlet implementiert wird, das die Prozesse auf dem lokalen Computer abruft.</span><span class="sxs-lookup"><span data-stu-id="2e76e-104">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="2e76e-105">Sie stellt einen `Name` Parameter bereit, der ein Objekt aus der Pipeline oder einen Wert aus einer Eigenschaft eines Objekts akzeptieren kann, dessen Eigenschaftsname mit dem Parameternamen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="2e76e-105">It provides a `Name` parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span> <span data-ttu-id="2e76e-106">Dieses Cmdlet ist eine vereinfachte Version des `Get-Process` Cmdlets, das von Windows PowerShell 2,0 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2e76e-106">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="2e76e-107">So erstellen Sie das Beispiel mithilfe von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2e76e-107">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="2e76e-108">Navigieren Sie mit installiertem Windows PowerShell 2,0 SDK zum Ordner GetProcessSample03.</span><span class="sxs-lookup"><span data-stu-id="2e76e-108">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample03 folder.</span></span> <span data-ttu-id="2e76e-109">Der Standard Speicherort ist "c:\Programme (x86) \Microsoft SDKs\Windows\v7.0\samples\sysmgmt\windowspowershell\csharp\getprocesssample03.".</span><span class="sxs-lookup"><span data-stu-id="2e76e-109">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample03.</span></span>

2. <span data-ttu-id="2e76e-110">Doppelklicken Sie auf das Symbol für die Projektmappendatei (. sln).</span><span class="sxs-lookup"><span data-stu-id="2e76e-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="2e76e-111">Dadurch wird das Beispiel Projekt in Visual Studio geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2e76e-111">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="2e76e-112">Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="2e76e-112">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="2e76e-113">Die Bibliothek für das Beispiel wird im Standardordner \bin oder \bin\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="2e76e-113">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="2e76e-114">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="2e76e-114">How to run the sample</span></span>

1. <span data-ttu-id="2e76e-115">Erstellen Sie den folgenden Modul Ordner:</span><span class="sxs-lookup"><span data-stu-id="2e76e-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample03`

2. <span data-ttu-id="2e76e-116">Kopieren Sie die Beispielassembly in den Modul Ordner.</span><span class="sxs-lookup"><span data-stu-id="2e76e-116">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="2e76e-117">Starten Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e76e-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="2e76e-118">Führen Sie den folgenden Befehl aus, um die Assembly in Windows PowerShell zu laden:</span><span class="sxs-lookup"><span data-stu-id="2e76e-118">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample03`

5. <span data-ttu-id="2e76e-119">Führen Sie den folgenden Befehl aus, um das Cmdlet auszuführen:</span><span class="sxs-lookup"><span data-stu-id="2e76e-119">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="2e76e-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e76e-120">Requirements</span></span>

<span data-ttu-id="2e76e-121">Dieses Beispiel erfordert Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="2e76e-121">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="2e76e-122">Zeigt</span><span class="sxs-lookup"><span data-stu-id="2e76e-122">Demonstrates</span></span>

<span data-ttu-id="2e76e-123">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="2e76e-123">This sample demonstrates the following.</span></span>

- <span data-ttu-id="2e76e-124">Deklarieren einer Cmdlet-Klasse mithilfe des Cmdlet-Attributs.</span><span class="sxs-lookup"><span data-stu-id="2e76e-124">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="2e76e-125">Deklarieren eines Cmdlet-Parameters mithilfe des Parameter-Attributs.</span><span class="sxs-lookup"><span data-stu-id="2e76e-125">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="2e76e-126">Angeben der Position des Parameters.</span><span class="sxs-lookup"><span data-stu-id="2e76e-126">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="2e76e-127">Angeben, dass der Parameter Eingaben aus der Pipeline annimmt.</span><span class="sxs-lookup"><span data-stu-id="2e76e-127">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="2e76e-128">Die Eingabe kann aus einem Objekt oder einem Wert aus einer Eigenschaft eines Objekts entnommen werden, dessen Eigenschaftsname mit dem Parameternamen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="2e76e-128">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="2e76e-129">Deklarieren eines Validierungs Attributs für die Parameter Eingabe.</span><span class="sxs-lookup"><span data-stu-id="2e76e-129">Declaring a validation attribute for the parameter input.</span></span>

## <a name="example"></a><span data-ttu-id="2e76e-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e76e-130">Example</span></span>

<span data-ttu-id="2e76e-131">Dieses Beispiel zeigt eine Implementierung des Get-Proc-Cmdlets, das einen `Name` Parameter enthält, der Eingaben aus der Pipeline akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="2e76e-131">This sample shows an implementation of the Get-Proc cmdlet that includes a `Name` parameter that accepts input from the pipeline.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
  using System;
  using System.Diagnostics;
  using System.Management.Automation;           // Windows PowerShell namespace
  #region GetProcCommand

  /// <summary>
  /// This class implements the get-proc cmdlet.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Parameters

    /// <summary>
    /// The names of the processes retrieved by the cmdlet.
    /// </summary>
    private string[] processNames;

    /// <summary>
    /// Gets or sets the names of the
    /// process that the cmdlet will retrieve.
    /// </summary>
    [Parameter(
               Position = 0,
               ValueFromPipeline = true,
               ValueFromPipelineByPropertyName = true)]
    [ValidateNotNullOrEmpty]
    public string[] Name
    {
      get { return this.processNames; }
      set { this.processNames = value; }
    }

    #endregion Parameters

    #region Cmdlet Overrides

    /// <summary>
    /// The ProcessRecord method calls the Process.GetProcesses
    /// method to retrieve the processes specified by the Name
    /// parameter. Then, the WriteObject method writes the
    /// associated processes to the pipeline.
    /// </summary>
    protected override void ProcessRecord()
    {
      // If no process names are passed to the cmdlet, get all
      // processes.
      if (this.processNames == null)
      {
        WriteObject(Process.GetProcesses(), true);
      }
      else
      {
        // If process names are passed to the cmdlet, get and write
        // the associated processes.
        foreach (string name in this.processNames)
        {
          WriteObject(Process.GetProcessesByName(name), true);
        }
      } // End if (processNames ...)
    } // End ProcessRecord.

    #endregion Overrides
  } // End GetProcCommand.
  #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="2e76e-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e76e-132">See Also</span></span>

[<span data-ttu-id="2e76e-133">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2e76e-133">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
