---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-html?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Html
ms.openlocfilehash: ffe7fe7c44258435c7ec9ddd2bab9ebeb9f6c465
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601718"
---
# <span data-ttu-id="75947-102">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="75947-102">ConvertTo-Html</span></span>

## <span data-ttu-id="75947-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="75947-103">SYNOPSIS</span></span>
<span data-ttu-id="75947-104">Konvertiert .NET-Objekte in HTML, die in einem Webbrowser angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="75947-104">Converts .NET objects into HTML that can be displayed in a Web browser.</span></span>

## <span data-ttu-id="75947-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="75947-105">SYNTAX</span></span>

### <span data-ttu-id="75947-106">Seite (Standard)</span><span class="sxs-lookup"><span data-stu-id="75947-106">Page (Default)</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [[-Body] <String[]>]
 [[-Head] <String[]>] [[-Title] <String>] [-As <String>] [-CssUri <Uri>] [-PostContent <String[]>]
 [-PreContent <String[]>] [-Meta <Hashtable>] [-Charset <String>] [-Transitional]
 [<CommonParameters>]
```

### <span data-ttu-id="75947-107">Fragment</span><span class="sxs-lookup"><span data-stu-id="75947-107">Fragment</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [-As <String>] [-Fragment]
 [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="75947-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="75947-108">DESCRIPTION</span></span>

<span data-ttu-id="75947-109">Das- `ConvertTo-Html` Cmdlet konvertiert .NET-Objekte in HTML, die in einem Webbrowser angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="75947-109">The `ConvertTo-Html` cmdlet converts .NET objects into HTML that can be displayed in a Web browser.</span></span> <span data-ttu-id="75947-110">Sie können dieses Cmdlet verwenden, um die Ausgabe eines Befehls auf einer Webseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="75947-110">You can use this cmdlet to display the output of a command in a Web page.</span></span>

<span data-ttu-id="75947-111">Sie können die Parameter von verwenden `ConvertTo-Html` , um Objekteigenschaften auszuwählen, ein Tabellen-oder Listenformat anzugeben, den Titel der HTML-Seite anzugeben, Text vor und nach dem Objekt hinzuzufügen und nur das Tabellen-oder Listen Fragment anstelle einer Strict DTD-Seite zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="75947-111">You can use the parameters of `ConvertTo-Html` to select object properties, to specify a table or list format, to specify the HTML page title, to add text before and after the object, and to return only the table or list fragment, instead of a strict DTD page.</span></span>

<span data-ttu-id="75947-112">Wenn Sie mehrere Objekte an senden `ConvertTo-Html` , erstellt PowerShell die Tabelle (oder Liste) auf Grundlage der Eigenschaften des ersten Objekts, das Sie übermitteln.</span><span class="sxs-lookup"><span data-stu-id="75947-112">When you submit multiple objects to `ConvertTo-Html`, PowerShell creates the table (or list) based on the properties of the first object that you submit.</span></span> <span data-ttu-id="75947-113">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschaftenwert dieses Objekts eine leere Zelle.</span><span class="sxs-lookup"><span data-stu-id="75947-113">If the remaining objects do not have one of the specified properties, the property value of that object is an empty cell.</span></span> <span data-ttu-id="75947-114">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, sind diese Eigenschaftenwerte nicht in der Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="75947-114">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

## <span data-ttu-id="75947-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="75947-115">EXAMPLES</span></span>

### <span data-ttu-id="75947-116">Beispiel 1: Erstellen einer Webseite zum Anzeigen des Datums</span><span class="sxs-lookup"><span data-stu-id="75947-116">Example 1: Create a web page to display the date</span></span>

```powershell
ConvertTo-Html -InputObject (Get-Date)
```

<span data-ttu-id="75947-117">Dieser Befehl erstellt eine HTML-Seite, die die Eigenschaften des aktuellen Datums anzeigt.</span><span class="sxs-lookup"><span data-stu-id="75947-117">This command creates an HTML page that displays the properties of the current date.</span></span> <span data-ttu-id="75947-118">Er verwendet den **Inputobject** -Parameter, um die Ergebnisse eines `Get-Date` Befehls an das `ConvertTo-Html` Cmdlet zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="75947-118">It uses the **InputObject** parameter to submit the results of a `Get-Date` command to the `ConvertTo-Html` cmdlet.</span></span>

### <span data-ttu-id="75947-119">Beispiel 2: Erstellen einer Webseite zum Anzeigen von PowerShell-Aliasen</span><span class="sxs-lookup"><span data-stu-id="75947-119">Example 2: Create a web page to display PowerShell aliases</span></span>

```powershell
Get-Alias | ConvertTo-Html | Out-File aliases.htm
Invoke-Item aliases.htm
```

<span data-ttu-id="75947-120">Dieser Befehl erstellt eine HTML-Seite, auf der die PowerShell-Aliase in der aktuellen Konsole aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="75947-120">This command creates an HTML page that lists the PowerShell aliases in the current console.</span></span>

<span data-ttu-id="75947-121">Der Befehl verwendet das `Get-Alias` Cmdlet, um die Aliase zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="75947-121">The command uses the `Get-Alias` cmdlet to get the aliases.</span></span> <span data-ttu-id="75947-122">Der Pipeline Operator ( `|` ) wird verwendet, um die Aliase an das `ConvertTo-Html` Cmdlet zu senden, das die HTML-Seite erstellt.</span><span class="sxs-lookup"><span data-stu-id="75947-122">It uses the pipeline operator (`|`) to send the aliases to the `ConvertTo-Html` cmdlet, which creates the HTML page.</span></span> <span data-ttu-id="75947-123">Der Befehl verwendet auch das `Out-File` Cmdlet, um den HTML-Code an die Datei zu senden `aliases.htm` .</span><span class="sxs-lookup"><span data-stu-id="75947-123">The command also uses the `Out-File` cmdlet to send the HTML code to the `aliases.htm` file.</span></span>

### <span data-ttu-id="75947-124">Beispiel 3: Erstellen einer Webseite zum Anzeigen von PowerShell-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="75947-124">Example 3: Create a web page to display PowerShell events</span></span>

```powershell
`Get-EventLog` -LogName "Windows PowerShell" | ConvertTo-Html | Out-File pslog.htm
```

<span data-ttu-id="75947-125">Dieser Befehl erstellt eine HTML-Seite mit `pslog.htm` dem Namen, auf der die Ereignisse im Windows PowerShell-Ereignisprotokoll auf dem lokalen Computer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75947-125">This command creates an HTML page called `pslog.htm` that displays the events in the Windows PowerShell event log on the local computer.</span></span>

<span data-ttu-id="75947-126">Er verwendet das `Get-EventLog` Cmdlet, um die Ereignisse im Windows PowerShell-Protokoll zu erhalten, und verwendet dann den Pipeline Operator ( `|` ), um die Ereignisse an das `ConvertTo-Html` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="75947-126">It uses the `Get-EventLog` cmdlet to get the events in the Windows PowerShell log and then uses the pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="75947-127">Der Befehl verwendet auch das `Out-File` Cmdlet, um den HTML-Code an die Datei zu senden `pslog.htm` .</span><span class="sxs-lookup"><span data-stu-id="75947-127">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

<span data-ttu-id="75947-128">Der Befehl verwendet auch das `Out-File` Cmdlet, um den HTML-Code an die Datei zu senden `pslog.htm` .</span><span class="sxs-lookup"><span data-stu-id="75947-128">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

### <span data-ttu-id="75947-129">Beispiel 4: Erstellen einer Webseite zum Anzeigen von Prozessen</span><span class="sxs-lookup"><span data-stu-id="75947-129">Example 4: Create a web page to display processes</span></span>

```powershell
Get-Process |
  ConvertTo-Html -Property Name, Path, Company -Title "Process Information" |
    Out-File proc.htm
