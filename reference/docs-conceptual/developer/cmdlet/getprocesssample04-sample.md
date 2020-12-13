---
ms.date: 09/13/2016
ms.topic: reference
title: GetProcessSample04-Beispiel
description: GetProcessSample04-Beispiel
ms.openlocfilehash: 4b2b7f7ed5fd87711d0d7872caaf75d453de4832
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652734"
---
# <a name="getprocesssample04-sample"></a><span data-ttu-id="95dcf-103">GetProcessSample04-Beispiel</span><span class="sxs-lookup"><span data-stu-id="95dcf-103">GetProcessSample04 Sample</span></span>

<span data-ttu-id="95dcf-104">In diesem Beispiel wird gezeigt, wie ein Cmdlet implementiert wird, das die Prozesse auf dem lokalen Computer abruft.</span><span class="sxs-lookup"><span data-stu-id="95dcf-104">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="95dcf-105">Darin wird ein Fehler ohne Abbruch generiert, wenn es beim Abrufen eines Prozesses zu einem Fehler kommt.</span><span class="sxs-lookup"><span data-stu-id="95dcf-105">It generates a nonterminating error if an error occurs while retrieving a process.</span></span> <span data-ttu-id="95dcf-106">Dieses Cmdlet ist eine vereinfachte Version des `Get-Process` Cmdlets, das von Windows PowerShell 2,0 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="95dcf-106">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="95dcf-107">So erstellen Sie das Beispiel mithilfe von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="95dcf-107">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="95dcf-108">Navigieren Sie mit installiertem Windows PowerShell 2,0 SDK zum Ordner GetProcessSample04.</span><span class="sxs-lookup"><span data-stu-id="95dcf-108">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample04 folder.</span></span> <span data-ttu-id="95dcf-109">Der Standard Speicherort ist "c:\Programme (x86) \Microsoft SDKs\Windows\v7.0\samples\sysmgmt\windowspowershell\csharp\getprocesssample04.".</span><span class="sxs-lookup"><span data-stu-id="95dcf-109">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.</span></span>

2. <span data-ttu-id="95dcf-110">Doppelklicken Sie auf das Symbol für die Projektmappendatei (. sln).</span><span class="sxs-lookup"><span data-stu-id="95dcf-110">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="95dcf-111">Dadurch wird das Beispiel Projekt in Visual Studio geöffnet.</span><span class="sxs-lookup"><span data-stu-id="95dcf-111">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="95dcf-112">Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="95dcf-112">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="95dcf-113">Die Bibliothek für das Beispiel wird im Standardordner \bin oder \bin\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="95dcf-113">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="95dcf-114">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="95dcf-114">How to run the sample</span></span>

1. <span data-ttu-id="95dcf-115">Erstellen Sie den folgenden Modul Ordner:</span><span class="sxs-lookup"><span data-stu-id="95dcf-115">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample04`

2. <span data-ttu-id="95dcf-116">Kopieren Sie die Beispielassembly in den Modul Ordner.</span><span class="sxs-lookup"><span data-stu-id="95dcf-116">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="95dcf-117">Starten Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95dcf-117">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="95dcf-118">Führen Sie den folgenden Befehl aus, um die Assembly in Windows PowerShell zu laden:</span><span class="sxs-lookup"><span data-stu-id="95dcf-118">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample04`

5. <span data-ttu-id="95dcf-119">Führen Sie den folgenden Befehl aus, um das Cmdlet auszuführen:</span><span class="sxs-lookup"><span data-stu-id="95dcf-119">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="95dcf-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95dcf-120">Requirements</span></span>

<span data-ttu-id="95dcf-121">Dieses Beispiel erfordert Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="95dcf-121">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="95dcf-122">Zeigt</span><span class="sxs-lookup"><span data-stu-id="95dcf-122">Demonstrates</span></span>

<span data-ttu-id="95dcf-123">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="95dcf-123">This sample demonstrates the following.</span></span>

- <span data-ttu-id="95dcf-124">Deklarieren einer Cmdlet-Klasse mithilfe des Cmdlet-Attributs.</span><span class="sxs-lookup"><span data-stu-id="95dcf-124">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="95dcf-125">Deklarieren eines Cmdlet-Parameters mithilfe des Parameter-Attributs.</span><span class="sxs-lookup"><span data-stu-id="95dcf-125">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="95dcf-126">Angeben der Position des Parameters.</span><span class="sxs-lookup"><span data-stu-id="95dcf-126">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="95dcf-127">Angeben, dass der Parameter Eingaben aus der Pipeline annimmt.</span><span class="sxs-lookup"><span data-stu-id="95dcf-127">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="95dcf-128">Die Eingabe kann aus einem Objekt oder einem Wert aus einer Eigenschaft eines Objekts entnommen werden, dessen Eigenschaftsname mit dem Parameternamen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="95dcf-128">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="95dcf-129">Deklarieren eines Validierungs Attributs für die Parameter Eingabe.</span><span class="sxs-lookup"><span data-stu-id="95dcf-129">Declaring a validation attribute for the parameter input.</span></span>

- <span data-ttu-id="95dcf-130">Das Abfangen eines Fehlers ohne Abbruch und das Schreiben einer Fehlermeldung in den Fehler Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="95dcf-130">Trapping a nonterminating error and writing an error message to the error stream.</span></span>

## <a name="example"></a><span data-ttu-id="95dcf-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="95dcf-131">Example</span></span>

<span data-ttu-id="95dcf-132">In diesem Beispiel wird gezeigt, wie ein Cmdlet erstellt wird, das nicht abschließende Fehler behandelt und Fehlermeldungen in den Fehler Datenstrom schreibt.</span><span class="sxs-lookup"><span data-stu-id="95dcf-132">This sample shows how to create a cmdlet that handles nonterminating errors and writes error messages to the error stream.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
    using System;
    using System.Diagnostics;
    using System.Management.Automation;      // Windows PowerShell namespace.
   #region GetProcCommand

   /// <summary>
   /// This class implements the get-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Parameters

       /// <summary>
       /// The names of the processes to act on.
       /// </summary>
       private string[] processNames;

      /// <summary>
      /// Gets or sets the list of process names on
      /// which the Get-Proc cmdlet will work.
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
          // If no process names are passed to cmdlet, get all
          // processes.
          if (this.processNames == null)
          {
              WriteObject(Process.GetProcesses(), true);
          }
          else
          {
              // If process names are passed to the cmdlet, get and write
              // the associated processes.
              // If a nonterminating error occurs while retrieving processes,
              // call the WriteError method to send an error record to the
              // error stream.
              foreach (string name in this.processNames)
              {
                  Process[] processes;

                  try
                  {
                      processes = Process.GetProcessesByName(name);
                  }
                  catch (InvalidOperationException ex)
                  {
                      WriteError(new ErrorRecord(
                         ex,
                         "UnableToAccessProcessByName",
                         ErrorCategory.InvalidOperation,
                         name));
                      continue;
                  }

                  WriteObject(processes, true);
              } // foreach (string name...
          } // else
      } // ProcessRecord

      #endregion Overrides
    } // End GetProcCommand class.

   #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="95dcf-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95dcf-133">See Also</span></span>

[<span data-ttu-id="95dcf-134">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="95dcf-134">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
