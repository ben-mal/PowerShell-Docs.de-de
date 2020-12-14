---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: 17c3ef3046ba8f0cca9a85cf41aaf683212a58e9
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913340"
---
# <span data-ttu-id="8e80e-102">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="8e80e-102">Export-Csv</span></span>

## <span data-ttu-id="8e80e-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="8e80e-103">SYNOPSIS</span></span>
<span data-ttu-id="8e80e-104">Konvertiert-Objekte in eine Reihe von CSV-Zeichen folgen (Comma-Separated Value, Komma getrennte Werte) und speichert die Zeichen folgen in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="8e80e-104">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="8e80e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8e80e-105">SYNTAX</span></span>

### <span data-ttu-id="8e80e-106">Trennzeichen (Standard)</span><span class="sxs-lookup"><span data-stu-id="8e80e-106">Delimiter (Default)</span></span>

```
Export-Csv [[-Path] <string>] [[-Delimiter] <char>] -InputObject <psobject> [-LiteralPath <string>]
 [-Force] [-NoClobber] [-Encoding <string>] [-Append] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="8e80e-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="8e80e-107">UseCulture</span></span>

```
Export-Csv [[-Path] <string>] -InputObject <psobject> [-LiteralPath <string>] [-Force] [-NoClobber]
 [-Encoding <string>] [-Append] [-UseCulture] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="8e80e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8e80e-108">DESCRIPTION</span></span>

