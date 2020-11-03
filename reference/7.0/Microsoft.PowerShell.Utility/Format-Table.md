---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-table?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Table
ms.openlocfilehash: dc406be942cce50fea7d39cae705834353ff6941
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219367"
---
# <span data-ttu-id="1a16f-103">Format-Table</span><span class="sxs-lookup"><span data-stu-id="1a16f-103">Format-Table</span></span>

## <span data-ttu-id="1a16f-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1a16f-104">SYNOPSIS</span></span>
<span data-ttu-id="1a16f-105">Formatiert die Ausgabe als Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1a16f-105">Formats the output as a table.</span></span>

## <span data-ttu-id="1a16f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1a16f-106">SYNTAX</span></span>

### <span data-ttu-id="1a16f-107">Alle</span><span class="sxs-lookup"><span data-stu-id="1a16f-107">All</span></span>

```
Format-Table [-AutoSize] [-RepeatHeader] [-HideTableHeaders] [-Wrap] [[-Property] <Object[]>]
 [-GroupBy <Object>] [-View <String>] [-ShowError] [-DisplayError] [-Force] [-Expand <String>]
 [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="1a16f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1a16f-108">DESCRIPTION</span></span>

<span data-ttu-id="1a16f-109">Das- `Format-Table` Cmdlet formatiert die Ausgabe eines Befehls als Tabelle mit den ausgewählten Eigenschaften des Objekts in jeder Spalte.</span><span class="sxs-lookup"><span data-stu-id="1a16f-109">The `Format-Table` cmdlet formats the output of a command as a table with the selected properties of the object in each column.</span></span> <span data-ttu-id="1a16f-110">Der-Objekttyp bestimmt das Standardlayout und die Standardeigenschaften, die in den einzelnen Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-110">The object type determines the default layout and properties that are displayed in each column.</span></span> <span data-ttu-id="1a16f-111">Sie können den **Property** -Parameter verwenden, um die Eigenschaften auszuwählen, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="1a16f-111">You can use the **Property** parameter to select the properties that you want to display.</span></span>

<span data-ttu-id="1a16f-112">PowerShell verwendet Standardformatierer, um zu definieren, wie Objekttypen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-112">PowerShell uses default formatters to define how object types are displayed.</span></span> <span data-ttu-id="1a16f-113">Sie können `.ps1xml` Dateien verwenden, um benutzerdefinierte Ansichten zu erstellen, die eine Ausgabe Tabelle mit angegebenen Eigenschaften anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-113">You can use `.ps1xml` files to create custom views that display an output table with specified properties.</span></span> <span data-ttu-id="1a16f-114">Nachdem eine benutzerdefinierte Ansicht erstellt wurde, verwenden Sie den **View** -Parameter, um die Tabelle mit Ihrer benutzerdefinierten Ansicht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-114">After a custom view is created, use the **View** parameter to display the table with your custom view.</span></span> <span data-ttu-id="1a16f-115">Weitere Informationen zu Ansichten finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="1a16f-115">For more information about views, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="1a16f-116">Sie können eine Hash Tabelle verwenden, um einem Objekt berechnete Eigenschaften hinzuzufügen, bevor Sie Sie anzeigen und die Spaltenüberschriften in der Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="1a16f-116">You can use a hash table to add calculated properties to an object before displaying it and to specify the column headings in the table.</span></span> <span data-ttu-id="1a16f-117">Um eine berechnete Eigenschaft hinzuzufügen, verwenden Sie die **Eigenschaft** oder den **GroupBy** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1a16f-117">To add a calculated property, use the **Property** or **GroupBy** parameter.</span></span> <span data-ttu-id="1a16f-118">Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md) (Informationen zu Hashtabellen).</span><span class="sxs-lookup"><span data-stu-id="1a16f-118">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

## <span data-ttu-id="1a16f-119">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1a16f-119">EXAMPLES</span></span>

### <span data-ttu-id="1a16f-120">Beispiel 1: Formatieren eines PowerShell-Hosts</span><span class="sxs-lookup"><span data-stu-id="1a16f-120">Example 1: Format PowerShell host</span></span>

<span data-ttu-id="1a16f-121">In diesem Beispiel werden Informationen zum Host Programm für PowerShell in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a16f-121">This example displays information about the host program for PowerShell in a table.</span></span>

```powershell
Get-Host | Format-Table -AutoSize
```

<span data-ttu-id="1a16f-122">Mit dem- `Get-Host` Cmdlet werden **System. Management. Automation. Internal. Host. internalhost** -Objekte abgerufen, die den Host darstellen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-122">The `Get-Host` cmdlet gets **System.Management.Automation.Internal.Host.InternalHost** objects that represent the host.</span></span> <span data-ttu-id="1a16f-123">Die Objekte werden an die Pipeline gesendet `Format-Table` und in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a16f-123">The objects are sent down the pipeline to `Format-Table` and displayed in a table.</span></span> <span data-ttu-id="1a16f-124">Der **AutoSize** -Parameter passt die Spaltenbreite an, um das Abschneiden zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="1a16f-124">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

### <span data-ttu-id="1a16f-125">Beispiel 2: Formatieren von Prozessen nach BasePriority</span><span class="sxs-lookup"><span data-stu-id="1a16f-125">Example 2: Format processes by BasePriority</span></span>

<span data-ttu-id="1a16f-126">In diesem Beispiel werden Prozesse in Gruppen angezeigt, die dieselbe **BasePriority** -Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-126">In this example, processes are displayed in groups that have the same **BasePriority** property.</span></span>

```powershell
Get-Process | Sort-Object -Property BasePriority | Format-Table -GroupBy BasePriority -Wrap
```

<span data-ttu-id="1a16f-127">Das `Get-Process` -Cmdlet ruft Objekte ab, die jeden Prozess auf dem Computer darstellen, und sendet Sie an die Pipeline `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="1a16f-127">The `Get-Process` cmdlet gets objects that represent each process on the computer and sends them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="1a16f-128">Die Objekte werden in der Reihenfolge ihrer **BasePriority** -Eigenschaft sortiert.</span><span class="sxs-lookup"><span data-stu-id="1a16f-128">The objects are sorted in the order of their **BasePriority** property.</span></span>