Invoke-Item proc.htm
```

<span data-ttu-id="75947-130">Diese Befehle erstellen und öffnen eine HTML-Seite, die den Namen, Pfad und das Unternehmen der Prozesse auf dem lokalen Computer auflistet.</span><span class="sxs-lookup"><span data-stu-id="75947-130">These commands create and open an HTML page that lists the name, path, and company of the processes on the local computer.</span></span>

<span data-ttu-id="75947-131">Der erste Befehl verwendet das `Get-Process` Cmdlet, um Objekte zu erhalten, die die Prozesse darstellen, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="75947-131">The first command uses the `Get-Process` cmdlet to get objects that represent the processes running on the computer.</span></span> <span data-ttu-id="75947-132">Der Befehl verwendet den Pipeline Operator ( `|` ), um die Prozess Objekte an das `ConvertTo-Html` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="75947-132">The command uses the pipeline operator (`|`) to send the process objects to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="75947-133">Der Befehl verwendet den **Property** -Parameter, um drei Eigenschaften der Process-Objekte auszuwählen, die in die Tabelle eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="75947-133">The command uses the **Property** parameter to select three properties of the process objects to be included in the table.</span></span> <span data-ttu-id="75947-134">Der Befehl verwendet den **Title** -Parameter, um einen Titel für die HTML-Seite anzugeben.</span><span class="sxs-lookup"><span data-stu-id="75947-134">The command uses the **Title** parameter to specify a title for the HTML page.</span></span> <span data-ttu-id="75947-135">Der Befehl verwendet auch das `Out-File` Cmdlet, um das resultierende HTML an eine Datei mit dem Namen Proc.htm zu senden.</span><span class="sxs-lookup"><span data-stu-id="75947-135">The command also uses the `Out-File` cmdlet to send the resulting HTML to a file named Proc.htm.</span></span>

<span data-ttu-id="75947-136">Der zweite Befehl verwendet das `Invoke-Item` Cmdlet, um `Proc.htm` im Standardbrowser zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="75947-136">The second command uses the `Invoke-Item` cmdlet to open the `Proc.htm` in the default browser.</span></span>

### <span data-ttu-id="75947-137">Beispiel 5: Erstellen einer Webseite zum Anzeigen von Dienst Objekten</span><span class="sxs-lookup"><span data-stu-id="75947-137">Example 5: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -CssUri "test.css"
```

