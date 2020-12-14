---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: f920130ec8354b61b0bb3617e061520271df0eed
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913235"
---
# <span data-ttu-id="207df-102">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="207df-102">Export-Csv</span></span>

## <span data-ttu-id="207df-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="207df-103">SYNOPSIS</span></span>
<span data-ttu-id="207df-104">Konvertiert-Objekte in eine Reihe von CSV-Zeichen folgen (Comma-Separated Value, Komma getrennte Werte) und speichert die Zeichen folgen in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="207df-104">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="207df-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="207df-105">SYNTAX</span></span>

### <span data-ttu-id="207df-106">Trennzeichen (Standard)</span><span class="sxs-lookup"><span data-stu-id="207df-106">Delimiter (Default)</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="207df-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="207df-107">UseCulture</span></span>

```
Export-Csv -InputObject <PSObject> [[-Path] <String>] [-LiteralPath <String>] [-Force] [-NoClobber]
 [-Encoding <Encoding>] [-Append] [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="207df-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="207df-108">DESCRIPTION</span></span>

<span data-ttu-id="207df-109">Mit dem- `Export-CSV` Cmdlet wird eine CSV-Datei mit den von Ihnen übermittelten Objekten erstellt.</span><span class="sxs-lookup"><span data-stu-id="207df-109">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="207df-110">Jedes-Objekt ist eine Zeile, die eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts enthält.</span><span class="sxs-lookup"><span data-stu-id="207df-110">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="207df-111">Sie können das `Export-CSV` Cmdlet verwenden, um Tabellen zu erstellen und Daten für Programme freizugeben, die CSV-Dateien als Eingabe akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="207df-111">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="207df-112">Formatieren Sie Objekte nicht, bevor Sie Sie an das `Export-CSV` Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="207df-112">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="207df-113">Wenn `Export-CSV` formatierte Objekte empfängt, enthält die CSV-Datei anstelle der Objekteigenschaften die Format Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="207df-113">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="207df-114">Verwenden Sie das-Cmdlet, um nur ausgewählte Eigenschaften eines Objekts zu exportieren `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="207df-114">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="207df-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="207df-115">EXAMPLES</span></span>

### <span data-ttu-id="207df-116">Beispiel 1: Exportieren von Prozess Eigenschaften in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="207df-116">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="207df-117">In diesem Beispiel werden **Prozess** Objekte mit bestimmten Eigenschaften ausgewählt, die Objekte werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="207df-117">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

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

<span data-ttu-id="207df-118">Mit dem- `Get-Process` Cmdlet werden die **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="207df-118">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="207df-119">Mit dem **Name** -Parameter wird die Ausgabe so gefiltert, dass nur die wmiprvse-Prozess Objekte einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="207df-119">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="207df-120">Die Prozess Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-120">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="207df-121">`Select-Object` verwendet den **Property** -Parameter, um eine Teilmenge der Prozess Objekteigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="207df-121">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="207df-122">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-122">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-123">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="207df-123">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="207df-124">Der **path** -Parameter gibt an, dass die WmiData.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="207df-124">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="207df-125">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="207df-125">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="207df-126">Das `Import-Csv` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-126">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="207df-127">Beispiel 2: Exportieren von Prozessen in eine durch Trennzeichen getrennte Datei</span><span class="sxs-lookup"><span data-stu-id="207df-127">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="207df-128">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="207df-128">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="207df-129">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="207df-129">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="207df-130">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-130">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-131">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="207df-131">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="207df-132">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="207df-132">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="207df-133">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="207df-133">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="207df-134">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-134">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="207df-135">Beispiel 3: Exportieren von Prozessen in eine durch Semikolons getrennte Datei</span><span class="sxs-lookup"><span data-stu-id="207df-135">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="207df-136">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine Datei mit einem Semikolon-Trennzeichen exportiert.</span><span class="sxs-lookup"><span data-stu-id="207df-136">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="207df-137">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="207df-137">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="207df-138">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-138">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-139">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="207df-139">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="207df-140">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="207df-140">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="207df-141">Mit dem **Delimiter** -Parameter wird ein Semikolon zum Trennen der Zeichen folgen Werte angegeben.</span><span class="sxs-lookup"><span data-stu-id="207df-141">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="207df-142">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="207df-142">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="207df-143">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-143">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="207df-144">Beispiel 4: Exportieren von Prozessen mit dem Listen Trennzeichen der aktuellen Kultur</span><span class="sxs-lookup"><span data-stu-id="207df-144">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="207df-145">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="207df-145">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="207df-146">Das Trennzeichen ist das Listen Trennzeichen der aktuellen Kultur.</span><span class="sxs-lookup"><span data-stu-id="207df-146">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="207df-147">Das `Get-Culture` Cmdlet verwendet die genten Eigenschaften **TextInfo** und **ListSeparator** und zeigt das Standard Listen Trennzeichen der aktuellen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="207df-147">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="207df-148">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="207df-148">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="207df-149">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-149">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-150">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="207df-150">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="207df-151">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="207df-151">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="207df-152">Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="207df-152">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="207df-153">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="207df-153">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="207df-154">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-154">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="207df-155">Beispiel 5: Exportieren von Prozessen mit Typinformationen</span><span class="sxs-lookup"><span data-stu-id="207df-155">Example 5: Export processes with type information</span></span>