<span data-ttu-id="1a16f-129">Die sortierten Objekte werden über die Pipeline an gesendet `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="1a16f-129">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="1a16f-130">Der **GroupBy** -Parameter ordnet die Prozessdaten basierend auf dem Wert Ihrer **BasePriority** -Eigenschaft in Gruppen an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-130">The **GroupBy** parameter arranges the process data into groups based on their **BasePriority** property's value.</span></span> <span data-ttu-id="1a16f-131">Mit dem **Wrap** -Parameter wird sichergestellt, dass keine Daten abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-131">The **Wrap** parameter ensures that data isn't truncated.</span></span>

### <span data-ttu-id="1a16f-132">Beispiel 3: Formatieren von Prozessen nach Startdatum</span><span class="sxs-lookup"><span data-stu-id="1a16f-132">Example 3: Format processes by start date</span></span>

<span data-ttu-id="1a16f-133">Dieses Beispiel zeigt Informationen zu den Prozessen, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-133">This example displays information about the processes running on the computer.</span></span> <span data-ttu-id="1a16f-134">Die Objekte werden sortiert und `Format-Table` verwenden eine Ansicht, um die Objekte nach Ihrem Startdatum zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="1a16f-134">The objects are sorted and `Format-Table` uses a view to group the objects by their start date.</span></span>

```powershell
Get-Process | Sort-Object StartTime | Format-Table -View StartTime
```

<span data-ttu-id="1a16f-135">`Get-Process` Ruft die **System. Diagnostics. Process** -Objekte ab, die die Prozesse darstellen, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-135">`Get-Process` gets the **System.Diagnostics.Process** objects that represent the processes running on the computer.</span></span> <span data-ttu-id="1a16f-136">Die Objekte werden über die Pipeline an gesendet `Sort-Object` und basierend auf der **StartTime** -Eigenschaft sortiert.</span><span class="sxs-lookup"><span data-stu-id="1a16f-136">The objects are sent down the pipeline to `Sort-Object`, and are sorted based on the **StartTime** property.</span></span>

<span data-ttu-id="1a16f-137">Die sortierten Objekte werden über die Pipeline an gesendet `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="1a16f-137">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="1a16f-138">Der **View** -Parameter gibt die **StartTime** -Ansicht an, die in der PowerShell- `DotNetTypes.format.ps1xml` Datei für **System. Diagnostics. Process** -Objekte definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1a16f-138">The **View** parameter specifies the **StartTime** view that's defined in the PowerShell `DotNetTypes.format.ps1xml` file for **System.Diagnostics.Process** objects.</span></span> <span data-ttu-id="1a16f-139">Die **StartTime** -Sicht konvertiert die Startzeit der einzelnen Prozesse in ein kurzes Datum und gruppiert dann die Prozesse nach dem Startdatum.</span><span class="sxs-lookup"><span data-stu-id="1a16f-139">The **StartTime** view converts each processes start time to a short date and then groups the processes by the start date.</span></span>

