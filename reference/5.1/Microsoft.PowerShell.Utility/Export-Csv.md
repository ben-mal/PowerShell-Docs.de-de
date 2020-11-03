---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: 5a76f8ec454ad8144f193d8927f913b89a429fec
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214039"
---
# <span data-ttu-id="fef69-103">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="fef69-103">Export-Csv</span></span>

## <span data-ttu-id="fef69-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="fef69-104">SYNOPSIS</span></span>
<span data-ttu-id="fef69-105">Konvertiert-Objekte in eine Reihe von CSV-Zeichen folgen (Comma-Separated Value, Komma getrennte Werte) und speichert die Zeichen folgen in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="fef69-105">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="fef69-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fef69-106">SYNTAX</span></span>

### <span data-ttu-id="fef69-107">Trennzeichen (Standard)</span><span class="sxs-lookup"><span data-stu-id="fef69-107">Delimiter (Default)</span></span>

```
Export-Csv [[-Path] <string>] [[-Delimiter] <char>] -InputObject <psobject> [-LiteralPath <string>]
 [-Force] [-NoClobber] [-Encoding <string>] [-Append] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="fef69-108">UseCulture</span><span class="sxs-lookup"><span data-stu-id="fef69-108">UseCulture</span></span>

```
Export-Csv [[-Path] <string>] -InputObject <psobject> [-LiteralPath <string>] [-Force] [-NoClobber]
 [-Encoding <string>] [-Append] [-UseCulture] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="fef69-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fef69-109">DESCRIPTION</span></span>