<span data-ttu-id="207df-156">In diesem Beispiel wird erläutert, wie die **#Type** Header Informationen in eine CSV-Datei eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="207df-156">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="207df-157">Der **#Type** -Header ist die Standardeinstellung in Versionen vor PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="207df-157">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -IncludeTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="207df-158">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="207df-158">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="207df-159">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-159">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-160">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="207df-160">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="207df-161">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="207df-161">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="207df-162">**Includetypeinformation** enthält den **#Type** -Informations Header in der CSV-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="207df-162">The **IncludeTypeInformation** includes the **#TYPE** information header in the CSV output.</span></span> <span data-ttu-id="207df-163">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-163">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="207df-164">Beispiel 6: Exportieren und Anfügen von Objekten an eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="207df-164">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="207df-165">In diesem Beispiel wird beschrieben, wie Objekte in eine CSV-Datei exportiert werden und wie der **Append** -Parameter zum Hinzufügen von Objekten zu einer vorhandenen Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="207df-165">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

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

<span data-ttu-id="207df-166">Mit dem- `Get-Service` Cmdlet werden Dienst Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="207df-166">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="207df-167">Der **DisplayName** -Parameter gibt Dienste zurück, die die Word-Anwendung enthalten.</span><span class="sxs-lookup"><span data-stu-id="207df-167">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="207df-168">Die Dienst Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-168">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="207df-169">`Select-Object` verwendet den **Property** -Parameter, um die Eigenschaften " **Display Name** " und " **Status** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="207df-169">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="207df-170">Die- `$AppService` Variable speichert die-Objekte.</span><span class="sxs-lookup"><span data-stu-id="207df-170">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="207df-171">Die `$AppService` Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-171">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-172">`Export-Csv` Konvertiert die Dienst Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="207df-172">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="207df-173">Der **path** -Parameter gibt an, dass die Services.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="207df-173">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="207df-174">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="207df-174">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="207df-175">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-175">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="207df-176">Die `Get-Service` -und- `Select-Object` Cmdlets werden für Dienste wiederholt, die das Word-Fenster enthalten.</span><span class="sxs-lookup"><span data-stu-id="207df-176">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="207df-177">Die- `$WinService` Variable speichert die Dienst Objekte.</span><span class="sxs-lookup"><span data-stu-id="207df-177">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="207df-178">Das `Export-Csv` Cmdlet verwendet den **Append** -Parameter, um anzugeben, dass die `$WinService` Objekte der vorhandenen Services.csv Datei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="207df-178">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="207df-179">Das `Get-Content` Cmdlet wird wiederholt, um die aktualisierte Datei mit den angefügten Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-179">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="207df-180">Beispiel 7: das Cmdlet "Format" in einer Pipeline erstellt unerwartete Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="207df-180">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="207df-181">Dieses Beispiel zeigt, warum es wichtig ist, ein Format-Cmdlet nicht in einer Pipeline zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="207df-181">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="207df-182">Wenn eine unerwartete Ausgabe empfangen wird, beheben Sie die Probleme mit der Pipeline Syntax.</span><span class="sxs-lookup"><span data-stu-id="207df-182">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

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