<span data-ttu-id="1a16f-140">Die `DotNetTypes.format.ps1xml` Datei enthält eine **Prioritäts** Ansicht für Prozesse.</span><span class="sxs-lookup"><span data-stu-id="1a16f-140">The `DotNetTypes.format.ps1xml` file contains a **Priority** view for processes.</span></span> <span data-ttu-id="1a16f-141">Sie können eigene `format.ps1xml` Dateien mit benutzerdefinierten Ansichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-141">You can create your own `format.ps1xml` files with customized views.</span></span>

### <span data-ttu-id="1a16f-142">Beispiel 4: Verwenden einer benutzerdefinierten Ansicht für die Tabellenausgabe</span><span class="sxs-lookup"><span data-stu-id="1a16f-142">Example 4: Use a custom view for table output</span></span>

<span data-ttu-id="1a16f-143">In diesem Beispiel zeigt eine benutzerdefinierte Ansicht den Inhalt eines Verzeichnisses an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-143">In this example, a custom view displays a directory's contents.</span></span> <span data-ttu-id="1a16f-144">Die benutzerdefinierte Ansicht fügt der Tabellenausgabe für **System. IO. directeryinfo** -und **System. IO. FileInfo** -Objekte, die von erstellt werden, die Spalte " **Spalte** " hinzu `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="1a16f-144">The custom view adds the **CreationTime** column to the table output for **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span>

<span data-ttu-id="1a16f-145">Die benutzerdefinierte Ansicht in diesem Beispiel wurde aus der Ansicht erstellt, die im PowerShell-Quellcode definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1a16f-145">The custom view in this example was created from the view defined in PowerShell source code.</span></span> <span data-ttu-id="1a16f-146">Weitere Informationen zu Ansichten und zum Code, der zum Erstellen der Ansicht dieses Beispiels verwendet wird, finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).</span><span class="sxs-lookup"><span data-stu-id="1a16f-146">For more information about views and the code used to create this example's view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).</span></span>

```powershell
Get-ChildItem  -Path C:\Test | Format-Table -View mygciview
```

```Output
    Directory: C:\Test

Mode                LastWriteTime              CreationTime         Length Name
----                -------------              ------------         ------ ----
d-----        11/4/2019     15:54       9/24/2019     15:54                Archives
d-----        8/27/2019     14:22       8/27/2019     14:22                Drawings
d-----       10/23/2019     09:38       2/25/2019     09:38                Files
-a----        11/7/2019     11:07       11/7/2019     11:07          11345 Alias.txt
-a----        2/27/2019     15:15       2/27/2019     15:15            258 alias_out.txt
-a----        2/27/2019     15:16       2/27/2019     15:16            258 alias_out2.txt
```