<span data-ttu-id="8e80e-109">Mit dem- `Export-CSV` Cmdlet wird eine CSV-Datei mit den von Ihnen übermittelten Objekten erstellt.</span><span class="sxs-lookup"><span data-stu-id="8e80e-109">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="8e80e-110">Jedes-Objekt ist eine Zeile, die eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts enthält.</span><span class="sxs-lookup"><span data-stu-id="8e80e-110">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="8e80e-111">Sie können das `Export-CSV` Cmdlet verwenden, um Tabellen zu erstellen und Daten für Programme freizugeben, die CSV-Dateien als Eingabe akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="8e80e-111">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="8e80e-112">Formatieren Sie Objekte nicht, bevor Sie Sie an das `Export-CSV` Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-112">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="8e80e-113">Wenn `Export-CSV` formatierte Objekte empfängt, enthält die CSV-Datei anstelle der Objekteigenschaften die Format Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8e80e-113">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="8e80e-114">Verwenden Sie das-Cmdlet, um nur ausgewählte Eigenschaften eines Objekts zu exportieren `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="8e80e-114">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="8e80e-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="8e80e-115">EXAMPLES</span></span>

### <span data-ttu-id="8e80e-116">Beispiel 1: Exportieren von Prozess Eigenschaften in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="8e80e-116">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="8e80e-117">In diesem Beispiel werden **Prozess** Objekte mit bestimmten Eigenschaften ausgewählt, die Objekte werden in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-117">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

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

<span data-ttu-id="8e80e-118">Mit dem- `Get-Process` Cmdlet werden die **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-118">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="8e80e-119">Mit dem **Name** -Parameter wird die Ausgabe so gefiltert, dass nur die wmiprvse-Prozess Objekte einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-119">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="8e80e-120">Die Prozess Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-120">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="8e80e-121">`Select-Object` verwendet den **Property** -Parameter, um eine Teilmenge der Prozess Objekteigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-121">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="8e80e-122">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-122">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-123">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-123">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="8e80e-124">Der **path** -Parameter gibt an, dass die WmiData.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-124">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="8e80e-125">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e80e-125">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="8e80e-126">Das `Import-Csv` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-126">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="8e80e-127">Beispiel 2: Exportieren von Prozessen in eine durch Trennzeichen getrennte Datei</span><span class="sxs-lookup"><span data-stu-id="8e80e-127">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="8e80e-128">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine CSV-Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-128">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="8e80e-129">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-129">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="8e80e-130">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-130">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-131">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-131">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="8e80e-132">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-132">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="8e80e-133">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e80e-133">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="8e80e-134">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-134">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="8e80e-135">Beispiel 3: Exportieren von Prozessen in eine durch Semikolons getrennte Datei</span><span class="sxs-lookup"><span data-stu-id="8e80e-135">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="8e80e-136">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine Datei mit einem Semikolon-Trennzeichen exportiert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-136">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="8e80e-137">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-137">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="8e80e-138">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-138">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-139">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-139">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="8e80e-140">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-140">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="8e80e-141">Mit dem **Delimiter** -Parameter wird ein Semikolon zum Trennen der Zeichen folgen Werte angegeben.</span><span class="sxs-lookup"><span data-stu-id="8e80e-141">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="8e80e-142">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e80e-142">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="8e80e-143">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-143">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="8e80e-144">Beispiel 4: Exportieren von Prozessen mit dem Listen Trennzeichen der aktuellen Kultur</span><span class="sxs-lookup"><span data-stu-id="8e80e-144">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="8e80e-145">In diesem Beispiel werden **Prozess** Objekte abgerufen und die Objekte in eine Datei exportiert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-145">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="8e80e-146">Das Trennzeichen ist das Listen Trennzeichen der aktuellen Kultur.</span><span class="sxs-lookup"><span data-stu-id="8e80e-146">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="8e80e-147">Das `Get-Culture` Cmdlet verwendet die genten Eigenschaften **TextInfo** und **ListSeparator** und zeigt das Standard Listen Trennzeichen der aktuellen Kultur an.</span><span class="sxs-lookup"><span data-stu-id="8e80e-147">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="8e80e-148">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-148">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="8e80e-149">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-149">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-150">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-150">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="8e80e-151">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-151">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="8e80e-152">Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur als Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-152">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="8e80e-153">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e80e-153">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="8e80e-154">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-154">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="8e80e-155">Beispiel 5: Exportieren von Prozessen mit Typinformationen</span><span class="sxs-lookup"><span data-stu-id="8e80e-155">Example 5: Export processes with type information</span></span>

<span data-ttu-id="8e80e-156">In diesem Beispiel wird erläutert, wie die **#Type** Header Informationen in eine CSV-Datei eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-156">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="8e80e-157">Der **#Type** -Header ist die Standardeinstellung in Versionen vor PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="8e80e-157">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="8e80e-158">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-158">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="8e80e-159">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-159">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-160">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-160">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="8e80e-161">Der **path** -Parameter gibt an, dass die Processes.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-161">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="8e80e-162">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-162">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="8e80e-163">Beispiel 6: Exportieren und Anfügen von Objekten an eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="8e80e-163">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="8e80e-164">In diesem Beispiel wird beschrieben, wie Objekte in eine CSV-Datei exportiert werden und wie der **Append** -Parameter zum Hinzufügen von Objekten zu einer vorhandenen Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-164">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

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

<span data-ttu-id="8e80e-165">Mit dem- `Get-Service` Cmdlet werden Dienst Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-165">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="8e80e-166">Der **DisplayName** -Parameter gibt Dienste zurück, die die Word-Anwendung enthalten.</span><span class="sxs-lookup"><span data-stu-id="8e80e-166">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="8e80e-167">Die Dienst Objekte werden über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-167">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="8e80e-168">`Select-Object` verwendet den **Property** -Parameter, um die Eigenschaften " **Display Name** " und " **Status** " anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8e80e-168">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="8e80e-169">Die- `$AppService` Variable speichert die-Objekte.</span><span class="sxs-lookup"><span data-stu-id="8e80e-169">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="8e80e-170">Die `$AppService` Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-170">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-171">`Export-Csv` Konvertiert die Dienst Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-171">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="8e80e-172">Der **path** -Parameter gibt an, dass die Services.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-172">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="8e80e-173">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e80e-173">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="8e80e-174">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-174">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="8e80e-175">Die `Get-Service` -und- `Select-Object` Cmdlets werden für Dienste wiederholt, die das Word-Fenster enthalten.</span><span class="sxs-lookup"><span data-stu-id="8e80e-175">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="8e80e-176">Die- `$WinService` Variable speichert die Dienst Objekte.</span><span class="sxs-lookup"><span data-stu-id="8e80e-176">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="8e80e-177">Das `Export-Csv` Cmdlet verwendet den **Append** -Parameter, um anzugeben, dass die `$WinService` Objekte der vorhandenen Services.csv Datei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-177">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="8e80e-178">Das `Get-Content` Cmdlet wird wiederholt, um die aktualisierte Datei mit den angefügten Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-178">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="8e80e-179">Beispiel 7: das Cmdlet "Format" in einer Pipeline erstellt unerwartete Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="8e80e-179">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="8e80e-180">Dieses Beispiel zeigt, warum es wichtig ist, ein Format-Cmdlet nicht in einer Pipeline zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-180">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="8e80e-181">Wenn eine unerwartete Ausgabe empfangen wird, beheben Sie die Probleme mit der Pipeline Syntax.</span><span class="sxs-lookup"><span data-stu-id="8e80e-181">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

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

<span data-ttu-id="8e80e-182">Mit dem- `Get-Date` Cmdlet wird das **DateTime** -Objekt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-182">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="8e80e-183">Das Objekt wird über die Pipeline an das `Select-Object` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-183">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="8e80e-184">`Select-Object` verwendet den **Property** -Parameter, um eine Teilmenge von Objekteigenschaften auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-184">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="8e80e-185">Das Objekt wird über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-185">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-186">`Export-Csv` Konvertiert das-Objekt in ein CSV-Format.</span><span class="sxs-lookup"><span data-stu-id="8e80e-186">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="8e80e-187">Der **path** -Parameter gibt an, dass die DateTime.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-187">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="8e80e-188">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e80e-188">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="8e80e-189">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die CSV-Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-189">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="8e80e-190">Wenn das `Format-Table` Cmdlet in der Pipeline verwendet wird, um Eigenschaften auszuwählen, werden unerwartete Ergebnisse empfangen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-190">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="8e80e-191">`Format-Table` sendet Tabellenformat Objekte über die Pipeline an das `Export-Csv` Cmdlet und nicht an das **DateTime** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="8e80e-191">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="8e80e-192">`Export-Csv` Konvertiert die Tabellenformat Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-192">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="8e80e-193">Das- `Get-Content` Cmdlet zeigt die CSV-Datei an, die die Tabellenformat Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="8e80e-193">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="8e80e-194">Beispiel 8: Verwenden des Force-Parameters, um schreibgeschützte Dateien zu überschreiben</span><span class="sxs-lookup"><span data-stu-id="8e80e-194">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="8e80e-195">In diesem Beispiel wird eine leere, schreibgeschützte Datei erstellt, und der **Force** -Parameter wird verwendet, um die Datei zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8e80e-195">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

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

<span data-ttu-id="8e80e-196">Das `New-Item` Cmdlet verwendet den **path** -Parameter und den **ItemType** -Parameter, um die ReadOnly.csv Datei im aktuellen Verzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-196">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="8e80e-197">Das `Set-ItemProperty` Cmdlet verwendet die Parameter **Name** und **value** , um die **isschreib only** -Eigenschaft der Datei in true zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8e80e-197">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="8e80e-198">Mit dem- `Get-Process` Cmdlet werden **Prozess** Objekte abgerufen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-198">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="8e80e-199">Die Prozess Objekte werden über die Pipeline an das `Export-Csv` Cmdlet gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-199">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-200">`Export-Csv` Konvertiert die Prozess Objekte in eine Reihe von CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-200">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="8e80e-201">Der **path** -Parameter gibt an, dass die ReadOnly.csv Datei im aktuellen Verzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-201">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="8e80e-202">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e80e-202">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="8e80e-203">Die Ausgabe zeigt, dass die Datei nicht geschrieben wurde, weil der Zugriff verweigert wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-203">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="8e80e-204">Der **Force** -Parameter wird zum `Export-Csv` Cmdlet hinzugefügt, um den Export in die Datei zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-204">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="8e80e-205">Das `Get-Content` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-205">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="8e80e-206">Beispiel 9: Verwenden des Force-Parameters mit Append</span><span class="sxs-lookup"><span data-stu-id="8e80e-206">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="8e80e-207">In diesem Beispiel wird gezeigt, wie die **Force** -und **Append** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-207">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="8e80e-208">Wenn diese Parameter kombiniert werden, können nicht übereinstimmende Objekteigenschaften in eine CSV-Datei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-208">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

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

<span data-ttu-id="8e80e-209">Ein Ausdruck erstellt das **pscustomobject** mit den Eigenschaften " **Name** " und " **Version** ".</span><span class="sxs-lookup"><span data-stu-id="8e80e-209">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="8e80e-210">Die Werte werden in der `$Content` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-210">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="8e80e-211">Die `$Content` Variable wird an das Cmdlet über die Pipeline gesendet `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="8e80e-211">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-212">`Export-Csv` verwendet den **path** -Parameter und speichert die ParmFile.csv Datei im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8e80e-212">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="8e80e-213">Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e80e-213">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="8e80e-214">Ein anderer Ausdruck erstellt ein **pscustomobject** mit den Eigenschaften **Name** und **Edition** .</span><span class="sxs-lookup"><span data-stu-id="8e80e-214">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="8e80e-215">Die Werte werden in der `$AdditionalContent` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-215">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="8e80e-216">Die `$AdditionalContent` Variable wird an das Cmdlet über die Pipeline gesendet `Export-Csv` .</span><span class="sxs-lookup"><span data-stu-id="8e80e-216">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="8e80e-217">Der **Append** -Parameter wird verwendet, um die Daten der Datei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-217">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="8e80e-218">Der Anfüge Vorgang schlägt fehl, da der Eigenschaften Name zwischen **Version** und **Edition** nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8e80e-218">The append fails because there is a property name mismatch between **Version** and **Edition**.</span></span>