<span data-ttu-id="207df-183">Mit dem- `Get-Date` Cmdlet wird das **DateTime** -Objekt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="207df-183">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="207df-184">Das Objekt wird über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-184">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="207df-185">`Select-Object` verwendet den **Property** -Parameter, um eine Teilmenge von Objekteigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="207df-185">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="207df-186">Das Objekt wird über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-186">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-187">`Export-Csv` Konvertiert das-Objekt in ein CSV-Format.</span><span class="sxs-lookup"><span data-stu-id="207df-187">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="207df-188">Der **path** -Parameter gibt an, dass die DateTime.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="207df-188">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="207df-189">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="207df-189">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="207df-190">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die CSV-Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-190">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="207df-191">Wenn das `Format-Table` Cmdlet in der Pipeline verwendet wird, um Eigenschaften auszuwählen, werden unerwartete Ergebnisse empfangen.</span><span class="sxs-lookup"><span data-stu-id="207df-191">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="207df-192">`Format-Table` sendet Tabellenformat Objekte über die Pipeline an das `Export-Csv` Cmdlet und nicht an das **DateTime** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="207df-192">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="207df-193">`Export-Csv` Konvertiert die Tabellenformat Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="207df-193">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="207df-194">Das- `Get-Content` Cmdlet zeigt die CSV-Datei an, die die Tabellenformat Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="207df-194">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="207df-195">Beispiel 8: Verwenden des Force-Parameters, um schreibgeschützte Dateien zu überschreiben</span><span class="sxs-lookup"><span data-stu-id="207df-195">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="207df-196">In diesem Beispiel wird eine leere, schreibgeschützte Datei erstellt, und der **Force** -Parameter wird verwendet, um die Datei zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="207df-196">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

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

<span data-ttu-id="207df-197">Das `New-Item` Cmdlet verwendet den **path** -Parameter und den **ItemType** -Parameter, um die ReadOnly.csv Datei im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="207df-197">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="207df-198">Das `Set-ItemProperty` Cmdlet verwendet die Parameter **Name** und **value** , um die **isschreib only** -Eigenschaft der Datei in true zu ändern.</span><span class="sxs-lookup"><span data-stu-id="207df-198">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="207df-199">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="207df-199">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="207df-200">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-200">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-201">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="207df-201">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="207df-202">Der **path** -Parameter gibt an, dass die ReadOnly.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="207df-202">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="207df-203">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="207df-203">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="207df-204">Die Ausgabe zeigt, dass die Datei nicht geschrieben wurde, weil der Zugriff verweigert wird.</span><span class="sxs-lookup"><span data-stu-id="207df-204">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="207df-205">Der **Force** -Parameter wird zum `Export-Csv` Cmdlet hinzugefügt, um den Export in die Datei zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="207df-205">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="207df-206">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-206">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="207df-207">Beispiel 9: Verwenden des Force-Parameters mit Append</span><span class="sxs-lookup"><span data-stu-id="207df-207">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="207df-208">In diesem Beispiel wird gezeigt, wie die **Force** -und **Append** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="207df-208">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="207df-209">Wenn diese Parameter kombiniert werden, können nicht übereinstimmende Objekteigenschaften in eine CSV-Datei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="207df-209">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

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