<span data-ttu-id="1a16f-147">`Get-ChildItem` Ruft den Inhalt des aktuellen Verzeichnisses ab `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="1a16f-147">`Get-ChildItem` gets the contents of the current directory, `C:\Test`.</span></span> <span data-ttu-id="1a16f-148">Die Objekte " **System. IO. Director yinfo** " und " **System. IO. FileInfo** " werden über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="1a16f-148">The **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects are sent down the pipeline.</span></span>
<span data-ttu-id="1a16f-149">`Format-Table` verwendet den **View** -Parameter, um die benutzerdefinierte Ansicht **mygciview** anzugeben, die die Spalte " **kreationtime** " enthält.</span><span class="sxs-lookup"><span data-stu-id="1a16f-149">`Format-Table` uses the **View** parameter to specify the custom view **mygciview** that includes the **CreationTime** column.</span></span>

<span data-ttu-id="1a16f-150">Die Standard `Format-Table` Ausgabe für `Get-ChildItem` enthält nicht die Spalte "up **time** ".</span><span class="sxs-lookup"><span data-stu-id="1a16f-150">The default `Format-Table` output for `Get-ChildItem` doesn't include the **CreationTime** column.</span></span>

### <span data-ttu-id="1a16f-151">Beispiel 5: Verwenden von Eigenschaften für die Tabellenausgabe</span><span class="sxs-lookup"><span data-stu-id="1a16f-151">Example 5: Use properties for table output</span></span>

<span data-ttu-id="1a16f-152">In diesem Beispiel wird der **Property** -Parameter verwendet, um alle Computerdienste in einer Tabelle mit zwei Spalten anzuzeigen, in der die Eigenschaften **Name** und **DependentServices** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-152">This example uses the **Property** parameter to display all the computer's services in a two-column table that shows the properties **Name** and **DependentServices**.</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="1a16f-153">`Get-Service` Ruft alle Dienste auf dem Computer ab und sendet die **System. ServiceProcess. ServiceController** -Objekte über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="1a16f-153">`Get-Service` gets all the services on the computer and sends the **System.ServiceProcess.ServiceController** objects down the pipeline.</span></span> <span data-ttu-id="1a16f-154">`Format-Table` verwendet den **Property** -Parameter, um anzugeben, dass die Eigenschaften **Name** und **DependentServices** in der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-154">`Format-Table` uses the **Property** parameter to specify that the **Name** and **DependentServices** properties are displayed in the table.</span></span>

<span data-ttu-id="1a16f-155">**Name** und **DependentServices** sind zwei der Eigenschaften des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="1a16f-155">**Name** and **DependentServices** are two of the object type's properties.</span></span> <span data-ttu-id="1a16f-156">Um alle Eigenschaften anzuzeigen: `Get-Service | Get-Member -MemberType Properties` .</span><span class="sxs-lookup"><span data-stu-id="1a16f-156">To view all the properties: `Get-Service | Get-Member -MemberType Properties`.</span></span>

### <span data-ttu-id="1a16f-157">Beispiel 6: Formatieren eines Prozesses und Berechnen der Lauf Zeit</span><span class="sxs-lookup"><span data-stu-id="1a16f-157">Example 6: Format a process and calculate its running time</span></span>

<span data-ttu-id="1a16f-158">In diesem Beispiel wird eine Tabelle mit dem Prozessnamen und der Gesamtlaufzeit für die **Editor** -Prozesse des lokalen Computers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a16f-158">This example displays a table with the process name and total running time for the local computer's **notepad** processes.</span></span> <span data-ttu-id="1a16f-159">Die Gesamtausführungszeit wird durch Subtrahieren der Startzeit der einzelnen Prozesses von der aktuellen Zeit berechnet.</span><span class="sxs-lookup"><span data-stu-id="1a16f-159">The total running time is calculated by subtracting the start time of each process from the current time.</span></span>

```powershell
Get-Process notepad |
  Format-Table ProcessName, @{Label="TotalRunningTime"; Expression={(Get-Date) - $_.StartTime}}