```Output
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"  "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html>
<head>
<title>HTML TABLE</title>
<link rel="stylesheet" type="text/css" href="test.css" />
...
```

<span data-ttu-id="75947-138">Dieser Befehl erstellt eine HTML-Seite der Dienst Objekte, die vom `Get-Service` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="75947-138">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="75947-139">Der Befehl verwendet den **cssuri** -Parameter, um ein Cascading Stylesheet für die HTML-Seite anzugeben.</span><span class="sxs-lookup"><span data-stu-id="75947-139">The command uses the **CssUri** parameter to specify a cascading style sheet for the HTML page.</span></span>

<span data-ttu-id="75947-140">Der **cssuri** -Parameter fügt dem resultierenden HTML-Code ein zusätzliches `<link rel="stylesheet" type="text/css" href="test.css">` Tag hinzu.</span><span class="sxs-lookup"><span data-stu-id="75947-140">The **CssUri** parameter adds an additional `<link rel="stylesheet" type="text/css" href="test.css">` tag to the resulting HTML.</span></span> <span data-ttu-id="75947-141">Das HREF-Attribut im Tag enthält den Namen des Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="75947-141">The HREF attribute in the tag contains the name of the style sheet.</span></span>

### <span data-ttu-id="75947-142">Beispiel 6: Erstellen einer Webseite zum Anzeigen von Dienst Objekten</span><span class="sxs-lookup"><span data-stu-id="75947-142">Example 6: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -As LIST | Out-File services.htm
```

<span data-ttu-id="75947-143">Dieser Befehl erstellt eine HTML-Seite der Dienst Objekte, die vom `Get-Service` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="75947-143">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="75947-144">Der Befehl verwendet den **As** -Parameter, um ein Listenformat anzugeben.</span><span class="sxs-lookup"><span data-stu-id="75947-144">The command uses the **As** parameter to specify a list format.</span></span> <span data-ttu-id="75947-145">Das-Cmdlet `Out-File` sendet das resultierende HTML an die `Services.htm` Datei.</span><span class="sxs-lookup"><span data-stu-id="75947-145">The cmdlet `Out-File` sends the resulting HTML to the `Services.htm` file.</span></span>

### <span data-ttu-id="75947-146">Beispiel 7: Erstellen einer Webtabelle für das aktuelle Datum</span><span class="sxs-lookup"><span data-stu-id="75947-146">Example 7: Create a web table for the current date</span></span>

```powershell
Get-Date | ConvertTo-Html -Fragment
```

```Output
<table>
<colgroup>...</colgroup>
<tr><th>DisplayHint</th><th>DateTime</th><th>Date</th><th>Day</th><th>DayOfWeek</th><th>DayOfYear</th><th>Hour</th>
<th>Kind</th><th>Millisecond</th><th>Minute</th><th>Month</th><th>Second</th><th>Ticks</th><th>TimeOfDay</th><th>Year</th></tr>
<tr><td>DateTime</td><td>Monday, May 05, 2008 10:40:04 AM</td><td>5/5/2008 12:00:00 AM</td><td>5</td><td>Monday</td>
<td>126</td><td>10</td><td>Local</td><td>123</td><td>40</td><td>5</td><td>4</td><td>633455808041237213</td><td>10:40:04.12
37213</td><td>2008</td></tr>
</table>
```

<span data-ttu-id="75947-147">Dieser Befehl verwendet `ConvertTo-Html` , um eine HTML-Tabelle des aktuellen Datums zu generieren.</span><span class="sxs-lookup"><span data-stu-id="75947-147">This command uses `ConvertTo-Html` to generate an HTML table of the current date.</span></span> <span data-ttu-id="75947-148">Der Befehl verwendet das `Get-Date` Cmdlet, um das aktuelle Datum zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="75947-148">The command uses the `Get-Date` cmdlet to get the current date.</span></span> <span data-ttu-id="75947-149">Er verwendet einen Pipeline Operator (|), um die Ergebnisse an das `ConvertTo-Html` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="75947-149">It uses a pipeline operator (|) to send the results to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="75947-150">Der- `ConvertTo-Html` Befehl enthält den **Fragment** -Parameter, der die Ausgabe auf eine HTML-Tabelle beschränkt.</span><span class="sxs-lookup"><span data-stu-id="75947-150">The `ConvertTo-Html` command includes the **Fragment** parameter, which limits the output to an HTML table.</span></span> <span data-ttu-id="75947-151">Daher werden die anderen Elemente einer HTML-Seite wie die `<HEAD>`- und `<BODY>`-Tags ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="75947-151">As a result, the other elements of an HTML page, such as the `<HEAD>` and `<BODY>` tags, are omitted.</span></span>

### <span data-ttu-id="75947-152">Beispiel 8: Erstellen einer Webseite zum Anzeigen von PowerShell-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="75947-152">Example 8: Create a web page to display PowerShell events</span></span>

```powershell
Get-EventLog -Log "Windows PowerShell" | ConvertTo-Html -Property id, level, task
```

<span data-ttu-id="75947-153">Dieser Befehl verwendet das `Get-EventLog` Cmdlet, um Ereignisse aus dem Windows PowerShell-Ereignisprotokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="75947-153">This command uses the `Get-EventLog` cmdlet to get events from the Windows PowerShell event log.</span></span>

<span data-ttu-id="75947-154">Er verwendet einen Pipeline Operator ( `|` ), um die Ereignisse an das `ConvertTo-Html` Cmdlet zu senden, das die Ereignisse in das HTML-Format konvertiert.</span><span class="sxs-lookup"><span data-stu-id="75947-154">It uses a pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet, which converts the events to HTML format.</span></span>

<span data-ttu-id="75947-155">Der `ConvertTo-Html` Befehl verwendet den **Property** -Parameter, um nur die Eigenschaften " **ID**", " **Level**" und " **Task** " des Ereignisses auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="75947-155">The `ConvertTo-Html` command uses the **Property** parameter to select only the **ID**, **Level**, and **Task** properties of the event.</span></span>

### <span data-ttu-id="75947-156">Beispiel 9: Erstellen einer Webseite zum Anzeigen der angegebenen Dienste</span><span class="sxs-lookup"><span data-stu-id="75947-156">Example 9: Create a web page to display specified services</span></span>

```powershell
$htmlParams = @{
  Title = "Windows Services: Server01"
  Body = Get-Date
  PreContent = "<P>Generated by Corporate IT</P>"
  PostContent = "For details, contact Corporate IT."
}
Get-Service A* |
  ConvertTo-Html @htmlParams |
    Out-File Services.htm