<span data-ttu-id="8e80e-219">Der `Export-Csv` Cmdlet- **Force** -Parameter wird verwendet, um den Export zum Schreiben in die Datei zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-219">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="8e80e-220">Die **Edition** -Eigenschaft wird verworfen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-220">The **Edition** property is discarded.</span></span> <span data-ttu-id="8e80e-221">Das `Import-Csv` Cmdlet verwendet den **path** -Parameter, um die Datei im aktuellen Verzeichnis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-221">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

## <span data-ttu-id="8e80e-222">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8e80e-222">PARAMETERS</span></span>

### <span data-ttu-id="8e80e-223">-Anfügen</span><span class="sxs-lookup"><span data-stu-id="8e80e-223">-Append</span></span>

<span data-ttu-id="8e80e-224">Verwenden Sie diesen Parameter, um `Export-CSV` die CSV-Ausgabe am Ende der angegebenen Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-224">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="8e80e-225">Ohne diesen Parameter `Export-CSV` ersetzt den Dateiinhalt ohne Warnung.</span><span class="sxs-lookup"><span data-stu-id="8e80e-225">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="8e80e-226">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8e80e-226">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8e80e-227">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="8e80e-227">-Delimiter</span></span>

<span data-ttu-id="8e80e-228">Gibt ein Trennzeichen zum Trennen der Eigenschaftswerte an.</span><span class="sxs-lookup"><span data-stu-id="8e80e-228">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="8e80e-229">Der Standardwert ist ein Komma ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="8e80e-229">The default is a comma (`,`).</span></span> <span data-ttu-id="8e80e-230">Geben Sie ein Zeichen ein, z. b. einen Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="8e80e-230">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="8e80e-231">Um ein Semikolon ( `;` ) anzugeben, müssen Sie es in Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-231">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

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