```

```Output
ProcessName TotalRunningTime
----------- ----------------
notepad     03:20:00.2751767
notepad     00:00:16.7710520
```

<span data-ttu-id="1a16f-160">`Get-Process` Ruft alle **Editor** -Prozesse des lokalen Computers ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="1a16f-160">`Get-Process` gets all the local computer's **notepad** processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="1a16f-161">`Format-Table` zeigt eine Tabelle mit zwei Spalten an: **ProcessName** , eine `Get-Process` Eigenschaft und **totalrunningtime** , eine berechnete Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1a16f-161">`Format-Table` displays a table with two columns: **ProcessName** , a `Get-Process` property, and **TotalRunningTime** , a calculated property.</span></span>

<span data-ttu-id="1a16f-162">Die **totalrunningtime** -Eigenschaft wird durch eine Hash Tabelle mit zwei Schlüsseln, **Bezeichnung** und **Ausdruck** , angegeben.</span><span class="sxs-lookup"><span data-stu-id="1a16f-162">The **TotalRunningTime** property is specified by a hash table with two keys, **Label** and **Expression**.</span></span> <span data-ttu-id="1a16f-163">Die **Bezeichnung Key gibt den Namen** der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-163">The **Label** key specifies the property name.</span></span> <span data-ttu-id="1a16f-164">Der **Ausdrucks** Schlüssel gibt die Berechnung an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-164">The **Expression** key specifies the calculation.</span></span> <span data-ttu-id="1a16f-165">Der Ausdruck ruft die **StartTime** -Eigenschaft jedes Prozess Objekts ab und subtrahiert Sie vom Ergebnis eines- `Get-Date` Befehls, der das aktuelle Datum und die Uhrzeit abruft.</span><span class="sxs-lookup"><span data-stu-id="1a16f-165">The expression gets the **StartTime** property of each process object and subtracts it from the result of a `Get-Date` command, which gets the current date and time.</span></span>

### <span data-ttu-id="1a16f-166">Beispiel 7: Formatieren von Notepad-Prozessen</span><span class="sxs-lookup"><span data-stu-id="1a16f-166">Example 7: Format Notepad processes</span></span>

<span data-ttu-id="1a16f-167">In diesem Beispiel wird verwendet `Get-CimInstance` , um die Lauf Zeit für alle **Editor** -Prozesse auf dem lokalen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1a16f-167">This example uses `Get-CimInstance` to get the running time for all **notepad** processes on the local computer.</span></span> <span data-ttu-id="1a16f-168">Sie können `Get-CimInstance` mit dem **Computername** -Parameter verwenden, um Informationen von Remote Computern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1a16f-168">You can use `Get-CimInstance` with the **ComputerName** parameter to get information from remote computers.</span></span>

```powershell
$Processes = Get-CimInstance -Class win32_process -Filter "name='notepad.exe'"
$Processes | Format-Table ProcessName, @{ Label = "Total Running Time"; Expression={(Get-Date) - $_.CreationDate}}
```

```Output
ProcessName Total Running Time
----------- ------------------
notepad.exe 03:39:39.6260693
notepad.exe 00:19:56.1376922
```

<span data-ttu-id="1a16f-169">`Get-CimInstance` Ruft Instanzen der WMI- **Win32_Process** Klasse ab, die alle Prozesse des lokalen Computers mit dem Namen **notepad.exe** beschreibt.</span><span class="sxs-lookup"><span data-stu-id="1a16f-169">`Get-CimInstance` gets instances of the WMI **Win32_Process** class that describes all the local computer's processes named **notepad.exe**.</span></span> <span data-ttu-id="1a16f-170">Die Prozess Objekte werden in der `$Processes` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1a16f-170">The process objects are stored in the `$Processes` variable.</span></span>

<span data-ttu-id="1a16f-171">Die Prozess Objekte in der `$Processes` Variablen werden über die Pipeline an gesendet `Format-Table` , wodurch die **ProcessName** -Eigenschaft und eine neue berechnete Eigenschaft, **Gesamtlaufzeit** , angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-171">The process objects in the `$Processes` variable are sent down the pipeline to `Format-Table`, which displays the **ProcessName** property and a new calculated property, **Total Running Time**.</span></span>

<span data-ttu-id="1a16f-172">Der Befehl weist den Namen der neuen berechneten Eigenschaft ( **gesamte Lauf Zeit** ) dem Bezeichnungs **Schlüssel zu** .</span><span class="sxs-lookup"><span data-stu-id="1a16f-172">The command assigns the name of the new calculated property, **Total Running Time** , to the **Label** key.</span></span> <span data-ttu-id="1a16f-173">Der Skriptblock des **Ausdrucks** Schlüssels berechnet, wie lange der Prozess ausgeführt wurde, indem er das Erstellungsdatum des Prozesses vom aktuellen Datum subtrahieren konnte.</span><span class="sxs-lookup"><span data-stu-id="1a16f-173">The **Expression** key's script block calculates how long the process has been running by subtracting the processes creation date from the current date.</span></span> <span data-ttu-id="1a16f-174">Das- `Get-Date` Cmdlet ruft das aktuelle Datum ab.</span><span class="sxs-lookup"><span data-stu-id="1a16f-174">The `Get-Date` cmdlet gets the current date.</span></span> <span data-ttu-id="1a16f-175">Das Erstellungsdatum wird vom aktuellen Datum subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="1a16f-175">The creation date is subtracted from the current date.</span></span> <span data-ttu-id="1a16f-176">Das Ergebnis ist der Wert der **gesamten Laufzeit**.</span><span class="sxs-lookup"><span data-stu-id="1a16f-176">The result is the value of **Total Running Time**.</span></span>

### <span data-ttu-id="1a16f-177">Beispiel 8: Problembehandlung bei Format Fehlern</span><span class="sxs-lookup"><span data-stu-id="1a16f-177">Example 8: Troubleshooting format errors</span></span>

<span data-ttu-id="1a16f-178">Die folgenden Beispiele zeigen die Ergebnisse des Hinzufügens der **displayerror** -oder **ShowError** -Parameter mit einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1a16f-178">The following examples show the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -DisplayError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday #ERR
```

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -ShowError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday

InvalidArgument: Failed to evaluate expression " $_ / $null ".
```

## <span data-ttu-id="1a16f-179">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1a16f-179">PARAMETERS</span></span>

### <span data-ttu-id="1a16f-180">-AutoSize</span><span class="sxs-lookup"><span data-stu-id="1a16f-180">-AutoSize</span></span>

<span data-ttu-id="1a16f-181">Gibt an, dass das Cmdlet die Spaltengröße und die Anzahl der Spalten basierend auf der Breite der Daten anpasst.</span><span class="sxs-lookup"><span data-stu-id="1a16f-181">Indicates that the cmdlet adjusts the column size and number of columns based on the width of the data.</span></span> <span data-ttu-id="1a16f-182">Standardmäßig werden die Spaltengröße und die Anzahl von der Ansicht bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1a16f-182">By default, the column size and number are determined by the view.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-183">-Display Error</span><span class="sxs-lookup"><span data-stu-id="1a16f-183">-DisplayError</span></span>

<span data-ttu-id="1a16f-184">Gibt an, dass das Cmdlet Fehler in der Befehlszeile anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1a16f-184">Indicates that the cmdlet displays errors on the command line.</span></span> <span data-ttu-id="1a16f-185">Dieser Parameter kann als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Table` und Probleme beheben müssen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-185">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-186">-Erweitern</span><span class="sxs-lookup"><span data-stu-id="1a16f-186">-Expand</span></span>

<span data-ttu-id="1a16f-187">Gibt das Format des Auflistungs Objekts und die Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-187">Specifies the format of the collection object and the objects in the collection.</span></span> <span data-ttu-id="1a16f-188">Dieser Parameter dient zum Formatieren von Objekten, die die [ICollection](/dotnet/api/system.collections.icollection) ([System. Collections](/dotnet/api/system.collections))-Schnittstelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-188">This parameter is designed to format objects that support the [ICollection](/dotnet/api/system.collections.icollection) ([System.Collections](/dotnet/api/system.collections)) interface.</span></span> <span data-ttu-id="1a16f-189">Der Standardwert ist " **enumonly** ".</span><span class="sxs-lookup"><span data-stu-id="1a16f-189">The default value is **EnumOnly**.</span></span>
<span data-ttu-id="1a16f-190">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1a16f-190">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="1a16f-191">**Enumonly** : zeigt die Eigenschaften der Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-191">**EnumOnly** : Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="1a16f-192">**Coreonly** : zeigt die Eigenschaften des Auflistungs Objekts an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-192">**CoreOnly** : Displays the properties of the collection object.</span></span>
- <span data-ttu-id="1a16f-193">**Beides** : zeigt die Eigenschaften des Auflistungs Objekts und die Eigenschaften von Objekten in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-193">**Both** : Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-194">-Force</span><span class="sxs-lookup"><span data-stu-id="1a16f-194">-Force</span></span>

<span data-ttu-id="1a16f-195">Gibt an, dass das Cmdlet das Cmdlet anweist, alle Fehlerinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-195">Indicates that the cmdlet directs the cmdlet to display all the error information.</span></span> <span data-ttu-id="1a16f-196">Verwenden Sie mit dem **Display Error** -Parameter oder **ShowError** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1a16f-196">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="1a16f-197">Wenn ein Fehlerobjekt in die Fehler- oder Anzeigedatenströme geschrieben wird, werden standardmäßig nur einige der Fehlerinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a16f-197">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-198">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="1a16f-198">-GroupBy</span></span>

<span data-ttu-id="1a16f-199">Gibt die sortierte Ausgabe basierend auf einem Eigenschafts Wert in separaten Tabellen an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-199">Specifies sorted output in separate tables based on a property value.</span></span> <span data-ttu-id="1a16f-200">Sie können z. b. **GroupBy** verwenden, um Dienste basierend auf Ihrem Status in separaten Tabellen aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="1a16f-200">For example, you can use **GroupBy** to list services in separate tables based on their status.</span></span>

<span data-ttu-id="1a16f-201">Geben Sie einen Ausdruck oder eine Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="1a16f-201">Enter an expression or a property.</span></span> <span data-ttu-id="1a16f-202">Der **GroupBy** -Parameter erwartet, dass die Objekte sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-202">The **GroupBy** parameter expects that the objects are sorted.</span></span>
<span data-ttu-id="1a16f-203">Verwenden Sie das- `Sort-Object` Cmdlet `Format-Table` , bevor Sie zum Gruppieren der Objekte verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-203">Use the `Sort-Object` cmdlet before using `Format-Table` to group the objects.</span></span>

<span data-ttu-id="1a16f-204">Der Wert des **GroupBy** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="1a16f-204">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="1a16f-205">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="1a16f-205">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="1a16f-206">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="1a16f-206">Valid key-value pairs are:</span></span>

- <span data-ttu-id="1a16f-207">Name (oder Bezeichnung)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="1a16f-207">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="1a16f-208">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="1a16f-208">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="1a16f-209">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="1a16f-209">FormatString - `<string>`</span></span>

<span data-ttu-id="1a16f-210">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="1a16f-210">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-211">-Hidetableheaders</span><span class="sxs-lookup"><span data-stu-id="1a16f-211">-HideTableHeaders</span></span>