Invoke-Item Services.htm
```

<span data-ttu-id="75947-157">Mit diesem Befehl wird eine Webseite erstellt und geöffnet, auf der die Dienste auf dem Computer angezeigt werden, die mit beginnen. Sie verwendet die Parameter **Title**, **Body**, **precontent** und **postcontent** von, `ConvertTo-Html` um die Ausgabe anzupassen.</span><span class="sxs-lookup"><span data-stu-id="75947-157">This command creates and opens a Web page that displays the services on the computer that begin with A. It uses the **Title**, **Body**, **PreContent**, and **PostContent** parameters of `ConvertTo-Html` to customize the output.</span></span>

<span data-ttu-id="75947-158">Der erste Teil des Befehls verwendet das- `Get-Service` Cmdlet, um die Dienste auf dem Computer zu erhalten, die mit beginnen. Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Ergebnisse an das `ConvertTo-Html` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="75947-158">The first part of the command uses the `Get-Service` cmdlet to get the services on the computer that begin with A. The command uses a pipeline operator (`|`) to send the results to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="75947-159">Der Befehl verwendet auch das `Out-File` Cmdlet, um die Ausgabe an die Services.htm Datei zu senden.</span><span class="sxs-lookup"><span data-stu-id="75947-159">The command also uses the `Out-File` cmdlet to send the output to the Services.htm file.</span></span>

<span data-ttu-id="75947-160">Ein Semikolon ( `;` ) beendet den ersten Befehl und startet einen zweiten Befehl, der das `Invoke-Item` Cmdlet verwendet, um die `Services.htm` Datei im Standardbrowser zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="75947-160">A semicolon (`;`) ends the first command and starts a second command, which uses the `Invoke-Item` cmdlet to open the `Services.htm` file in the default browser.</span></span>

### <span data-ttu-id="75947-161">Beispiel 10: Festlegen der Meta-Eigenschaften und des Zeichensatzes der HTML</span><span class="sxs-lookup"><span data-stu-id="75947-161">Example 10: Set the Meta properties and Charset of the HTML</span></span>

```powershell
Get-Service | ConvertTo-HTML -Meta @{
  refresh=10
  author="Author's Name"
  keywords="PowerShell, HTML, ConvertTo-HTML"
} -Charset "UTF-8"
```

<span data-ttu-id="75947-162">Dieser Befehl erstellt den HTML-Code für eine Webseite mit den Meta-Tags für die Aktualisierung, den Autor und die Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="75947-162">This command creates the HTML for a webpage with the meta tags for refresh, author, and keywords.</span></span>
<span data-ttu-id="75947-163">Der Zeichensatz für die Seite ist auf UTF-8 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="75947-163">The charset for the page is set to UTF-8</span></span>

### <span data-ttu-id="75947-164">Beispiel 11: Festlegen des HTML-Code auf XHTML-Übergangs-DTD</span><span class="sxs-lookup"><span data-stu-id="75947-164">Example 11: Set the HTML to XHTML Transitional DTD</span></span>

```powershell
Get-Service | ConvertTo-HTML -Transitional
```

<span data-ttu-id="75947-165">Mit diesem Befehl wird der DOCTYPE des zurückgegebenen HTML-Code auf XHTML Transitional DTD festgelegt.</span><span class="sxs-lookup"><span data-stu-id="75947-165">This command sets the DOCTYPE of the returned HTML to XHTML Transitional DTD</span></span>

## <span data-ttu-id="75947-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="75947-166">PARAMETERS</span></span>

### <span data-ttu-id="75947-167">-AS</span><span class="sxs-lookup"><span data-stu-id="75947-167">-As</span></span>

<span data-ttu-id="75947-168">Bestimmt, ob das Objekt als Tabelle oder Liste formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="75947-168">Determines whether the object is formatted as a table or a list.</span></span> <span data-ttu-id="75947-169">Gültige Werte sind **Table** und **List**.</span><span class="sxs-lookup"><span data-stu-id="75947-169">Valid values are **Table** and **List**.</span></span> <span data-ttu-id="75947-170">Der Standardwert ist **Table**.</span><span class="sxs-lookup"><span data-stu-id="75947-170">The default value is **Table**.</span></span>

<span data-ttu-id="75947-171">Der **Tabellen** Wert generiert eine HTML-Tabelle, die dem PowerShell-Tabellenformat ähnelt.</span><span class="sxs-lookup"><span data-stu-id="75947-171">The **Table** value generates an HTML table that resembles the PowerShell table format.</span></span> <span data-ttu-id="75947-172">Die Kopfzeile zeigt die Eigenschaftennamen an.</span><span class="sxs-lookup"><span data-stu-id="75947-172">The header row displays the property names.</span></span> <span data-ttu-id="75947-173">Jede Tabellenzeile stellt ein Objekt dar und zeigt die Werte des Objekts für jede Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="75947-173">Each table row represents an object and displays the object's values for each property.</span></span>

<span data-ttu-id="75947-174">Der **Listen** Wert generiert eine zweispaltige HTML-Tabelle für jedes Objekt, das dem PowerShell-Listenformat ähnelt.</span><span class="sxs-lookup"><span data-stu-id="75947-174">The **List** value generates a two-column HTML table for each object that resembles the PowerShell list format.</span></span> <span data-ttu-id="75947-175">Die erste Spalte zeigt den Namen der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="75947-175">The first column displays the property name.</span></span> <span data-ttu-id="75947-176">In der zweiten Spalte wird der Eigenschafts Wert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75947-176">The second column displays the property value.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Table, List

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-177">-Text</span><span class="sxs-lookup"><span data-stu-id="75947-177">-Body</span></span>

<span data-ttu-id="75947-178">Gibt den Text an, der nach dem `<BODY>`-Starttag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="75947-178">Specifies the text to add after the opening `<BODY>` tag.</span></span> <span data-ttu-id="75947-179">Standardmäßig enthält diese Position keinen Text.</span><span class="sxs-lookup"><span data-stu-id="75947-179">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-180">-Charset</span><span class="sxs-lookup"><span data-stu-id="75947-180">-Charset</span></span>

<span data-ttu-id="75947-181">Gibt den Text an, der dem öffnenden Tag hinzugefügt wird `<charset>` .</span><span class="sxs-lookup"><span data-stu-id="75947-181">Specifies text to add to the opening `<charset>` tag.</span></span> <span data-ttu-id="75947-182">Standardmäßig enthält diese Position keinen Text.</span><span class="sxs-lookup"><span data-stu-id="75947-182">By default, there is no text in that position.</span></span>

<span data-ttu-id="75947-183">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75947-183">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-184">-Cssuri</span><span class="sxs-lookup"><span data-stu-id="75947-184">-CssUri</span></span>

<span data-ttu-id="75947-185">Gibt den Uniform Resource Identifier (URI) des Cascading Style Sheet (CSS) an, das auf die HTML-Datei angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="75947-185">Specifies the Uniform Resource Identifier (URI) of the cascading style sheet (CSS) that is applied to the HTML file.</span></span> <span data-ttu-id="75947-186">Der URI ist in einem Stylesheet-Link in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="75947-186">The URI is included in a style sheet link in the output.</span></span>

```yaml
Type: System.Uri
Parameter Sets: Page
Aliases: cu, uri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-187">-Fragment</span><span class="sxs-lookup"><span data-stu-id="75947-187">-Fragment</span></span>