### <span data-ttu-id="8e80e-232">-Codierung</span><span class="sxs-lookup"><span data-stu-id="8e80e-232">-Encoding</span></span>

<span data-ttu-id="8e80e-233">Gibt den Typ der Codierung für die Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="8e80e-233">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="8e80e-234">Der Standardwert ist `ASCII`.</span><span class="sxs-lookup"><span data-stu-id="8e80e-234">The default value is `ASCII`.</span></span>

<span data-ttu-id="8e80e-235">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8e80e-235">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="8e80e-236">`ASCII` Verwendet den ASCII-Zeichensatz (7-Bit).</span><span class="sxs-lookup"><span data-stu-id="8e80e-236">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="8e80e-237">`BigEndianUnicode` Verwendet UTF-16 mit der Big-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="8e80e-237">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="8e80e-238">`Default` Verwendet die Codierung, die der aktiven Codepage des Systems entspricht (normalerweise ANSI).</span><span class="sxs-lookup"><span data-stu-id="8e80e-238">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="8e80e-239">`OEM` Verwendet die Codierung, die der aktuellen OEM-Codepage des Systems entspricht.</span><span class="sxs-lookup"><span data-stu-id="8e80e-239">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="8e80e-240">`Unicode` Verwendet UTF-16 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="8e80e-240">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="8e80e-241">`UTF7` Verwendet UTF-7.</span><span class="sxs-lookup"><span data-stu-id="8e80e-241">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="8e80e-242">`UTF8` Verwendet UTF-8.</span><span class="sxs-lookup"><span data-stu-id="8e80e-242">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="8e80e-243">`UTF32` Verwendet UTF-32 mit der Little-Endian-Byte Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="8e80e-243">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

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

### <span data-ttu-id="8e80e-244">-Force</span><span class="sxs-lookup"><span data-stu-id="8e80e-244">-Force</span></span>