<span data-ttu-id="207df-210">Ein Ausdruck erstellt das **pscustomobject** mit den Eigenschaften " **Name** " und " **Version** ".</span><span class="sxs-lookup"><span data-stu-id="207df-210">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="207df-211">Die Werte werden in der `$Content` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="207df-211">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="207df-212">Die `$Content` Variable wird an das Cmdlet über die Pipeline gesendet `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="207df-212">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-213">`Export-Csv` verwendet den **path** -Parameter und speichert die ParmFile.csv Datei im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="207df-213">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="207df-214">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="207df-214">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="207df-215">Ein anderer Ausdruck erstellt ein **pscustomobject** mit den Eigenschaften **Name** und **Edition** .</span><span class="sxs-lookup"><span data-stu-id="207df-215">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="207df-216">Die Werte werden in der `$AdditionalContent` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="207df-216">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="207df-217">Die `$AdditionalContent` Variable wird an das Cmdlet über die Pipeline gesendet `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="207df-217">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="207df-218">Der **Append** -Parameter wird verwendet, um die Daten der Datei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="207df-218">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="207df-219">Der Anfüge Vorgang schlägt fehl, da der Eigenschaften Name zwischen **Version** und **Edition** nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="207df-219">The append fails because there is a property name mismatch between **Version** and **Edition**.</span></span>

<span data-ttu-id="207df-220">Der `Export-Csv` Cmdlet- **Force** -Parameter wird verwendet, um den Export zum Schreiben in die Datei zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="207df-220">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="207df-221">Die **Edition** -Eigenschaft wird verworfen.</span><span class="sxs-lookup"><span data-stu-id="207df-221">The **Edition** property is discarded.</span></span> <span data-ttu-id="207df-222">Das `Import-Csv` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="207df-222">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="207df-223">Beispiel 10: Exportieren nach CSV mit Anführungszeichen um zwei Spalten</span><span class="sxs-lookup"><span data-stu-id="207df-223">Example 10: Export to CSV with quotes around two columns</span></span>

<span data-ttu-id="207df-224">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="207df-224">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -QuoteFields "DateTime","Date" -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### <span data-ttu-id="207df-225">Beispiel 11: Exportieren in CSV nur bei Bedarf mit Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="207df-225">Example 11: Export to CSV with quotes only when needed</span></span>

<span data-ttu-id="207df-226">In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="207df-226">This example converts a **DateTime** object to a CSV string.</span></span>