<span data-ttu-id="75947-188">Generiert nur eine HTML-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="75947-188">Generates only an HTML table.</span></span> <span data-ttu-id="75947-189">Die Tags HTML, HEAD, TITLE und BODY werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="75947-189">The HTML, HEAD, TITLE, and BODY tags are omitted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Fragment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-190">-Head</span><span class="sxs-lookup"><span data-stu-id="75947-190">-Head</span></span>

<span data-ttu-id="75947-191">Gibt den Inhalt des `<HEAD>`-Tags an.</span><span class="sxs-lookup"><span data-stu-id="75947-191">Specifies the content of the `<HEAD>` tag.</span></span> <span data-ttu-id="75947-192">Der Standardwert ist `<title\>HTML TABLE</title>`.</span><span class="sxs-lookup"><span data-stu-id="75947-192">The default is `<title\>HTML TABLE</title>`.</span></span> <span data-ttu-id="75947-193">Wenn Sie den **Head** -Parameter verwenden, wird der **Title** -Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="75947-193">If you use the **Head** parameter, the **Title** parameter is ignored.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="75947-194">-InputObject</span></span>

<span data-ttu-id="75947-195">Gibt die Objekte an, die im HTML-Format dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="75947-195">Specifies the objects to be represented in HTML.</span></span> <span data-ttu-id="75947-196">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="75947-196">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="75947-197">Wenn Sie diesen Parameter verwenden, um mehrere Objekte zu senden, z. b. alle Dienste auf einem Computer, `ConvertTo-Html` erstellt eine Tabelle, in der die Eigenschaften einer Sammlung oder eines Arrays von Objekten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75947-197">If you use this parameter to submit multiple objects, such as all of the services on a computer, `ConvertTo-Html` creates a table that displays the properties of a collection or of an array of objects.</span></span> <span data-ttu-id="75947-198">Verwenden Sie zum Erstellen einer Tabelle der einzelnen Objekte den Pipeline-Operator, um die Objekte an zu übergeben `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="75947-198">To create a table of the individual objects, use the pipeline operator to pipe the objects to `ConvertTo-Html`.</span></span>

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

