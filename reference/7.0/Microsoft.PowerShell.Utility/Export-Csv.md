---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: bb2d077b3584d4501db00a927b83034d37dceaec
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913358"
---
# <span data-ttu-id="00dd7-102">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="00dd7-102">Export-Csv</span></span>

## <span data-ttu-id="00dd7-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="00dd7-103">SYNOPSIS</span></span>
<span data-ttu-id="00dd7-104">Konvertiert-Objekte in eine Reihe von CSV-Zeichen folgen (Comma-Separated Value, Komma getrennte Werte) und speichert die Zeichen folgen in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="00dd7-104">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="00dd7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="00dd7-105">SYNTAX</span></span>

### <span data-ttu-id="00dd7-106">Trennzeichen (Standard)</span><span class="sxs-lookup"><span data-stu-id="00dd7-106">Delimiter (Default)</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="00dd7-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="00dd7-107">UseCulture</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="00dd7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="00dd7-108">DESCRIPTION</span></span>

<span data-ttu-id="00dd7-109">Mit dem- `Export-CSV` Cmdlet wird eine CSV-Datei mit den von Ihnen übermittelten Objekten erstellt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-109">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="00dd7-110">Jedes-Objekt ist eine Zeile, die eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts enthält.</span><span class="sxs-lookup"><span data-stu-id="00dd7-110">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="00dd7-111">Sie können das `Export-CSV` Cmdlet verwenden, um Tabellen zu erstellen und Daten für Programme freizugeben, die CSV-Dateien als Eingabe akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="00dd7-111">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="00dd7-112">Formatieren Sie Objekte nicht, bevor Sie Sie an das `Export-CSV` Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-112">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="00dd7-113">Wenn `Export-CSV` formatierte Objekte empfängt, enthält die CSV-Datei anstelle der Objekteigenschaften die Format Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="00dd7-113">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="00dd7-114">Verwenden Sie das-Cmdlet, um nur ausgewählte Eigenschaften eines Objekts zu exportieren `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="00dd7-114">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="00dd7-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="00dd7-115">EXAMPLES</span></span>

### <span data-ttu-id="00dd7-116">Beispiel 1: Exportieren von Prozess Eigenschaften in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="00dd7-116">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="00dd7-117">In diesem Beispiel werden **Prozess** Objekte mit bestimmten Eigenschaften ausgewählt, die Objekte werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-117">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

```powershell
Get-Process -Name WmiPrvSE | Select-Object -Property BasePriority,Id,SessionId,WorkingSet |
  Export-Csv -Path .\WmiData.csv -NoTypeInformation