<span data-ttu-id="fef69-110">Mit dem- `Export-CSV` Cmdlet wird eine CSV-Datei mit den von Ihnen übermittelten Objekten erstellt.</span><span class="sxs-lookup"><span data-stu-id="fef69-110">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="fef69-111">Jedes-Objekt ist eine Zeile, die eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts enthält.</span><span class="sxs-lookup"><span data-stu-id="fef69-111">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="fef69-112">Sie können das `Export-CSV` Cmdlet verwenden, um Tabellen zu erstellen und Daten für Programme freizugeben, die CSV-Dateien als Eingabe akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="fef69-112">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="fef69-113">Formatieren Sie Objekte nicht, bevor Sie Sie an das `Export-CSV` Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="fef69-113">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="fef69-114">Wenn `Export-CSV` formatierte Objekte empfängt, enthält die CSV-Datei anstelle der Objekteigenschaften die Format Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="fef69-114">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="fef69-115">Verwenden Sie das-Cmdlet, um nur ausgewählte Eigenschaften eines Objekts zu exportieren `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="fef69-115">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="fef69-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="fef69-116">EXAMPLES</span></span>

### <span data-ttu-id="fef69-117">Beispiel 1: Exportieren von Prozess Eigenschaften in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="fef69-117">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="fef69-118">In diesem Beispiel werden **Prozess** Objekte mit bestimmten Eigenschaften ausgewählt, die Objekte werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="fef69-118">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

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

<span data-ttu-id="fef69-119">Mit dem- `Get-Process` Cmdlet werden die **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fef69-119">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="fef69-120">Mit dem **Name** -Parameter wird die Ausgabe so gefiltert, dass nur die wmiprvse-Prozess Objekte einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="fef69-120">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="fef69-121">Die Prozess Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-121">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="fef69-122">`Select-Object` verwendet den **Property** -Parameter, um eine Teilmenge der Prozess Objekteigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="fef69-122">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="fef69-123">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-123">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-124">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fef69-124">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="fef69-125">Der **path** -Parameter gibt an, dass die WmiData.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-125">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="fef69-126">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fef69-126">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="fef69-127">Das `Import-Csv` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-127">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="fef69-128">Beispiel 2: Exportieren von Prozessen in eine durch Trennzeichen getrennte Datei</span><span class="sxs-lookup"><span data-stu-id="fef69-128">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="fef69-129">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="fef69-129">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="fef69-130">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fef69-130">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="fef69-131">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-131">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-132">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fef69-132">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="fef69-133">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-133">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="fef69-134">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fef69-134">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="fef69-135">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-135">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="fef69-136">Beispiel 3: Exportieren von Prozessen in eine durch Semikolons getrennte Datei</span><span class="sxs-lookup"><span data-stu-id="fef69-136">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="fef69-137">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine Datei mit einem Semikolon-Trennzeichen exportiert.</span><span class="sxs-lookup"><span data-stu-id="fef69-137">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="fef69-138">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fef69-138">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="fef69-139">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-139">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-140">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fef69-140">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="fef69-141">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-141">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="fef69-142">Mit dem **Delimiter** -Parameter wird ein Semikolon zum Trennen der Zeichen folgen Werte angegeben.</span><span class="sxs-lookup"><span data-stu-id="fef69-142">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="fef69-143">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fef69-143">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="fef69-144">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-144">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="fef69-145">Beispiel 4: Exportieren von Prozessen mit dem Listen Trennzeichen der aktuellen Kultur</span><span class="sxs-lookup"><span data-stu-id="fef69-145">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="fef69-146">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="fef69-146">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="fef69-147">Das Trennzeichen ist das Listen Trennzeichen der aktuellen Kultur.</span><span class="sxs-lookup"><span data-stu-id="fef69-147">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="fef69-148">Das `Get-Culture` Cmdlet verwendet die genten Eigenschaften **TextInfo** und **ListSeparator** und zeigt das Standard Listen Trennzeichen der aktuellen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="fef69-148">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="fef69-149">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fef69-149">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="fef69-150">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-150">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-151">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fef69-151">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="fef69-152">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-152">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="fef69-153">Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="fef69-153">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="fef69-154">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fef69-154">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="fef69-155">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-155">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="fef69-156">Beispiel 5: Exportieren von Prozessen mit Typinformationen</span><span class="sxs-lookup"><span data-stu-id="fef69-156">Example 5: Export processes with type information</span></span>

<span data-ttu-id="fef69-157">In diesem Beispiel wird erläutert, wie die **#Type** Header Informationen in eine CSV-Datei eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="fef69-157">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="fef69-158">Der **#Type** -Header ist die Standardeinstellung in Versionen vor PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="fef69-158">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="fef69-159">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fef69-159">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="fef69-160">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-160">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-161">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fef69-161">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="fef69-162">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-162">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="fef69-163">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-163">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="fef69-164">Beispiel 6: Exportieren und Anfügen von Objekten an eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="fef69-164">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="fef69-165">In diesem Beispiel wird beschrieben, wie Objekte in eine CSV-Datei exportiert werden und wie der **Append** -Parameter zum Hinzufügen von Objekten zu einer vorhandenen Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-165">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

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

<span data-ttu-id="fef69-166">Mit dem- `Get-Service` Cmdlet werden Dienst Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fef69-166">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="fef69-167">Der **DisplayName** -Parameter gibt Dienste zurück, die die Word-Anwendung enthalten.</span><span class="sxs-lookup"><span data-stu-id="fef69-167">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="fef69-168">Die Dienst Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-168">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="fef69-169">`Select-Object` verwendet den **Property** -Parameter, um die Eigenschaften " **Display Name** " und " **Status** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fef69-169">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="fef69-170">Die- `$AppService` Variable speichert die-Objekte.</span><span class="sxs-lookup"><span data-stu-id="fef69-170">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="fef69-171">Die `$AppService` Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-171">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-172">`Export-Csv` Konvertiert die Dienst Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fef69-172">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="fef69-173">Der **path** -Parameter gibt an, dass die Services.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-173">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="fef69-174">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fef69-174">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="fef69-175">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-175">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="fef69-176">Die `Get-Service` -und- `Select-Object` Cmdlets werden für Dienste wiederholt, die das Word-Fenster enthalten.</span><span class="sxs-lookup"><span data-stu-id="fef69-176">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="fef69-177">Die- `$WinService` Variable speichert die Dienst Objekte.</span><span class="sxs-lookup"><span data-stu-id="fef69-177">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="fef69-178">Das `Export-Csv` Cmdlet verwendet den **Append** -Parameter, um anzugeben, dass die `$WinService` Objekte der vorhandenen Services.csv Datei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fef69-178">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="fef69-179">Das `Get-Content` Cmdlet wird wiederholt, um die aktualisierte Datei mit den angefügten Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-179">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="fef69-180">Beispiel 7: das Cmdlet "Format" in einer Pipeline erstellt unerwartete Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="fef69-180">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="fef69-181">Dieses Beispiel zeigt, warum es wichtig ist, ein Format-Cmdlet nicht in einer Pipeline zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fef69-181">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="fef69-182">Wenn eine unerwartete Ausgabe empfangen wird, beheben Sie die Probleme mit der Pipeline Syntax.</span><span class="sxs-lookup"><span data-stu-id="fef69-182">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

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

<span data-ttu-id="fef69-183">Mit dem- `Get-Date` Cmdlet wird das **DateTime** -Objekt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fef69-183">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="fef69-184">Das Objekt wird über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-184">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="fef69-185">`Select-Object` verwendet den **Property** -Parameter, um eine Teilmenge von Objekteigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="fef69-185">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="fef69-186">Das Objekt wird über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-186">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-187">`Export-Csv` Konvertiert das-Objekt in ein CSV-Format.</span><span class="sxs-lookup"><span data-stu-id="fef69-187">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="fef69-188">Der **path** -Parameter gibt an, dass die DateTime.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-188">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="fef69-189">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fef69-189">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="fef69-190">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die CSV-Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-190">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="fef69-191">Wenn das `Format-Table` Cmdlet in der Pipeline verwendet wird, um Eigenschaften auszuwählen, werden unerwartete Ergebnisse empfangen.</span><span class="sxs-lookup"><span data-stu-id="fef69-191">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="fef69-192">`Format-Table` sendet Tabellenformat Objekte über die Pipeline an das `Export-Csv` Cmdlet und nicht an das **DateTime** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="fef69-192">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="fef69-193">`Export-Csv` Konvertiert die Tabellenformat Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fef69-193">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="fef69-194">Das- `Get-Content` Cmdlet zeigt die CSV-Datei an, die die Tabellenformat Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="fef69-194">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="fef69-195">Beispiel 8: Verwenden des Force-Parameters, um schreibgeschützte Dateien zu überschreiben</span><span class="sxs-lookup"><span data-stu-id="fef69-195">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="fef69-196">In diesem Beispiel wird eine leere, schreibgeschützte Datei erstellt, und der **Force** -Parameter wird verwendet, um die Datei zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fef69-196">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

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

<span data-ttu-id="fef69-197">Das `New-Item` Cmdlet verwendet den **path** -Parameter und den **ItemType** -Parameter, um die ReadOnly.csv Datei im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fef69-197">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="fef69-198">Das `Set-ItemProperty` Cmdlet verwendet die Parameter **Name** und **value** , um die **isschreib only** -Eigenschaft der Datei in true zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fef69-198">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="fef69-199">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fef69-199">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="fef69-200">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-200">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-201">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fef69-201">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="fef69-202">Der **path** -Parameter gibt an, dass die ReadOnly.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-202">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="fef69-203">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fef69-203">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="fef69-204">Die Ausgabe zeigt, dass die Datei nicht geschrieben wurde, weil der Zugriff verweigert wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-204">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="fef69-205">Der **Force** -Parameter wird zum `Export-Csv` Cmdlet hinzugefügt, um den Export in die Datei zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="fef69-205">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="fef69-206">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-206">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="fef69-207">Beispiel 9: Verwenden des Force-Parameters mit Append</span><span class="sxs-lookup"><span data-stu-id="fef69-207">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="fef69-208">In diesem Beispiel wird gezeigt, wie die **Force** -und **Append** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fef69-208">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="fef69-209">Wenn diese Parameter kombiniert werden, können nicht übereinstimmende Objekteigenschaften in eine CSV-Datei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fef69-209">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

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

<span data-ttu-id="fef69-210">Ein Ausdruck erstellt das **pscustomobject** mit den Eigenschaften " **Name** " und " **Version** ".</span><span class="sxs-lookup"><span data-stu-id="fef69-210">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="fef69-211">Die Werte werden in der `$Content` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fef69-211">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="fef69-212">Die `$Content` Variable wird an das Cmdlet über die Pipeline gesendet `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="fef69-212">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-213">`Export-Csv` verwendet den **path** -Parameter und speichert die ParmFile.csv Datei im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fef69-213">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="fef69-214">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fef69-214">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="fef69-215">Ein anderer Ausdruck erstellt ein **pscustomobject** mit den Eigenschaften **Name** und **Edition** .</span><span class="sxs-lookup"><span data-stu-id="fef69-215">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="fef69-216">Die Werte werden in der `$AdditionalContent` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fef69-216">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="fef69-217">Die `$AdditionalContent` Variable wird an das Cmdlet über die Pipeline gesendet `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="fef69-217">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="fef69-218">Der **Append** -Parameter wird verwendet, um die Daten der Datei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fef69-218">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="fef69-219">Der Anfüge Vorgang schlägt fehl, da der Eigenschaften Name zwischen **Version** und **Edition** nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fef69-219">The append fails because there is a property name mismatch between **Version** and **Edition** .</span></span>

<span data-ttu-id="fef69-220">Der `Export-Csv` Cmdlet- **Force** -Parameter wird verwendet, um den Export zum Schreiben in die Datei zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="fef69-220">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="fef69-221">Die **Edition** -Eigenschaft wird verworfen.</span><span class="sxs-lookup"><span data-stu-id="fef69-221">The **Edition** property is discarded.</span></span> <span data-ttu-id="fef69-222">Das `Import-Csv` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef69-222">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

## <span data-ttu-id="fef69-223">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fef69-223">PARAMETERS</span></span>

### <span data-ttu-id="fef69-224">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="fef69-224">-Append</span></span>

<span data-ttu-id="fef69-225">Verwenden Sie diesen Parameter, um `Export-CSV` die CSV-Ausgabe am Ende der angegebenen Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fef69-225">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="fef69-226">Ohne diesen Parameter `Export-CSV` ersetzt den Dateiinhalt ohne Warnung.</span><span class="sxs-lookup"><span data-stu-id="fef69-226">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="fef69-227">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fef69-227">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="fef69-228">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="fef69-228">-Delimiter</span></span>

<span data-ttu-id="fef69-229">Gibt ein Trennzeichen zum Trennen der Eigenschaftswerte an.</span><span class="sxs-lookup"><span data-stu-id="fef69-229">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="fef69-230">Der Standardwert ist ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="fef69-230">The default is a comma (`,`).</span></span> <span data-ttu-id="fef69-231">Geben Sie ein Zeichen ein, z. b. einen Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="fef69-231">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="fef69-232">Um ein Semikolon ( `;` ) anzugeben, müssen Sie es in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="fef69-232">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="fef69-233">-Codierung</span><span class="sxs-lookup"><span data-stu-id="fef69-233">-Encoding</span></span>

<span data-ttu-id="fef69-234">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="fef69-234">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="fef69-235">Der Standardwert ist `ASCII`.</span><span class="sxs-lookup"><span data-stu-id="fef69-235">The default value is `ASCII`.</span></span>

<span data-ttu-id="fef69-236">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fef69-236">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="fef69-237">`ASCII` Verwendet den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="fef69-237">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="fef69-238">`BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="fef69-238">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="fef69-239">`Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).</span><span class="sxs-lookup"><span data-stu-id="fef69-239">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="fef69-240">`OEM` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.</span><span class="sxs-lookup"><span data-stu-id="fef69-240">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="fef69-241">`Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="fef69-241">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="fef69-242">`UTF7` Verwendet UTF-7.</span><span class="sxs-lookup"><span data-stu-id="fef69-242">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="fef69-243">`UTF8` Verwendet UTF-8.</span><span class="sxs-lookup"><span data-stu-id="fef69-243">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="fef69-244">`UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="fef69-244">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fef69-245">-Force</span><span class="sxs-lookup"><span data-stu-id="fef69-245">-Force</span></span>

<span data-ttu-id="fef69-246">Dieser Parameter ermöglicht das `Export-Csv` Überschreiben von Dateien mit dem **Read-Only** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="fef69-246">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="fef69-247">Wenn **Force** -und **Append** -Parameter kombiniert werden, können Objekte, die nicht übereinstimmende Eigenschaften enthalten, in eine CSV-Datei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fef69-247">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="fef69-248">Nur die Eigenschaften, die mit verglichen werden, werden in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="fef69-248">Only the properties that match are written to the file.</span></span> <span data-ttu-id="fef69-249">Die nicht übereinstimmenden Eigenschaften werden verworfen.</span><span class="sxs-lookup"><span data-stu-id="fef69-249">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="fef69-250">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fef69-250">-InputObject</span></span>

<span data-ttu-id="fef69-251">Gibt die als CSV-Zeichenfolgen zu exportierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="fef69-251">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="fef69-252">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fef69-252">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="fef69-253">Sie können Objekte auch über die Pipeline an übergeben `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="fef69-253">You can also pipe objects to `Export-CSV`.</span></span>

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