### <span data-ttu-id="75947-199">-Meta</span><span class="sxs-lookup"><span data-stu-id="75947-199">-Meta</span></span>

<span data-ttu-id="75947-200">Gibt den Text an, der dem öffnenden Tag hinzugefügt wird `<meta>` .</span><span class="sxs-lookup"><span data-stu-id="75947-200">Specifies text to add to the opening `<meta>` tag.</span></span> <span data-ttu-id="75947-201">Standardmäßig enthält diese Position keinen Text.</span><span class="sxs-lookup"><span data-stu-id="75947-201">By default, there is no text in that position.</span></span>

<span data-ttu-id="75947-202">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75947-202">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-203">-Postcontent</span><span class="sxs-lookup"><span data-stu-id="75947-203">-PostContent</span></span>

<span data-ttu-id="75947-204">Gibt Text an, der nach dem `</TABLE>`-Endtag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="75947-204">Specifies text to add after the closing `</TABLE>` tag.</span></span> <span data-ttu-id="75947-205">Standardmäßig enthält diese Position keinen Text.</span><span class="sxs-lookup"><span data-stu-id="75947-205">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-206">-Vorab Inhalt</span><span class="sxs-lookup"><span data-stu-id="75947-206">-PreContent</span></span>

<span data-ttu-id="75947-207">Gibt den Text an, der vor dem `<TABLE>`-Starttag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="75947-207">Specifies text to add before the opening `<TABLE>` tag.</span></span> <span data-ttu-id="75947-208">Standardmäßig enthält diese Position keinen Text.</span><span class="sxs-lookup"><span data-stu-id="75947-208">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-209">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="75947-209">-Property</span></span>