```powershell
Get-Date | Export-Csv  -UseQuotes AsNeeded -Path .\FTDateTime.csv
Get-Content -Path .\FTDateTime.csv
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## <span data-ttu-id="207df-227">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="207df-227">PARAMETERS</span></span>

### <span data-ttu-id="207df-228">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="207df-228">-Append</span></span>

<span data-ttu-id="207df-229">Verwenden Sie diesen Parameter, um `Export-CSV` die CSV-Ausgabe am Ende der angegebenen Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="207df-229">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="207df-230">Ohne diesen Parameter `Export-CSV` ersetzt den Dateiinhalt ohne Warnung.</span><span class="sxs-lookup"><span data-stu-id="207df-230">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="207df-231">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="207df-231">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="207df-232">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="207df-232">-Delimiter</span></span>

<span data-ttu-id="207df-233">Gibt ein Trennzeichen zum Trennen der Eigenschaftswerte an.</span><span class="sxs-lookup"><span data-stu-id="207df-233">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="207df-234">Der Standardwert ist ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="207df-234">The default is a comma (`,`).</span></span> <span data-ttu-id="207df-235">Geben Sie ein Zeichen ein, z. b. einen Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="207df-235">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="207df-236">Um ein Semikolon ( `;` ) anzugeben, müssen Sie es in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="207df-236">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="207df-237">-Codierung</span><span class="sxs-lookup"><span data-stu-id="207df-237">-Encoding</span></span>

<span data-ttu-id="207df-238">Gibt die Codierung für die exportierte CSV-Datei an.</span><span class="sxs-lookup"><span data-stu-id="207df-238">Specifies the encoding for the exported CSV file.</span></span> <span data-ttu-id="207df-239">Der Standardwert ist `utf8NoBOM`.</span><span class="sxs-lookup"><span data-stu-id="207df-239">The default value is `utf8NoBOM`.</span></span>

<span data-ttu-id="207df-240">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="207df-240">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="207df-241">`ascii`: Verwendet die Codierung für den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="207df-241">`ascii`: Uses the encoding for the ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="207df-242">`bigendianunicode`: Codiert im UTF-16-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="207df-242">`bigendianunicode`: Encodes in UTF-16 format using the big-endian byte order.</span></span>
- <span data-ttu-id="207df-243">`bigendianutf32`: Codiert im UTF-32-Format unter Verwendung der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="207df-243">`bigendianutf32`: Encodes in UTF-32 format using the big-endian byte order.</span></span>
- <span data-ttu-id="207df-244">`oem`: Verwendet die Standard Codierung für MS-DOS-und-Konsolen Programme.</span><span class="sxs-lookup"><span data-stu-id="207df-244">`oem`: Uses the default encoding for MS-DOS and console programs.</span></span>
- <span data-ttu-id="207df-245">`unicode`: Codiert im UTF-16-Format unter Verwendung der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="207df-245">`unicode`: Encodes in UTF-16 format using the little-endian byte order.</span></span>
- <span data-ttu-id="207df-246">`utf7`: Codiert im UTF-7-Format.</span><span class="sxs-lookup"><span data-stu-id="207df-246">`utf7`: Encodes in UTF-7 format.</span></span>
- <span data-ttu-id="207df-247">`utf8`: Codiert im UTF-8-Format.</span><span class="sxs-lookup"><span data-stu-id="207df-247">`utf8`: Encodes in UTF-8 format.</span></span>
- <span data-ttu-id="207df-248">`utf8BOM`: Codiert im UTF-8-Format mit Byte Reihenfolge Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="207df-248">`utf8BOM`: Encodes in UTF-8 format with Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="207df-249">`utf8NoBOM`: Codiert im UTF-8-Format ohne Byte Reihenfolge-Markierung (BOM).</span><span class="sxs-lookup"><span data-stu-id="207df-249">`utf8NoBOM`: Encodes in UTF-8 format without Byte Order Mark (BOM)</span></span>
- <span data-ttu-id="207df-250">`utf32`: Codiert im UTF-32-Format.</span><span class="sxs-lookup"><span data-stu-id="207df-250">`utf32`: Encodes in UTF-32 format.</span></span>

<span data-ttu-id="207df-251">Ab PowerShell 6,2 ermöglicht der **Encoding** -Parameter auch numerische IDs registrierter Codepages (z `-Encoding 1251` . b.) oder Zeichen folgen Namen registrierter Codepages (z `-Encoding "windows-1251"` . b.).</span><span class="sxs-lookup"><span data-stu-id="207df-251">Beginning with PowerShell 6.2, the **Encoding** parameter also allows numeric IDs of registered code pages (like `-Encoding 1251`) or string names of registered code pages (like `-Encoding "windows-1251"`).</span></span> <span data-ttu-id="207df-252">Weitere Informationen finden Sie in der .NET-Dokumentation für [Encoding. Codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="207df-252">For more information, see the .NET documentation for [Encoding.CodePage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).</span></span>

> [!NOTE]
> <span data-ttu-id="207df-253">**UTF-7** _ wird nicht mehr für die Verwendung von empfohlen.</span><span class="sxs-lookup"><span data-stu-id="207df-253">**UTF-7** _ is no longer recommended to use.</span></span> <span data-ttu-id="207df-254">In PowerShell 7,1 wird eine Warnung geschrieben, wenn Sie `utf7` für den Parameter "_ \*Encoding\*\*" angeben.</span><span class="sxs-lookup"><span data-stu-id="207df-254">In PowerShell 7.1, a warning is written if you specify `utf7` for the _ *Encoding*\* parameter.</span></span>

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, BigEndianUTF32, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="207df-255">-Force</span><span class="sxs-lookup"><span data-stu-id="207df-255">-Force</span></span>

<span data-ttu-id="207df-256">Dieser Parameter ermöglicht das `Export-Csv` Überschreiben von Dateien mit dem **Read-Only** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="207df-256">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="207df-257">Wenn **Force** -und **Append** -Parameter kombiniert werden, können Objekte, die nicht übereinstimmende Eigenschaften enthalten, in eine CSV-Datei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="207df-257">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="207df-258">Nur die Eigenschaften, die mit verglichen werden, werden in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="207df-258">Only the properties that match are written to the file.</span></span> <span data-ttu-id="207df-259">Die nicht übereinstimmenden Eigenschaften werden verworfen.</span><span class="sxs-lookup"><span data-stu-id="207df-259">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="207df-260">-Includecotypeinformation</span><span class="sxs-lookup"><span data-stu-id="207df-260">-IncludeTypeInformation</span></span>

<span data-ttu-id="207df-261">Wenn dieser Parameter verwendet wird, enthält die erste Zeile der CSV-Ausgabe **#Type** gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="207df-261">When this parameter is used the first line of the CSV output contains **#TYPE** followed by the fully qualified name of the object type.</span></span> <span data-ttu-id="207df-262">#Type z. b. **System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="207df-262">For example, **#TYPE System.Diagnostics.Process**.</span></span>

<span data-ttu-id="207df-263">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="207df-263">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="207df-264">-InputObject</span><span class="sxs-lookup"><span data-stu-id="207df-264">-InputObject</span></span>

<span data-ttu-id="207df-265">Gibt die als CSV-Zeichenfolgen zu exportierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="207df-265">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="207df-266">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="207df-266">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="207df-267">Sie können Objekte auch über die Pipeline an übergeben `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="207df-267">You can also pipe objects to `Export-CSV`.</span></span>

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