<span data-ttu-id="1a16f-212">Lässt die Spaltenüberschriften in der Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="1a16f-212">Omits the column headings from the table.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-213">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1a16f-213">-InputObject</span></span>

<span data-ttu-id="1a16f-214">Gibt die zu formatierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="1a16f-214">Specifies the objects to format.</span></span> <span data-ttu-id="1a16f-215">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-215">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-216">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1a16f-216">-Property</span></span>

<span data-ttu-id="1a16f-217">Gibt die in der Anzeige angezeigten Objekteigenschaften und die Reihenfolge an, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-217">Specifies the object properties that appear in the display and the order in which they appear.</span></span> <span data-ttu-id="1a16f-218">Geben Sie einen oder mehrere Eigenschaftsnamen ein, die durch Kommas getrennt sind, oder verwenden Sie eine Hash Tabelle, um eine berechnete Eigenschaft anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-218">Type one or more property names, separated by commas, or use a hash table to display a calculated property.</span></span> <span data-ttu-id="1a16f-219">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1a16f-219">Wildcards are permitted.</span></span>

<span data-ttu-id="1a16f-220">Wenn Sie diesen Parameter weglassen, hängen die Eigenschaften, die in der Anzeige angezeigt werden, von den Eigenschaften des ersten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="1a16f-220">If you omit this parameter, the properties that appear in the display depend on the first object's properties.</span></span> <span data-ttu-id="1a16f-221">Wenn das erste Objekt beispielsweise **PropertyA** und **propertyb** aufweist, die nachfolgenden Objekte jedoch **PropertyA** , **propertyb** und **propertyc** aufweisen, werden nur die **PropertyA** -und **propertyb** -Header angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a16f-221">For example, if the first object has **PropertyA** and **PropertyB** but subsequent objects have **PropertyA** , **PropertyB** , and **PropertyC** , then only the **PropertyA** and **PropertyB** headers will display.</span></span>

<span data-ttu-id="1a16f-222">Der **Property** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="1a16f-222">The **Property** parameter is optional.</span></span> <span data-ttu-id="1a16f-223">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-223">You can't use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="1a16f-224">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="1a16f-224">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="1a16f-225">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="1a16f-225">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="1a16f-226">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="1a16f-226">Valid key-value pairs are:</span></span>

- <span data-ttu-id="1a16f-227">Name (oder Bezeichnung) `<string>`</span><span class="sxs-lookup"><span data-stu-id="1a16f-227">Name (or Label) `<string>`</span></span>
- <span data-ttu-id="1a16f-228">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="1a16f-228">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="1a16f-229">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="1a16f-229">FormatString - `<string>`</span></span>
- <span data-ttu-id="1a16f-230">Width- `<int32>` -muss größer sein als `0`</span><span class="sxs-lookup"><span data-stu-id="1a16f-230">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="1a16f-231">Der Ausrichtungs Wert kann `Left` , `Center` oder sein. `Right`</span><span class="sxs-lookup"><span data-stu-id="1a16f-231">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="1a16f-232">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="1a16f-232">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1a16f-233">-Repeatheiader</span><span class="sxs-lookup"><span data-stu-id="1a16f-233">-RepeatHeader</span></span>

<span data-ttu-id="1a16f-234">Wiederholt, wenn der Header einer Tabelle nach jedem Vollbild angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1a16f-234">Repeats displaying the header of a table after every screen full.</span></span> <span data-ttu-id="1a16f-235">Der wiederholte Header ist nützlich, wenn die Ausgabe an einen Pager wie oder weitergeleitet wird, z `less` `more` . b. oder mit einer Bildschirm Sprachausgabe.</span><span class="sxs-lookup"><span data-stu-id="1a16f-235">The repeated header is useful when the output is piped to a pager such as `less` or `more` or paging with a screen reader.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-236">-ShowError</span><span class="sxs-lookup"><span data-stu-id="1a16f-236">-ShowError</span></span>

<span data-ttu-id="1a16f-237">Dieser Parameter sendet Fehler über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="1a16f-237">This parameter sends errors through the pipeline.</span></span> <span data-ttu-id="1a16f-238">Dieser Parameter kann als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Table` und Probleme beheben müssen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-238">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-239">-Ansicht</span><span class="sxs-lookup"><span data-stu-id="1a16f-239">-View</span></span>

<span data-ttu-id="1a16f-240">Ab PowerShell 6 werden die Standardansichten im PowerShell-Quellcode definiert `C#` .</span><span class="sxs-lookup"><span data-stu-id="1a16f-240">Beginning in PowerShell 6, the default views are defined in PowerShell `C#` source code.</span></span> <span data-ttu-id="1a16f-241">Die `*.format.ps1xml` Dateien aus PowerShell 5,1 und früheren Versionen sind in PowerShell 6 und höheren Versionen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-241">The `*.format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later versions.</span></span>