<span data-ttu-id="75947-210">Schließt die angegebenen Eigenschaften der Objekte im HTML-Code ein.</span><span class="sxs-lookup"><span data-stu-id="75947-210">Includes the specified properties of the objects in the HTML.</span></span> <span data-ttu-id="75947-211">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="75947-211">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="75947-212">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="75947-212">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="75947-213">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="75947-213">Valid key-value pairs are:</span></span>

- <span data-ttu-id="75947-214">Name (oder Bezeichnung): `<string>` (hinzugefügt in PowerShell 6. x)</span><span class="sxs-lookup"><span data-stu-id="75947-214">Name (or label) - `<string>` (added in PowerShell 6.x)</span></span>
- <span data-ttu-id="75947-215">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="75947-215">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="75947-216">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="75947-216">FormatString - `<string>`</span></span>
- <span data-ttu-id="75947-217">Width- `<int32>` -muss größer sein als `0`</span><span class="sxs-lookup"><span data-stu-id="75947-217">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="75947-218">Der Ausrichtungs Wert kann `Left` , `Center` oder sein. `Right`</span><span class="sxs-lookup"><span data-stu-id="75947-218">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="75947-219">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="75947-219">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-220">-Title</span><span class="sxs-lookup"><span data-stu-id="75947-220">-Title</span></span>

<span data-ttu-id="75947-221">Gibt einen Titel für die HTML-Datei an, d. h. den Text zwischen den `<TITLE>`-Tags.</span><span class="sxs-lookup"><span data-stu-id="75947-221">Specifies a title for the HTML file, that is, the text that appears between the `<TITLE>` tags.</span></span>

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-222">-Transitional</span><span class="sxs-lookup"><span data-stu-id="75947-222">-Transitional</span></span>

<span data-ttu-id="75947-223">Ändert den **DOCTYPE** in **XHTML Transitional DTD**, der Standard **DOCTYPE** ist **XHTML strict DTD**.</span><span class="sxs-lookup"><span data-stu-id="75947-223">Changes the **DOCTYPE** to **XHTML Transitional DTD**, Default **DOCTYPE** is **XHTML Strict DTD**.</span></span>

<span data-ttu-id="75947-224">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75947-224">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75947-225">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="75947-225">CommonParameters</span></span>