### <span data-ttu-id="207df-268">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="207df-268">-LiteralPath</span></span>

<span data-ttu-id="207df-269">Gibt den Pfad zur CSV-Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="207df-269">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="207df-270">Im Gegensatz zu **Path** wird der Wert des **LiteralPath**-Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="207df-270">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="207df-271">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="207df-271">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="207df-272">Wenn der Pfad Escapezeichen enthält, verwenden Sie einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="207df-272">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="207df-273">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="207df-273">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="207df-274">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="207df-274">-NoClobber</span></span>

<span data-ttu-id="207df-275">Verwenden Sie diesen Parameter, damit `Export-CSV` eine vorhandene Datei nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="207df-275">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="207df-276">Wenn die Datei im angegebenen Pfad vorhanden ist, wird `Export-CSV` die Datei standardmäßig ohne Warnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="207df-276">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="207df-277">-Notypeinformation</span><span class="sxs-lookup"><span data-stu-id="207df-277">-NoTypeInformation</span></span>

<span data-ttu-id="207df-278">Entfernt den **#Type** Informations Header aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="207df-278">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="207df-279">Dieser Parameter wurde in PowerShell 6,0 zum Standard und ist aus Gründen der Abwärtskompatibilität eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="207df-279">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="207df-280">-Path</span><span class="sxs-lookup"><span data-stu-id="207df-280">-Path</span></span>

<span data-ttu-id="207df-281">Ein erforderlicher Parameter, der den Speicherort zum Speichern der CSV-Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="207df-281">A required parameter that specifies the location to save the CSV output file.</span></span>

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

### <span data-ttu-id="207df-282">-Useculture</span><span class="sxs-lookup"><span data-stu-id="207df-282">-UseCulture</span></span>

<span data-ttu-id="207df-283">Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="207df-283">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="207df-284">Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="207df-284">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="207df-285">-Confirm</span><span class="sxs-lookup"><span data-stu-id="207df-285">-Confirm</span></span>

<span data-ttu-id="207df-286">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="207df-286">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="207df-287">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="207df-287">-WhatIf</span></span>