### <span data-ttu-id="fef69-254">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="fef69-254">-LiteralPath</span></span>

<span data-ttu-id="fef69-255">Gibt den Pfad zur CSV-Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="fef69-255">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="fef69-256">Im Gegensatz zu **Path** wird der Wert des **LiteralPath** -Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="fef69-256">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="fef69-257">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="fef69-257">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="fef69-258">Wenn der Pfad Escapezeichen enthält, verwenden Sie einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="fef69-258">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="fef69-259">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="fef69-259">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fef69-260">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="fef69-260">-NoClobber</span></span>

<span data-ttu-id="fef69-261">Verwenden Sie diesen Parameter, damit `Export-CSV` eine vorhandene Datei nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="fef69-261">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="fef69-262">Wenn die Datei im angegebenen Pfad vorhanden ist, wird `Export-CSV` die Datei standardmäßig ohne Warnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="fef69-262">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="fef69-263">-Notypeinformation</span><span class="sxs-lookup"><span data-stu-id="fef69-263">-NoTypeInformation</span></span>

<span data-ttu-id="fef69-264">Entfernt den **#Type** Informations Header aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fef69-264">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="fef69-265">Dieser Parameter wurde in PowerShell 6,0 zum Standard und ist aus Gründen der Abwärtskompatibilität eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fef69-265">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="fef69-266">-Path</span><span class="sxs-lookup"><span data-stu-id="fef69-266">-Path</span></span>