<span data-ttu-id="75947-226">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="75947-226">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="75947-227">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="75947-227">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="75947-228">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="75947-228">INPUTS</span></span>

### <span data-ttu-id="75947-229">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="75947-229">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="75947-230">Sie können ein beliebiges .NET-Objekt an übergeben `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="75947-230">You can pipe any .NET object to `ConvertTo-Html`.</span></span>

## <span data-ttu-id="75947-231">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="75947-231">OUTPUTS</span></span>

### <span data-ttu-id="75947-232">System. String-oder System.Xml.Xml-Dokument</span><span class="sxs-lookup"><span data-stu-id="75947-232">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="75947-233">`ConvertTo-Html` gibt eine Reihe von Zeichen folgen zurück, die gültige HTML enthalten.</span><span class="sxs-lookup"><span data-stu-id="75947-233">`ConvertTo-Html` returns series of strings that comprise valid HTML.</span></span>

## <span data-ttu-id="75947-234">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="75947-234">NOTES</span></span>

<span data-ttu-id="75947-235">Um dieses Cmdlet zu verwenden, übergeben Sie ein oder mehrere Objekte an das Cmdlet, oder verwenden Sie den **Inputobject** -Parameter, um das Objekt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="75947-235">To use this cmdlet, pipe one or more objects to the cmdlet or use the **InputObject** parameter to specify the object.</span></span> <span data-ttu-id="75947-236">Wenn die Eingabe aus mehreren Objekten besteht, ist die Ausgabe dieser beiden Methoden sehr unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="75947-236">When the input consists of multiple objects, the output of these two methods is quite different.</span></span>

- <span data-ttu-id="75947-237">Wenn Sie mehrere Objekte an ein Cmdlet weiterreichen, sendet PowerShell die Objekte nacheinander an das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="75947-237">When you pipe multiple objects to a cmdlet, PowerShell sends the objects to the cmdlet one at a time.</span></span> <span data-ttu-id="75947-238">Daher wird von `ConvertTo-Html` eine Tabelle erstellt, in der die einzelnen Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75947-238">As a result, `ConvertTo-Html` creates a table that displays the individual objects.</span></span> <span data-ttu-id="75947-239">Wenn Sie beispielsweise die Prozesse auf einem Computer an weiterleiten `ConvertTo-Html` , zeigt die resultierende Tabelle alle Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="75947-239">For example, if you pipe the processes on a computer to `ConvertTo-Html`, the resulting table displays all of the processes.</span></span>

- <span data-ttu-id="75947-240">Wenn Sie den **Inputobject** -Parameter verwenden, um mehrere Objekte zu senden, `ConvertTo-Html` empfängt diese Objekte als Sammlung oder als Array.</span><span class="sxs-lookup"><span data-stu-id="75947-240">When you use the **InputObject** parameter to submit multiple objects, `ConvertTo-Html` receives these objects as a collection or as an array.</span></span> <span data-ttu-id="75947-241">Daher wird eine Tabelle mit dem Array und seinen Eigenschaften erstellt, nicht mit den Elementen im Array.</span><span class="sxs-lookup"><span data-stu-id="75947-241">As a result, it creates a table that displays the array and its properties, not the items in the array.</span></span> <span data-ttu-id="75947-242">Wenn Sie z. b. **Inputobject** verwenden, um die Prozesse auf einem Computer an zu übermitteln `ConvertTo-Html` , zeigt die resultierende Tabelle ein Objekt Array und seine Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="75947-242">For example, if you use **InputObject** to submit the processes on a computer to `ConvertTo-Html`, the resulting table displays an object array and its properties.</span></span>

  <span data-ttu-id="75947-243">Um die XHTML strict DTD einzuhalten, wird das DOCTYPE-Tag entsprechend geändert:</span><span class="sxs-lookup"><span data-stu-id="75947-243">To comply with the XHTML Strict DTD, the DOCTYPE tag is modified accordingly:</span></span>

   `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"   "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"\>`

## <span data-ttu-id="75947-244">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="75947-244">RELATED LINKS</span></span>

[<span data-ttu-id="75947-245">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="75947-245">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="75947-246">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="75947-246">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="75947-247">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="75947-247">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="75947-248">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="75947-248">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="75947-249">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="75947-249">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="75947-250">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="75947-250">Import-Clixml</span></span>](Import-Clixml.md)