<span data-ttu-id="207df-288">Verhindert, dass das Cmdlet verarbeitet wird oder Änderungen vornimmt.</span><span class="sxs-lookup"><span data-stu-id="207df-288">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="207df-289">Die Ausgabe zeigt, was geschieht, wenn das Cmdlet ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="207df-289">The output shows what would happen if the cmdlet were run.</span></span>

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

### <span data-ttu-id="207df-290">-Quotefields</span><span class="sxs-lookup"><span data-stu-id="207df-290">-QuoteFields</span></span>

<span data-ttu-id="207df-291">Gibt die Namen der Spalten an, die in Anführungszeichen eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="207df-291">Specifies the names of the columns that should be quoted.</span></span> <span data-ttu-id="207df-292">Wenn dieser Parameter verwendet wird, werden nur die angegebenen Spalten in Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="207df-292">When this parameter is used, only the specified columns are quoted.</span></span> <span data-ttu-id="207df-293">Dieser Parameter wurde in PowerShell 7,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="207df-293">This parameter was added in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="207df-294">-Usequotes</span><span class="sxs-lookup"><span data-stu-id="207df-294">-UseQuotes</span></span>

<span data-ttu-id="207df-295">Gibt an, wann Anführungszeichen in den CSV-Dateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="207df-295">Specifies when quotes are used in the CSV files.</span></span> <span data-ttu-id="207df-296">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="207df-296">Possible values are:</span></span>

- <span data-ttu-id="207df-297">Niemals etwas angeben</span><span class="sxs-lookup"><span data-stu-id="207df-297">Never - don't quote anything</span></span>
- <span data-ttu-id="207df-298">Alles immer angeben (Standardverhalten)</span><span class="sxs-lookup"><span data-stu-id="207df-298">Always - quote everything (default behavior)</span></span>
- <span data-ttu-id="207df-299">Asbedarf-nur Anführungszeichen Felder, die ein Trennzeichen enthalten</span><span class="sxs-lookup"><span data-stu-id="207df-299">AsNeeded - only quote fields that contain a delimiter character</span></span>

<span data-ttu-id="207df-300">Dieser Parameter wurde in PowerShell 7,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="207df-300">This parameter was added in PowerShell 7.0.</span></span>

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

### <span data-ttu-id="207df-301">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="207df-301">CommonParameters</span></span>

<span data-ttu-id="207df-302">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="207df-302">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="207df-303">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="207df-303">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="207df-304">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="207df-304">INPUTS</span></span>

### <span data-ttu-id="207df-305">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="207df-305">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="207df-306">Sie können jedes beliebige Objekt mit einem "ETS"-Adapter (Extended Type System) an über die Pipeline übergeben `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="207df-306">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="207df-307">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="207df-307">OUTPUTS</span></span>

### <span data-ttu-id="207df-308">System.String</span><span class="sxs-lookup"><span data-stu-id="207df-308">System.String</span></span>

<span data-ttu-id="207df-309">Die CSV-Liste wird an die im Path-Parameter festgelegte Datei gesendet.</span><span class="sxs-lookup"><span data-stu-id="207df-309">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="207df-310">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="207df-310">NOTES</span></span>

<span data-ttu-id="207df-311">Das `Export-CSV` -Cmdlet konvertiert die Objekte, die Sie in eine Reihe von CSV-Zeichen folgen übermitteln, und speichert Sie in der angegebenen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="207df-311">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="207df-312">Sie können verwenden `Export-CSV -IncludeTypeInformation` , um Objekte in einer CSV-Datei zu speichern. verwenden Sie dann das `Import-Csv` Cmdlet, um Objekte aus dem Text in der CSV-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="207df-312">You can use `Export-CSV -IncludeTypeInformation` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the text in the CSV file.</span></span>