<span data-ttu-id="fef69-267">Ein erforderlicher Parameter, der den Speicherort zum Speichern der CSV-Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="fef69-267">A required parameter that specifies the location to save the CSV output file.</span></span>

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

### <span data-ttu-id="fef69-268">-Useculture</span><span class="sxs-lookup"><span data-stu-id="fef69-268">-UseCulture</span></span>

<span data-ttu-id="fef69-269">Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="fef69-269">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="fef69-270">Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="fef69-270">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="fef69-271">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fef69-271">-Confirm</span></span>

<span data-ttu-id="fef69-272">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fef69-272">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fef69-273">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fef69-273">-WhatIf</span></span>

<span data-ttu-id="fef69-274">Verhindert, dass das Cmdlet verarbeitet wird oder Änderungen vornimmt.</span><span class="sxs-lookup"><span data-stu-id="fef69-274">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="fef69-275">Die Ausgabe zeigt, was geschieht, wenn das Cmdlet ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="fef69-275">The output shows what would happen if the cmdlet were run.</span></span>

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

### <span data-ttu-id="fef69-276">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fef69-276">CommonParameters</span></span>

<span data-ttu-id="fef69-277">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fef69-277">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fef69-278">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fef69-278">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fef69-279">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="fef69-279">INPUTS</span></span>