<span data-ttu-id="1a16f-242">Mit dem **View** -Parameter können Sie ein alternatives Format oder eine benutzerdefinierte Ansicht für die Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="1a16f-242">The **View** parameter lets you specify an alternate format or custom view for the table.</span></span> <span data-ttu-id="1a16f-243">Sie können die PowerShell-Standard Sichten verwenden oder benutzerdefinierte Ansichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-243">You can use the default PowerShell views or create custom views.</span></span> <span data-ttu-id="1a16f-244">Weitere Informationen zum Erstellen einer benutzerdefinierten Ansicht finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="1a16f-244">For more information about how to create a custom view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="1a16f-245">Die Alternative und die benutzerdefinierten Ansichten für den **View** -Parameter müssen das Tabellenformat verwenden, andernfalls `Format-Table` schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="1a16f-245">The alternate and custom views for the **View** parameter must use the table format, otherwise, `Format-Table` fails.</span></span> <span data-ttu-id="1a16f-246">Wenn die Alternative Ansicht eine Liste ist, verwenden Sie das- `Format-List` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a16f-246">If the alternate view is a list, use the `Format-List` cmdlet.</span></span> <span data-ttu-id="1a16f-247">Wenn die Alternative Ansicht weder eine Liste noch eine Tabelle ist, verwenden Sie das- `Format-Custom` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a16f-247">If the alternate view isn't a list or a table, use the `Format-Custom` cmdlet.</span></span>

<span data-ttu-id="1a16f-248">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a16f-248">You can't use the **Property** and **View** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-249">-Wrap</span><span class="sxs-lookup"><span data-stu-id="1a16f-249">-Wrap</span></span>

<span data-ttu-id="1a16f-250">Zeigt Text an, der die Spaltenbreite in der nächsten Zeile überschreitet.</span><span class="sxs-lookup"><span data-stu-id="1a16f-250">Displays text that exceeds the column width on the next line.</span></span> <span data-ttu-id="1a16f-251">Standardmäßig wird Text, der die Spaltenbreite überschreitet, abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="1a16f-251">By default, text that exceeds the column width is truncated.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1a16f-252">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1a16f-252">CommonParameters</span></span>

<span data-ttu-id="1a16f-253">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1a16f-253">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1a16f-254">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1a16f-254">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1a16f-255">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1a16f-255">INPUTS</span></span>

### <span data-ttu-id="1a16f-256">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="1a16f-256">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1a16f-257">Sie können jedes beliebige Objekt über die Pipeline an senden `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="1a16f-257">You can send any object down the pipeline to `Format-Table`.</span></span>

## <span data-ttu-id="1a16f-258">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1a16f-258">OUTPUTS</span></span>

### <span data-ttu-id="1a16f-259">Microsoft. PowerShell. Commands. Internal. Format</span><span class="sxs-lookup"><span data-stu-id="1a16f-259">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="1a16f-260">`Format-Table` gibt Format Objekte zurück, die die Tabelle darstellen.</span><span class="sxs-lookup"><span data-stu-id="1a16f-260">`Format-Table` returns format objects that represent the table.</span></span>

## <span data-ttu-id="1a16f-261">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1a16f-261">NOTES</span></span>

## <span data-ttu-id="1a16f-262">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1a16f-262">RELATED LINKS</span></span>

[<span data-ttu-id="1a16f-263">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="1a16f-263">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="1a16f-264">about_Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="1a16f-264">about_Format.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="1a16f-265">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="1a16f-265">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="1a16f-266">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="1a16f-266">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="1a16f-267">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="1a16f-267">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="1a16f-268">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="1a16f-268">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="1a16f-269">Format-List</span><span class="sxs-lookup"><span data-stu-id="1a16f-269">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="1a16f-270">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="1a16f-270">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="1a16f-271">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="1a16f-271">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="1a16f-272">Get-Member</span><span class="sxs-lookup"><span data-stu-id="1a16f-272">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="1a16f-273">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="1a16f-273">Get-CimInstance</span></span>](../CimCmdlets/Get-CimInstance.md)

[<span data-ttu-id="1a16f-274">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="1a16f-274">Update-FormatData</span></span>](Update-FormatData.md)