<span data-ttu-id="207df-313">In der CSV-Datei wird jedes Objekt durch eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="207df-313">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="207df-314">Die Eigenschaftswerte werden mithilfe der Methode " **destring ()** " in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="207df-314">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="207df-315">Die Zeichen folgen werden durch den Namen des Eigenschafts Werts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="207df-315">The strings are represented by the property value name.</span></span> <span data-ttu-id="207df-316">`Export-CSV -IncludeTypeInformation` exportiert nicht die Methoden des-Objekts.</span><span class="sxs-lookup"><span data-stu-id="207df-316">`Export-CSV -IncludeTypeInformation` does not export the methods of the object.</span></span>

<span data-ttu-id="207df-317">Die CSV-Zeichen folgen werden wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="207df-317">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="207df-318">Wenn **includetypeinformation** verwendet wird, enthält die erste Zeichenfolge den **#Type** Informations Header, gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="207df-318">If **IncludeTypeInformation** is used, the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span>
  <span data-ttu-id="207df-319">#Type z. b. **System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="207df-319">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="207df-320">Wenn **include TypeInformation** nicht verwendet wird, enthält die erste Zeichenfolge die Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="207df-320">If **IncludeTypeInformation** is not used the first string includes the column headers.</span></span> <span data-ttu-id="207df-321">Die Header enthalten die Eigenschaftsnamen des ersten Objekts als durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="207df-321">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="207df-322">Die übrigen Zeichen folgen enthalten durch Trennzeichen getrennte Listen der Eigenschaftswerte jedes Objekts.</span><span class="sxs-lookup"><span data-stu-id="207df-322">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="207df-323">Ab PowerShell 6,0 ist das Standardverhalten von `Export-CSV` , wenn die **#Type** Informationen in das CSV nicht eingeschlossen werden und **notypeinformation** impliziert ist.</span><span class="sxs-lookup"><span data-stu-id="207df-323">Beginning with PowerShell 6.0 the default behavior of `Export-CSV` is to not include the **#TYPE** information in the CSV and **NoTypeInformation** is implied.</span></span> <span data-ttu-id="207df-324">**Includetypeinformation** kann verwendet werden, um die **#Type** Informationen einzuschließen und das Standardverhalten von `Export-CSV` vor PowerShell 6,0 zu emulieren.</span><span class="sxs-lookup"><span data-stu-id="207df-324">**IncludeTypeInformation** can be used to include the **#TYPE** Information and emulate the default behavior of `Export-CSV` prior to PowerShell 6.0.</span></span>

<span data-ttu-id="207df-325">Wenn Sie mehrere Objekte an senden `Export-CSV` , wird `Export-CSV` die Datei von basierend auf den Eigenschaften des ersten von Ihnen gesendeten Objekts organisiert.</span><span class="sxs-lookup"><span data-stu-id="207df-325">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="207df-326">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschaftswert dieses Objekts NULL, was durch zwei aufeinander folgende Kommas dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="207df-326">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="207df-327">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, sind diese Eigenschaftenwerte nicht in der Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="207df-327">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="207df-328">Sie können das `Import-Csv` Cmdlet verwenden, um Objekte aus den CSV-Zeichen folgen in den Dateien neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="207df-328">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="207df-329">Die resultierenden Objekte sind CSV-Versionen der ursprünglichen Objekte, die aus den Zeichenfolgendarstellungen der Eigenschaftswerte bestehen und die keine Methoden haben.</span><span class="sxs-lookup"><span data-stu-id="207df-329">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="207df-330">Die `ConvertTo-Csv` -und- `ConvertFrom-Csv` Cmdlets konvertieren Objekte in CSV-Zeichen folgen und aus CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="207df-330">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="207df-331">`Export-CSV` ist identisch `ConvertTo-CSV` mit, außer dass die CSV-Zeichen folgen in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="207df-331">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="207df-332">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="207df-332">RELATED LINKS</span></span>

[<span data-ttu-id="207df-333">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="207df-333">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="207df-334">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="207df-334">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="207df-335">Format-Table</span><span class="sxs-lookup"><span data-stu-id="207df-335">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="207df-336">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="207df-336">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="207df-337">Select-Object</span><span class="sxs-lookup"><span data-stu-id="207df-337">Select-Object</span></span>](Select-Object.md)