Import-Csv -Path .\WmiData.csv
```

```Output
BasePriority Id    SessionId WorkingSet
------------ --    --------- ----------
8            976   0         20267008
8            2292  0         36786176
8            3816  0         30351360
8            8604  0         15011840
8            10008 0         8830976
8            11764 0         14237696
8            54632 0         9502720
```

<span data-ttu-id="00dd7-118">Mit dem- `Get-Process` Cmdlet werden die **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-118">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="00dd7-119">Mit dem **Name** -Parameter wird die Ausgabe so gefiltert, dass nur die wmiprvse-Prozess Objekte einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-119">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="00dd7-120">Die Prozess Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-120">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="00dd7-121">`Select-Object` verwendet den **Property** -Parameter, um eine Teilmenge der Prozess Objekteigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-121">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="00dd7-122">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-122">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-123">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-123">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="00dd7-124">Der **path** -Parameter gibt an, dass die WmiData.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-124">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="00dd7-125">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00dd7-125">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="00dd7-126">Das `Import-Csv` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-126">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="00dd7-127">Beispiel 2: Exportieren von Prozessen in eine durch Trennzeichen getrennte Datei</span><span class="sxs-lookup"><span data-stu-id="00dd7-127">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="00dd7-128">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-128">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="00dd7-129">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-129">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="00dd7-130">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-130">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-131">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-131">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="00dd7-132">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-132">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="00dd7-133">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00dd7-133">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="00dd7-134">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-134">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="00dd7-135">Beispiel 3: Exportieren von Prozessen in eine durch Semikolons getrennte Datei</span><span class="sxs-lookup"><span data-stu-id="00dd7-135">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="00dd7-136">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine Datei mit einem Semikolon-Trennzeichen exportiert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-136">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="00dd7-137">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-137">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="00dd7-138">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-138">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-139">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-139">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="00dd7-140">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-140">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="00dd7-141">Mit dem **Delimiter** -Parameter wird ein Semikolon zum Trennen der Zeichen folgen Werte angegeben.</span><span class="sxs-lookup"><span data-stu-id="00dd7-141">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="00dd7-142">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00dd7-142">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="00dd7-143">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-143">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="00dd7-144">Beispiel 4: Exportieren von Prozessen mit dem Listen Trennzeichen der aktuellen Kultur</span><span class="sxs-lookup"><span data-stu-id="00dd7-144">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="00dd7-145">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-145">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="00dd7-146">Das Trennzeichen ist das Listen Trennzeichen der aktuellen Kultur.</span><span class="sxs-lookup"><span data-stu-id="00dd7-146">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="00dd7-147">Das `Get-Culture` Cmdlet verwendet die genten Eigenschaften **TextInfo** und **ListSeparator** und zeigt das Standard Listen Trennzeichen der aktuellen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="00dd7-147">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="00dd7-148">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-148">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="00dd7-149">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-149">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-150">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-150">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="00dd7-151">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-151">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="00dd7-152">Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-152">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="00dd7-153">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00dd7-153">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="00dd7-154">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-154">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="00dd7-155">Beispiel 5: Exportieren von Prozessen mit Typinformationen</span><span class="sxs-lookup"><span data-stu-id="00dd7-155">Example 5: Export processes with type information</span></span>

<span data-ttu-id="00dd7-156">In diesem Beispiel wird erläutert, wie die **#Type** Header Informationen in eine CSV-Datei eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-156">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="00dd7-157">Der **#Type** -Header ist die Standardeinstellung in Versionen vor PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="00dd7-157">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -IncludeTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="00dd7-158">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-158">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="00dd7-159">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-159">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-160">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-160">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="00dd7-161">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-161">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="00dd7-162">**Includetypeinformation** enthält den **#Type** -Informations Header in der CSV-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="00dd7-162">The **IncludeTypeInformation** includes the **#TYPE** information header in the CSV output.</span></span> <span data-ttu-id="00dd7-163">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-163">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="00dd7-164">Beispiel 6: Exportieren und Anfügen von Objekten an eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="00dd7-164">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="00dd7-165">In diesem Beispiel wird beschrieben, wie Objekte in eine CSV-Datei exportiert werden und wie der **Append** -Parameter zum Hinzufügen von Objekten zu einer vorhandenen Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-165">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

```powershell
$AppService = (Get-Service -DisplayName *Application* | Select-Object -Property DisplayName, Status)
$AppService | Export-Csv -Path .\Services.Csv -NoTypeInformation
Get-Content -Path .\Services.Csv
$WinService = (Get-Service -DisplayName *Windows* | Select-Object -Property DisplayName, Status)
$WinService | Export-Csv -Path ./Services.csv -NoTypeInformation -Append
Get-Content -Path .\Services.Csv
```

```Output
"DisplayName","Status"
"Application Layer Gateway Service","Stopped"
"Application Identity","Running"
"Windows Audio Endpoint Builder","Running"
"Windows Audio","Running"
"Windows Event Log","Running"
```

<span data-ttu-id="00dd7-166">Mit dem- `Get-Service` Cmdlet werden Dienst Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-166">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="00dd7-167">Der **DisplayName** -Parameter gibt Dienste zurück, die die Word-Anwendung enthalten.</span><span class="sxs-lookup"><span data-stu-id="00dd7-167">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="00dd7-168">Die Dienst Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-168">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="00dd7-169">`Select-Object` verwendet den **Property** -Parameter, um die Eigenschaften " **Display Name** " und " **Status** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="00dd7-169">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="00dd7-170">Die- `$AppService` Variable speichert die-Objekte.</span><span class="sxs-lookup"><span data-stu-id="00dd7-170">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="00dd7-171">Die `$AppService` Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-171">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-172">`Export-Csv` Konvertiert die Dienst Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-172">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="00dd7-173">Der **path** -Parameter gibt an, dass die Services.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-173">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="00dd7-174">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00dd7-174">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="00dd7-175">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-175">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="00dd7-176">Die `Get-Service` -und- `Select-Object` Cmdlets werden für Dienste wiederholt, die das Word-Fenster enthalten.</span><span class="sxs-lookup"><span data-stu-id="00dd7-176">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="00dd7-177">Die- `$WinService` Variable speichert die Dienst Objekte.</span><span class="sxs-lookup"><span data-stu-id="00dd7-177">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="00dd7-178">Das `Export-Csv` Cmdlet verwendet den **Append** -Parameter, um anzugeben, dass die `$WinService` Objekte der vorhandenen Services.csv Datei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-178">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="00dd7-179">Das `Get-Content` Cmdlet wird wiederholt, um die aktualisierte Datei mit den angefügten Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-179">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="00dd7-180">Beispiel 7: das Cmdlet "Format" in einer Pipeline erstellt unerwartete Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="00dd7-180">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="00dd7-181">Dieses Beispiel zeigt, warum es wichtig ist, ein Format-Cmdlet nicht in einer Pipeline zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-181">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="00dd7-182">Wenn eine unerwartete Ausgabe empfangen wird, beheben Sie die Probleme mit der Pipeline Syntax.</span><span class="sxs-lookup"><span data-stu-id="00dd7-182">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

```powershell
Get-Date | Select-Object -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\DateTime.csv -NoTypeInformation
Get-Content -Path .\DateTime.csv
```

```Output
"DateTime","Day","DayOfWeek","DayOfYear"
"Wednesday, January 2, 2019 14:59:34","2","Wednesday","2"
```

```powershell
Get-Date | Format-Table -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\FTDateTime.csv -NoTypeInformation
Get-Content -Path .\FTDateTime.csv
```

```Output
"ClassId2e4f51ef21dd47e99d3c952918aff9cd","pageHeaderEntry","pageFooterEntry","autosizeInfo", ...
"033ecb2bc07a4d43b5ef94ed5a35d280",,,,"Microsoft.PowerShell.Commands.Internal.Format. ...
"9e210fe47d09416682b841769c78b8a3",,,,,
"27c87ef9bbda4f709f6b4002fa4af63c",,,,,
"4ec4f0187cb04f4cb6973460dfe252df",,,,,
"cf522b78d86c486691226b40aa69e95c",,,,,
```

<span data-ttu-id="00dd7-183">Mit dem- `Get-Date` Cmdlet wird das **DateTime** -Objekt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-183">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="00dd7-184">Das Objekt wird über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-184">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="00dd7-185">`Select-Object` verwendet den **Property** -Parameter, um eine Teilmenge von Objekteigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-185">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="00dd7-186">Das Objekt wird über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-186">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-187">`Export-Csv` Konvertiert das-Objekt in ein CSV-Format.</span><span class="sxs-lookup"><span data-stu-id="00dd7-187">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="00dd7-188">Der **path** -Parameter gibt an, dass die DateTime.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-188">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="00dd7-189">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00dd7-189">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="00dd7-190">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die CSV-Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-190">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="00dd7-191">Wenn das `Format-Table` Cmdlet in der Pipeline verwendet wird, um Eigenschaften auszuwählen, werden unerwartete Ergebnisse empfangen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-191">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="00dd7-192">`Format-Table` sendet Tabellenformat Objekte über die Pipeline an das `Export-Csv` Cmdlet und nicht an das **DateTime** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-192">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="00dd7-193">`Export-Csv` Konvertiert die Tabellenformat Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-193">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="00dd7-194">Das- `Get-Content` Cmdlet zeigt die CSV-Datei an, die die Tabellenformat Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="00dd7-194">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="00dd7-195">Beispiel 8: Verwenden des Force-Parameters, um schreibgeschützte Dateien zu überschreiben</span><span class="sxs-lookup"><span data-stu-id="00dd7-195">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="00dd7-196">In diesem Beispiel wird eine leere, schreibgeschützte Datei erstellt, und der **Force** -Parameter wird verwendet, um die Datei zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="00dd7-196">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

```powershell
New-Item -Path .\ReadOnly.csv -ItemType File
Set-ItemProperty -Path .\ReadOnly.csv -Name IsReadOnly -Value $true
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
```

```Output
Export-Csv : Access to the path 'C:\ReadOnly.csv' is denied.
At line:1 char:15
+ Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
+               ~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (:) [Export-Csv], UnauthorizedAccessException
+ FullyQualifiedErrorId : FileOpenFailure,Microsoft.PowerShell.Commands.ExportCsvCommand
```

```powershell
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation -Force
Get-Content -Path .\ReadOnly.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="00dd7-197">Das `New-Item` Cmdlet verwendet den **path** -Parameter und den **ItemType** -Parameter, um die ReadOnly.csv Datei im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-197">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="00dd7-198">Das `Set-ItemProperty` Cmdlet verwendet die Parameter **Name** und **value** , um die **isschreib only** -Eigenschaft der Datei in true zu ändern.</span><span class="sxs-lookup"><span data-stu-id="00dd7-198">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="00dd7-199">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-199">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="00dd7-200">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-200">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-201">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-201">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="00dd7-202">Der **path** -Parameter gibt an, dass die ReadOnly.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-202">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="00dd7-203">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00dd7-203">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="00dd7-204">Die Ausgabe zeigt, dass die Datei nicht geschrieben wurde, weil der Zugriff verweigert wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-204">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="00dd7-205">Der **Force** -Parameter wird zum `Export-Csv` Cmdlet hinzugefügt, um den Export in die Datei zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-205">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="00dd7-206">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-206">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="00dd7-207">Beispiel 9: Verwenden des Force-Parameters mit Append</span><span class="sxs-lookup"><span data-stu-id="00dd7-207">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="00dd7-208">In diesem Beispiel wird gezeigt, wie die **Force** -und **Append** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-208">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="00dd7-209">Wenn diese Parameter kombiniert werden, können nicht übereinstimmende Objekteigenschaften in eine CSV-Datei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-209">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