### <span data-ttu-id="fef69-280">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="fef69-280">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="fef69-281">Sie können jedes beliebige Objekt mit einem "ETS"-Adapter (Extended Type System) an über die Pipeline übergeben `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="fef69-281">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="fef69-282">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="fef69-282">OUTPUTS</span></span>

### <span data-ttu-id="fef69-283">System.String</span><span class="sxs-lookup"><span data-stu-id="fef69-283">System.String</span></span>

<span data-ttu-id="fef69-284">Die CSV-Liste wird an die im Path-Parameter festgelegte Datei gesendet.</span><span class="sxs-lookup"><span data-stu-id="fef69-284">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="fef69-285">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="fef69-285">NOTES</span></span>

<span data-ttu-id="fef69-286">Das `Export-CSV` -Cmdlet konvertiert die Objekte, die Sie in eine Reihe von CSV-Zeichen folgen übermitteln, und speichert Sie in der angegebenen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="fef69-286">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="fef69-287">Sie können verwenden `Export-CSV` , um Objekte in einer CSV-Datei zu speichern. verwenden Sie dann das `Import-Csv` Cmdlet, um Objekte aus der CSV-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fef69-287">You can use `Export-CSV` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the CSV file.</span></span>

<span data-ttu-id="fef69-288">In der CSV-Datei wird jedes Objekt durch eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fef69-288">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="fef69-289">Die Eigenschaftswerte werden mithilfe der Methode " **destring ()** " in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="fef69-289">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="fef69-290">Die Zeichen folgen werden durch den Namen des Eigenschafts Werts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fef69-290">The strings are represented by the property value name.</span></span> <span data-ttu-id="fef69-291">Export-CSV exportiert nicht die Methoden des Objekts.</span><span class="sxs-lookup"><span data-stu-id="fef69-291">\`Export-CSV does not export the methods of the object.</span></span>

<span data-ttu-id="fef69-292">Die CSV-Zeichen folgen werden wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="fef69-292">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="fef69-293">Standardmäßig enthält die erste Zeichenfolge den **#Type** Informations Header, gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="fef69-293">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="fef69-294">#Type z. b. **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="fef69-294">For example, **#TYPE System.Diagnostics.Process** .</span></span>
- <span data-ttu-id="fef69-295">Wenn **notypeinformation** verwendet wird, enthält die erste Zeichenfolge die Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="fef69-295">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="fef69-296">Die Header enthalten die Eigenschaftsnamen des ersten Objekts als durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="fef69-296">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="fef69-297">Die übrigen Zeichen folgen enthalten durch Trennzeichen getrennte Listen der Eigenschaftswerte jedes Objekts.</span><span class="sxs-lookup"><span data-stu-id="fef69-297">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="fef69-298">Wenn Sie mehrere Objekte an senden `Export-CSV` , wird `Export-CSV` die Datei von basierend auf den Eigenschaften des ersten von Ihnen gesendeten Objekts organisiert.</span><span class="sxs-lookup"><span data-stu-id="fef69-298">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="fef69-299">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschaftswert dieses Objekts NULL, was durch zwei aufeinander folgende Kommas dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fef69-299">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="fef69-300">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, sind diese Eigenschaftenwerte nicht in der Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="fef69-300">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="fef69-301">Sie können das `Import-Csv` Cmdlet verwenden, um Objekte aus den CSV-Zeichen folgen in den Dateien neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fef69-301">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="fef69-302">Die resultierenden Objekte sind CSV-Versionen der ursprünglichen Objekte, die aus den Zeichenfolgendarstellungen der Eigenschaftswerte bestehen und die keine Methoden haben.</span><span class="sxs-lookup"><span data-stu-id="fef69-302">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="fef69-303">Die `ConvertTo-Csv` -und- `ConvertFrom-Csv` Cmdlets konvertieren Objekte in CSV-Zeichen folgen und aus CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="fef69-303">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="fef69-304">`Export-CSV` ist identisch `ConvertTo-CSV` mit, außer dass die CSV-Zeichen folgen in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="fef69-304">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="fef69-305">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="fef69-305">RELATED LINKS</span></span>

[<span data-ttu-id="fef69-306">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="fef69-306">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="fef69-307">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="fef69-307">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="fef69-308">Format-Table</span><span class="sxs-lookup"><span data-stu-id="fef69-308">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="fef69-309">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="fef69-309">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="fef69-310">Select-Object</span><span class="sxs-lookup"><span data-stu-id="fef69-310">Select-Object</span></span>](Select-Object.md)