<span data-ttu-id="8e80e-245">Dieser Parameter ermöglicht das `Export-Csv` Überschreiben von Dateien mit dem **Read-Only** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="8e80e-245">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="8e80e-246">Wenn **Force** -und **Append** -Parameter kombiniert werden, können Objekte, die nicht übereinstimmende Eigenschaften enthalten, in eine CSV-Datei geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-246">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="8e80e-247">Nur die Eigenschaften, die mit verglichen werden, werden in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e80e-247">Only the properties that match are written to the file.</span></span> <span data-ttu-id="8e80e-248">Die nicht übereinstimmenden Eigenschaften werden verworfen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-248">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="8e80e-249">-InputObject</span><span class="sxs-lookup"><span data-stu-id="8e80e-249">-InputObject</span></span>

<span data-ttu-id="8e80e-250">Gibt die als CSV-Zeichenfolgen zu exportierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="8e80e-250">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="8e80e-251">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-251">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="8e80e-252">Sie können Objekte auch über die Pipeline an übergeben `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="8e80e-252">You can also pipe objects to `Export-CSV`.</span></span>

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

### <span data-ttu-id="8e80e-253">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="8e80e-253">-LiteralPath</span></span>

<span data-ttu-id="8e80e-254">Gibt den Pfad zur CSV-Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="8e80e-254">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="8e80e-255">Im Gegensatz zu **Path** wird der Wert des **LiteralPath**-Parameters genauso verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8e80e-255">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="8e80e-256">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-256">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="8e80e-257">Wenn der Pfad Escapezeichen enthält, verwenden Sie einfache Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-257">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="8e80e-258">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="8e80e-258">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="8e80e-259">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="8e80e-259">-NoClobber</span></span>

<span data-ttu-id="8e80e-260">Verwenden Sie diesen Parameter, damit `Export-CSV` eine vorhandene Datei nicht überschreibt.</span><span class="sxs-lookup"><span data-stu-id="8e80e-260">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="8e80e-261">Wenn die Datei im angegebenen Pfad vorhanden ist, wird `Export-CSV` die Datei standardmäßig ohne Warnung überschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e80e-261">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

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

### <span data-ttu-id="8e80e-262">-Notypeinformation</span><span class="sxs-lookup"><span data-stu-id="8e80e-262">-NoTypeInformation</span></span>

<span data-ttu-id="8e80e-263">Entfernt den **#Type** Informations Header aus der Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="8e80e-263">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="8e80e-264">Dieser Parameter wurde in PowerShell 6,0 zum Standard und ist aus Gründen der Abwärtskompatibilität eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-264">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

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

### <span data-ttu-id="8e80e-265">-Path</span><span class="sxs-lookup"><span data-stu-id="8e80e-265">-Path</span></span>

<span data-ttu-id="8e80e-266">Ein erforderlicher Parameter, der den Speicherort zum Speichern der CSV-Ausgabedatei angibt.</span><span class="sxs-lookup"><span data-stu-id="8e80e-266">A required parameter that specifies the location to save the CSV output file.</span></span>

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

### <span data-ttu-id="8e80e-267">-Useculture</span><span class="sxs-lookup"><span data-stu-id="8e80e-267">-UseCulture</span></span>

<span data-ttu-id="8e80e-268">Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-268">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="8e80e-269">Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .</span><span class="sxs-lookup"><span data-stu-id="8e80e-269">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

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

### <span data-ttu-id="8e80e-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8e80e-270">-Confirm</span></span>

<span data-ttu-id="8e80e-271">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8e80e-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8e80e-272">-WhatIf</span></span>

<span data-ttu-id="8e80e-273">Verhindert, dass das Cmdlet verarbeitet wird oder Änderungen vornimmt.</span><span class="sxs-lookup"><span data-stu-id="8e80e-273">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="8e80e-274">Die Ausgabe zeigt, was geschieht, wenn das Cmdlet ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="8e80e-274">The output shows what would happen if the cmdlet were run.</span></span>

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

### <span data-ttu-id="8e80e-275">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8e80e-275">CommonParameters</span></span>

<span data-ttu-id="8e80e-276">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8e80e-276">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8e80e-277">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8e80e-277">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8e80e-278">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="8e80e-278">INPUTS</span></span>

### <span data-ttu-id="8e80e-279">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="8e80e-279">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="8e80e-280">Sie können jedes beliebige Objekt mit einem "ETS"-Adapter (Extended Type System) an über die Pipeline übergeben `Export-CSV` .</span><span class="sxs-lookup"><span data-stu-id="8e80e-280">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="8e80e-281">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="8e80e-281">OUTPUTS</span></span>