```powershell
$Content = [PSCustomObject]@{Name = 'PowerShell Core'; Version = '6.0'}
$Content | Export-Csv -Path .\ParmFile.csv -NoTypeInformation
$AdditionalContent = [PSCustomObject]@{Name = 'Windows PowerShell'; Edition = 'Desktop'}
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
```

```Output
Export-Csv : Cannot append CSV content to the following file: ParmFile.csv.
The appended object does not have a property that corresponds to the following column:
Version. To continue with mismatched properties, add the -Force parameter, and then retry
 the command.
At line:1 char:22
+ $AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (Version:String) [Export-Csv], InvalidOperationException
+ FullyQualifiedErrorId : CannotAppendCsvWithMismatchedPropertyNames,Microsoft.PowerShell. ...
```

```powershell
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append -Force
Import-Csv -Path .\ParmFile.csv
```

```Output
Name               Version
----               -------
PowerShell Core    6.0
Windows PowerShell
```

<span data-ttu-id="00dd7-210">Ein Ausdruck erstellt das **pscustomobject** mit den Eigenschaften " **Name** " und " **Version** ".</span><span class="sxs-lookup"><span data-stu-id="00dd7-210">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="00dd7-211">Die Werte werden in der `$Content` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-211">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="00dd7-212">Die `$Content` Variable wird an das Cmdlet über die Pipeline gesendet `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="00dd7-212">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-213">`Export-Csv` verwendet den **path** -Parameter und speichert die ParmFile.csv Datei im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="00dd7-213">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="00dd7-214">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00dd7-214">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="00dd7-215">Ein anderer Ausdruck erstellt ein **pscustomobject** mit den Eigenschaften **Name** und **Edition** .</span><span class="sxs-lookup"><span data-stu-id="00dd7-215">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="00dd7-216">Die Werte werden in der `$AdditionalContent` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-216">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="00dd7-217">Die `$AdditionalContent` Variable wird an das Cmdlet über die Pipeline gesendet `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="00dd7-217">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="00dd7-218">Der **Append** -Parameter wird verwendet, um die Daten der Datei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-218">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="00dd7-219">Der Anfüge Vorgang schlägt fehl, da der Eigenschaften Name zwischen **Version** und **Edition** nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-219">The append fails because there is a property name mismatch between **Version** and **Edition**.</span></span>

<span data-ttu-id="00dd7-220">Der `Export-Csv` Cmdlet- **Force** -Parameter wird verwendet, um den Export zum Schreiben in die Datei zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-220">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="00dd7-221">Die **Edition** -Eigenschaft wird verworfen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-221">The **Edition** property is discarded.</span></span> <span data-ttu-id="00dd7-222">Das `Import-Csv` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-222">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="00dd7-223">Beispiel 10: Exportieren nach CSV mit Anführungszeichen um zwei Spalten</span><span class="sxs-lookup"><span data-stu-id="00dd7-223">Example 10: Export to CSV with quotes around two columns</span></span>

<span data-ttu-id="00dd7-224">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-224">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -QuoteFields "DateTime","Date" -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### <span data-ttu-id="00dd7-225">Beispiel 11: Exportieren in CSV nur bei Bedarf mit Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="00dd7-225">Example 11: Export to CSV with quotes only when needed</span></span>

<span data-ttu-id="00dd7-226">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-226">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -UseQuotes AsNeeded -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## <span data-ttu-id="00dd7-227">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="00dd7-227">PARAMETERS</span></span>

### <span data-ttu-id="00dd7-228">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="00dd7-228">-Append</span></span>

<span data-ttu-id="00dd7-229">Verwenden Sie diesen Parameter, um `Export-CSV` die CSV-Ausgabe am Ende der angegebenen Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-229">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="00dd7-230">Ohne diesen Parameter `Export-CSV` ersetzt den Dateiinhalt ohne Warnung.</span><span class="sxs-lookup"><span data-stu-id="00dd7-230">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="00dd7-231">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-231">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-232">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="00dd7-232">-Delimiter</span></span>

<span data-ttu-id="00dd7-233">Gibt ein Trennzeichen zum Trennen der Eigenschaftswerte an.</span><span class="sxs-lookup"><span data-stu-id="00dd7-233">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="00dd7-234">Der Standardwert ist ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="00dd7-234">The default is a comma (`,`).</span></span> <span data-ttu-id="00dd7-235">Geben Sie ein Zeichen ein, z. b. einen Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="00dd7-235">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="00dd7-236">Um ein Semikolon ( `;` ) anzugeben, müssen Sie es in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-236">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-237">-Codierung</span><span class="sxs-lookup"><span data-stu-id="00dd7-237">-Encoding</span></span>

<span data-ttu-id="00dd7-238">Gibt die Codierung für die exportierte CSV-Datei an.</span><span class="sxs-lookup"><span data-stu-id="00dd7-238">Specifies the encoding for the exported CSV file.</span></span> <span data-ttu-id="00dd7-239">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="00dd7-239">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="00dd7-240">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="00dd7-240">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="00dd7-241">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="00dd7-241">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="00dd7-242">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="00dd7-242">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="00dd7-243">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="00dd7-243">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="00dd7-244">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="00dd7-244">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="00dd7-245">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="00dd7-245">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="00dd7-246">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="00dd7-246">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="00dd7-247">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="00dd7-247">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="00dd7-248">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="00dd7-248">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="00dd7-249">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="00dd7-249">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="00dd7-250">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="00dd7-250">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="00dd7-251">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="00dd7-251">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-252">-Force</span><span class="sxs-lookup"><span data-stu-id="00dd7-252">-Force</span></span>

<span data-ttu-id="00dd7-253">Dieser Parameter ermöglicht das `Export-Csv` Überschreiben von Dateien mit dem **Read-Only** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="00dd7-253">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="00dd7-254">Wenn **Force** -und **Append** -Parameter kombiniert werden, können Objekte, die nicht übereinstimmende Eigenschaften enthalten, in eine CSV-Datei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-254">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="00dd7-255">Nur die Eigenschaften, die mit verglichen werden, werden in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="00dd7-255">Only the properties that match are written to the file.</span></span> <span data-ttu-id="00dd7-256">Die nicht übereinstimmenden Eigenschaften werden verworfen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-256">The mismatched properties are discarded.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-257">-Includecotypeinformation</span><span class="sxs-lookup"><span data-stu-id="00dd7-257">-IncludeTypeInformation</span></span>

<span data-ttu-id="00dd7-258">Wenn dieser Parameter verwendet wird, enthält die erste Zeile der CSV-Ausgabe **#Type** gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="00dd7-258">When this parameter is used the first line of the CSV output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="00dd7-259">#Type z. b. **System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="00dd7-259">For example, **#TYPE System.Diagnostics.Process**.</span></span>

<span data-ttu-id="00dd7-260">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-260">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-261">-InputObject</span><span class="sxs-lookup"><span data-stu-id="00dd7-261">-InputObject</span></span>

<span data-ttu-id="00dd7-262">Gibt die als CSV-Zeichenfolgen zu exportierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="00dd7-262">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="00dd7-263">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-263">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="00dd7-264">Sie können Objekte auch über die Pipeline an übergeben `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="00dd7-264">You can also pipe objects to `Export-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-265">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="00dd7-265">-LiteralPath</span></span>

<span data-ttu-id="00dd7-266">Gibt den Pfad zur CSV-Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="00dd7-266">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="00dd7-267">Im Gegensatz zu **Path** wird der Wert des **LiteralPath**-Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="00dd7-267">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="00dd7-268">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-268">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="00dd7-269">Wenn der Pfad Escapezeichen enthält, verwenden Sie einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-269">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="00dd7-270">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="00dd7-270">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, LP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-271">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="00dd7-271">-NoClobber</span></span>

<span data-ttu-id="00dd7-272">Verwenden Sie diesen Parameter, damit `Export-CSV` eine vorhandene Datei nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-272">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="00dd7-273">Wenn die Datei im angegebenen Pfad vorhanden ist, wird `Export-CSV` die Datei standardmäßig ohne Warnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="00dd7-273">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-274">-Notypeinformation</span><span class="sxs-lookup"><span data-stu-id="00dd7-274">-NoTypeInformation</span></span>

<span data-ttu-id="00dd7-275">Entfernt den **#Type** Informations Header aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="00dd7-275">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="00dd7-276">Dieser Parameter wurde in PowerShell 6,0 zum Standard und ist aus Gründen der Abwärtskompatibilität eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-276">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-277">-Path</span><span class="sxs-lookup"><span data-stu-id="00dd7-277">-Path</span></span>

<span data-ttu-id="00dd7-278">Ein erforderlicher Parameter, der den Speicherort zum Speichern der CSV-Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-278">A required parameter that specifies the location to save the CSV output file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-279">-Useculture</span><span class="sxs-lookup"><span data-stu-id="00dd7-279">-UseCulture</span></span>

<span data-ttu-id="00dd7-280">Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-280">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="00dd7-281">Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="00dd7-281">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-282">-Confirm</span><span class="sxs-lookup"><span data-stu-id="00dd7-282">-Confirm</span></span>

<span data-ttu-id="00dd7-283">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-283">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-284">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="00dd7-284">-WhatIf</span></span>

<span data-ttu-id="00dd7-285">Verhindert, dass das Cmdlet verarbeitet wird oder Änderungen vornimmt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-285">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="00dd7-286">Die Ausgabe zeigt, was geschieht, wenn das Cmdlet ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="00dd7-286">The output shows what would happen if the cmdlet were run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-287">-Quotefields</span><span class="sxs-lookup"><span data-stu-id="00dd7-287">-QuoteFields</span></span>

<span data-ttu-id="00dd7-288">Gibt die Namen der Spalten an, die in Anführungszeichen eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-288">Specifies the names of the columns that should be quoted.</span></span> <span data-ttu-id="00dd7-289">Wenn dieser Parameter verwendet wird, werden nur die angegebenen Spalten in Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-289">When this parameter is used, only the specified columns are quoted.</span></span> <span data-ttu-id="00dd7-290">Dieser Parameter wurde in PowerShell 7,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-290">This parameter was added in PowerShell 7.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: QF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-291">-Usequotes</span><span class="sxs-lookup"><span data-stu-id="00dd7-291">-UseQuotes</span></span>

<span data-ttu-id="00dd7-292">Gibt an, wann Anführungszeichen in den CSV-Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-292">Specifies when quotes are used in the CSV files.</span></span> <span data-ttu-id="00dd7-293">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="00dd7-293">Possible values are:</span></span>

- <span data-ttu-id="00dd7-294">Niemals etwas angeben</span><span class="sxs-lookup"><span data-stu-id="00dd7-294">Never - don't quote anything</span></span>
- <span data-ttu-id="00dd7-295">Alles immer angeben (Standardverhalten)</span><span class="sxs-lookup"><span data-stu-id="00dd7-295">Always - quote everything (default behavior)</span></span>
- <span data-ttu-id="00dd7-296">Asbedarf-nur Anführungszeichen Felder, die ein Trennzeichen enthalten</span><span class="sxs-lookup"><span data-stu-id="00dd7-296">AsNeeded - only quote fields that contain a delimiter character</span></span>

<span data-ttu-id="00dd7-297">Dieser Parameter wurde in PowerShell 7,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-297">This parameter was added in PowerShell 7.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BaseCsvWritingCommand+QuoteKind
Parameter Sets: (All)
Aliases: UQ

Required: False
Position: Named
Default value: Always
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="00dd7-298">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="00dd7-298">CommonParameters</span></span>

<span data-ttu-id="00dd7-299">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="00dd7-299">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="00dd7-300">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="00dd7-300">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="00dd7-301">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="00dd7-301">INPUTS</span></span>

### <span data-ttu-id="00dd7-302">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="00dd7-302">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="00dd7-303">Sie können jedes beliebige Objekt mit einem "ETS"-Adapter (Extended Type System) an über die Pipeline übergeben `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="00dd7-303">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="00dd7-304">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="00dd7-304">OUTPUTS</span></span>

### <span data-ttu-id="00dd7-305">System.String</span><span class="sxs-lookup"><span data-stu-id="00dd7-305">System.String</span></span>

<span data-ttu-id="00dd7-306">Die CSV-Liste wird an die im Path-Parameter festgelegte Datei gesendet.</span><span class="sxs-lookup"><span data-stu-id="00dd7-306">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="00dd7-307">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="00dd7-307">NOTES</span></span>

<span data-ttu-id="00dd7-308">Das `Export-CSV` -Cmdlet konvertiert die Objekte, die Sie in eine Reihe von CSV-Zeichen folgen übermitteln, und speichert Sie in der angegebenen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="00dd7-308">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="00dd7-309">Sie können verwenden `Export-CSV -IncludeTypeInformation` , um Objekte in einer CSV-Datei zu speichern. verwenden Sie dann das `Import-Csv` Cmdlet, um Objekte aus dem Text in der CSV-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-309">You can use `Export-CSV -IncludeTypeInformation` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the text in the CSV file.</span></span>

<span data-ttu-id="00dd7-310">In der CSV-Datei wird jedes Objekt durch eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-310">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="00dd7-311">Die Eigenschaftswerte werden mithilfe der Methode " **destring ()** " in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-311">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="00dd7-312">Die Zeichen folgen werden durch den Namen des Eigenschafts Werts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="00dd7-312">The strings are represented by the property value name.</span></span> <span data-ttu-id="00dd7-313">`Export-CSV -IncludeTypeInformation` exportiert nicht die Methoden des-Objekts.</span><span class="sxs-lookup"><span data-stu-id="00dd7-313">`Export-CSV -IncludeTypeInformation` does not export the methods of the object.</span></span>