### <span data-ttu-id="8e80e-282">System.String</span><span class="sxs-lookup"><span data-stu-id="8e80e-282">System.String</span></span>

<span data-ttu-id="8e80e-283">Die CSV-Liste wird an die im Path-Parameter festgelegte Datei gesendet.</span><span class="sxs-lookup"><span data-stu-id="8e80e-283">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="8e80e-284">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="8e80e-284">NOTES</span></span>

<span data-ttu-id="8e80e-285">Das `Export-CSV` -Cmdlet konvertiert die Objekte, die Sie in eine Reihe von CSV-Zeichen folgen übermitteln, und speichert Sie in der angegebenen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="8e80e-285">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="8e80e-286">Sie können verwenden `Export-CSV` , um Objekte in einer CSV-Datei zu speichern. verwenden Sie dann das `Import-Csv` Cmdlet, um Objekte aus der CSV-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-286">You can use `Export-CSV` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the CSV file.</span></span>

<span data-ttu-id="8e80e-287">In der CSV-Datei wird jedes Objekt durch eine durch Trennzeichen getrennte Liste der Eigenschaftswerte des Objekts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8e80e-287">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="8e80e-288">Die Eigenschaftswerte werden mithilfe der Methode " **destring ()** " in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-288">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="8e80e-289">Die Zeichen folgen werden durch den Namen des Eigenschafts Werts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8e80e-289">The strings are represented by the property value name.</span></span> <span data-ttu-id="8e80e-290">Export-CSV exportiert nicht die Methoden des Objekts.</span><span class="sxs-lookup"><span data-stu-id="8e80e-290">\`Export-CSV does not export the methods of the object.</span></span>

<span data-ttu-id="8e80e-291">Die CSV-Zeichen folgen werden wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="8e80e-291">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="8e80e-292">Standardmäßig enthält die erste Zeichenfolge den **#Type** Informations Header, gefolgt vom voll qualifizierten Namen des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="8e80e-292">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="8e80e-293">#Type z. b. **System. Diagnostics. Process**.</span><span class="sxs-lookup"><span data-stu-id="8e80e-293">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="8e80e-294">Wenn **notypeinformation** verwendet wird, enthält die erste Zeichenfolge die Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="8e80e-294">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="8e80e-295">Die Header enthalten die Eigenschaftsnamen des ersten Objekts als durch Trennzeichen getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="8e80e-295">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="8e80e-296">Die übrigen Zeichen folgen enthalten durch Trennzeichen getrennte Listen der Eigenschaftswerte jedes Objekts.</span><span class="sxs-lookup"><span data-stu-id="8e80e-296">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="8e80e-297">Wenn Sie mehrere Objekte an senden `Export-CSV` , wird `Export-CSV` die Datei von basierend auf den Eigenschaften des ersten von Ihnen gesendeten Objekts organisiert.</span><span class="sxs-lookup"><span data-stu-id="8e80e-297">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="8e80e-298">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschaftswert dieses Objekts NULL, was durch zwei aufeinander folgende Kommas dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8e80e-298">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="8e80e-299">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, sind diese Eigenschaftenwerte nicht in der Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="8e80e-299">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="8e80e-300">Sie können das `Import-Csv` Cmdlet verwenden, um Objekte aus den CSV-Zeichen folgen in den Dateien neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-300">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="8e80e-301">Die resultierenden Objekte sind CSV-Versionen der ursprünglichen Objekte, die aus den Zeichenfolgendarstellungen der Eigenschaftswerte bestehen und die keine Methoden haben.</span><span class="sxs-lookup"><span data-stu-id="8e80e-301">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="8e80e-302">Die `ConvertTo-Csv` -und- `ConvertFrom-Csv` Cmdlets konvertieren Objekte in CSV-Zeichen folgen und aus CSV-Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8e80e-302">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="8e80e-303">`Export-CSV` ist identisch `ConvertTo-CSV` mit, außer dass die CSV-Zeichen folgen in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8e80e-303">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="8e80e-304">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="8e80e-304">RELATED LINKS</span></span>

[<span data-ttu-id="8e80e-305">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="8e80e-305">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="8e80e-306">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="8e80e-306">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="8e80e-307">Format-Table</span><span class="sxs-lookup"><span data-stu-id="8e80e-307">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="8e80e-308">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="8e80e-308">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="8e80e-309">Select-Object</span><span class="sxs-lookup"><span data-stu-id="8e80e-309">Select-Object</span></span>](Select-Object.md)