<span data-ttu-id="00dd7-314">Die CSV-Zeichen folgen werden wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="00dd7-314">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="00dd7-315">Wenn **includetypeinformation** verwendet wird, enthält die erste Zeichenfolge den **#Type** Informations Header, gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="00dd7-315">If **IncludeTypeInformation** is used, the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span>
  <span data-ttu-id="00dd7-316">#Type z. b. **System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="00dd7-316">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="00dd7-317">Wenn **include TypeInformation** nicht verwendet wird, enthält die erste Zeichenfolge die Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="00dd7-317">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="00dd7-318">Die Header enthalten die Eigenschaftsnamen des ersten Objekts als durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="00dd7-318">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="00dd7-319">Die übrigen Zeichen folgen enthalten durch Trennzeichen getrennte Listen der Eigenschaftswerte jedes Objekts.</span><span class="sxs-lookup"><span data-stu-id="00dd7-319">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="00dd7-320">Ab PowerShell 6,0 ist das Standardverhalten von `Export-CSV` , wenn die **#Type** Informationen in das CSV nicht eingeschlossen werden und **notypeinformation** impliziert ist.</span><span class="sxs-lookup"><span data-stu-id="00dd7-320">Beginning with PowerShell 6.0 the default behavior of `Export-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="00dd7-321">**Includetypeinformation** kann verwendet werden, um die **#Type** Informationen einzuschließen und das Standardverhalten von `Export-CSV` vor PowerShell 6,0 zu emulieren.</span><span class="sxs-lookup"><span data-stu-id="00dd7-321">**IncludeTypeInformation** can be used to include the **#TYPE** Information and emulate the default behavior of `Export-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="00dd7-322">Wenn Sie mehrere Objekte an senden `Export-CSV` , wird `Export-CSV` die Datei von basierend auf den Eigenschaften des ersten von Ihnen gesendeten Objekts organisiert.</span><span class="sxs-lookup"><span data-stu-id="00dd7-322">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="00dd7-323">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschaftswert dieses Objekts NULL, was durch zwei aufeinander folgende Kommas dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="00dd7-323">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="00dd7-324">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, sind diese Eigenschaftenwerte nicht in der Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="00dd7-324">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="00dd7-325">Sie können das `Import-Csv` Cmdlet verwenden, um Objekte aus den CSV-Zeichen folgen in den Dateien neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-325">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="00dd7-326">Die resultierenden Objekte sind CSV-Versionen der ursprünglichen Objekte, die aus den Zeichenfolgendarstellungen der Eigenschaftswerte bestehen und die keine Methoden haben.</span><span class="sxs-lookup"><span data-stu-id="00dd7-326">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="00dd7-327">Die `ConvertTo-Csv` -und- `ConvertFrom-Csv` Cmdlets konvertieren Objekte in CSV-Zeichen folgen und aus CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="00dd7-327">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="00dd7-328">`Export-CSV` ist identisch `ConvertTo-CSV` mit, außer dass die CSV-Zeichen folgen in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="00dd7-328">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="00dd7-329">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="00dd7-329">RELATED LINKS</span></span>

[<span data-ttu-id="00dd7-330">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="00dd7-330">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="00dd7-331">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="00dd7-331">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="00dd7-332">Format-Table</span><span class="sxs-lookup"><span data-stu-id="00dd7-332">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="00dd7-333">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="00dd7-333">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="00dd7-334">Select-Object</span><span class="sxs-lookup"><span data-stu-id="00dd7-334">Select-Object</span></span>](Select-Object.md)
