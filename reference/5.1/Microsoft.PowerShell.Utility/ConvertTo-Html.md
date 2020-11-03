---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-html?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Html
ms.openlocfilehash: 618308bb03f47659b8fa932ac0bb029972546755
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "93219220"
---
# <span data-ttu-id="2a8ff-103">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="2a8ff-103">ConvertTo-Html</span></span>

## <span data-ttu-id="2a8ff-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="2a8ff-104">SYNOPSIS</span></span>
<span data-ttu-id="2a8ff-105">Konvertiert .NET-Objekte in HTML, die in einem Webbrowser angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-105">Converts .NET objects into HTML that can be displayed in a Web browser.</span></span>

## <span data-ttu-id="2a8ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2a8ff-106">SYNTAX</span></span>

### <span data-ttu-id="2a8ff-107">Seite (Standard)</span><span class="sxs-lookup"><span data-stu-id="2a8ff-107">Page (Default)</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [[-Body] <String[]>]
 [[-Head] <String[]>] [[-Title] <String>] [-As <String>] [-CssUri <Uri>] [-PostContent <String[]>]
 [-PreContent <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="2a8ff-108">Fragment</span><span class="sxs-lookup"><span data-stu-id="2a8ff-108">Fragment</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [-As <String>] [-Fragment]
 [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="2a8ff-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2a8ff-109">DESCRIPTION</span></span>

<span data-ttu-id="2a8ff-110">Das- `ConvertTo-Html` Cmdlet konvertiert .NET-Objekte in HTML, die in einem Webbrowser angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-110">The `ConvertTo-Html` cmdlet converts .NET objects into HTML that can be displayed in a Web browser.</span></span> <span data-ttu-id="2a8ff-111">Sie können dieses Cmdlet verwenden, um die Ausgabe eines Befehls auf einer Webseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-111">You can use this cmdlet to display the output of a command in a Web page.</span></span>

<span data-ttu-id="2a8ff-112">Sie können die Parameter von verwenden `ConvertTo-Html` , um Objekteigenschaften auszuwählen, ein Tabellen-oder Listenformat anzugeben, den Titel der HTML-Seite anzugeben, Text vor und nach dem Objekt hinzuzufügen und nur das Tabellen-oder Listen Fragment anstelle einer Strict DTD-Seite zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-112">You can use the parameters of `ConvertTo-Html` to select object properties, to specify a table or list format, to specify the HTML page title, to add text before and after the object, and to return only the table or list fragment, instead of a strict DTD page.</span></span>

<span data-ttu-id="2a8ff-113">Wenn Sie mehrere Objekte an senden `ConvertTo-Html` , erstellt PowerShell die Tabelle (oder Liste) auf Grundlage der Eigenschaften des ersten Objekts, das Sie übermitteln.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-113">When you submit multiple objects to `ConvertTo-Html`, PowerShell creates the table (or list) based on the properties of the first object that you submit.</span></span> <span data-ttu-id="2a8ff-114">Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschaftenwert dieses Objekts eine leere Zelle.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-114">If the remaining objects do not have one of the specified properties, the property value of that object is an empty cell.</span></span> <span data-ttu-id="2a8ff-115">Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, sind diese Eigenschaftenwerte nicht in der Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-115">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

## <span data-ttu-id="2a8ff-116">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="2a8ff-116">EXAMPLES</span></span>

### <span data-ttu-id="2a8ff-117">Beispiel 1: Erstellen einer Webseite zum Anzeigen des Datums</span><span class="sxs-lookup"><span data-stu-id="2a8ff-117">Example 1: Create a web page to display the date</span></span>

```powershell
ConvertTo-Html -InputObject (Get-Date)
```

<span data-ttu-id="2a8ff-118">Dieser Befehl erstellt eine HTML-Seite, die die Eigenschaften des aktuellen Datums anzeigt.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-118">This command creates an HTML page that displays the properties of the current date.</span></span> <span data-ttu-id="2a8ff-119">Er verwendet den **Inputobject** -Parameter, um die Ergebnisse eines `Get-Date` Befehls an das `ConvertTo-Html` Cmdlet zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-119">It uses the **InputObject** parameter to submit the results of a `Get-Date` command to the `ConvertTo-Html` cmdlet.</span></span>

### <span data-ttu-id="2a8ff-120">Beispiel 2: Erstellen einer Webseite zum Anzeigen von PowerShell-Aliasen</span><span class="sxs-lookup"><span data-stu-id="2a8ff-120">Example 2: Create a web page to display PowerShell aliases</span></span>

```powershell
Get-Alias | ConvertTo-Html | Out-File aliases.htm
Invoke-Item aliases.htm
```

<span data-ttu-id="2a8ff-121">Dieser Befehl erstellt eine HTML-Seite, auf der die PowerShell-Aliase in der aktuellen Konsole aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-121">This command creates an HTML page that lists the PowerShell aliases in the current console.</span></span>

<span data-ttu-id="2a8ff-122">Der Befehl verwendet das `Get-Alias` Cmdlet, um die Aliase zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-122">The command uses the `Get-Alias` cmdlet to get the aliases.</span></span> <span data-ttu-id="2a8ff-123">Der Pipeline Operator ( `|` ) wird verwendet, um die Aliase an das `ConvertTo-Html` Cmdlet zu senden, das die HTML-Seite erstellt.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-123">It uses the pipeline operator (`|`) to send the aliases to the `ConvertTo-Html` cmdlet, which creates the HTML page.</span></span> <span data-ttu-id="2a8ff-124">Der Befehl verwendet auch das `Out-File` Cmdlet, um den HTML-Code an die Datei zu senden `aliases.htm` .</span><span class="sxs-lookup"><span data-stu-id="2a8ff-124">The command also uses the `Out-File` cmdlet to send the HTML code to the `aliases.htm` file.</span></span>

### <span data-ttu-id="2a8ff-125">Beispiel 3: Erstellen einer Webseite zum Anzeigen von PowerShell-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="2a8ff-125">Example 3: Create a web page to display PowerShell events</span></span>

```powershell
`Get-EventLog` -LogName "Windows PowerShell" | ConvertTo-Html | Out-File pslog.htm
```

<span data-ttu-id="2a8ff-126">Dieser Befehl erstellt eine HTML-Seite mit `pslog.htm` dem Namen, auf der die Ereignisse im Windows PowerShell-Ereignisprotokoll auf dem lokalen Computer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-126">This command creates an HTML page called `pslog.htm` that displays the events in the Windows PowerShell event log on the local computer.</span></span>

<span data-ttu-id="2a8ff-127">Er verwendet das `Get-EventLog` Cmdlet, um die Ereignisse im Windows PowerShell-Protokoll zu erhalten, und verwendet dann den Pipeline Operator ( `|` ), um die Ereignisse an das `ConvertTo-Html` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-127">It uses the `Get-EventLog` cmdlet to get the events in the Windows PowerShell log and then uses the pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="2a8ff-128">Der Befehl verwendet auch das `Out-File` Cmdlet, um den HTML-Code an die Datei zu senden `pslog.htm` .</span><span class="sxs-lookup"><span data-stu-id="2a8ff-128">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

<span data-ttu-id="2a8ff-129">Der Befehl verwendet auch das `Out-File` Cmdlet, um den HTML-Code an die Datei zu senden `pslog.htm` .</span><span class="sxs-lookup"><span data-stu-id="2a8ff-129">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

### <span data-ttu-id="2a8ff-130">Beispiel 4: Erstellen einer Webseite zum Anzeigen von Prozessen</span><span class="sxs-lookup"><span data-stu-id="2a8ff-130">Example 4: Create a web page to display processes</span></span>

```powershell
Get-Process |
  ConvertTo-Html -Property Name, Path, Company -Title "Process Information" |
    Out-File proc.htm
Invoke-Item proc.htm
```

<span data-ttu-id="2a8ff-131">Diese Befehle erstellen und öffnen eine HTML-Seite, die den Namen, Pfad und das Unternehmen der Prozesse auf dem lokalen Computer auflistet.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-131">These commands create and open an HTML page that lists the name, path, and company of the processes on the local computer.</span></span>

<span data-ttu-id="2a8ff-132">Der erste Befehl verwendet das `Get-Process` Cmdlet, um Objekte zu erhalten, die die Prozesse darstellen, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-132">The first command uses the `Get-Process` cmdlet to get objects that represent the processes running on the computer.</span></span> <span data-ttu-id="2a8ff-133">Der Befehl verwendet den Pipeline Operator ( `|` ), um die Prozess Objekte an das `ConvertTo-Html` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-133">The command uses the pipeline operator (`|`) to send the process objects to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="2a8ff-134">Der Befehl verwendet den **Property** -Parameter, um drei Eigenschaften der Process-Objekte auszuwählen, die in die Tabelle eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-134">The command uses the **Property** parameter to select three properties of the process objects to be included in the table.</span></span> <span data-ttu-id="2a8ff-135">Der Befehl verwendet den **Title** -Parameter, um einen Titel für die HTML-Seite anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-135">The command uses the **Title** parameter to specify a title for the HTML page.</span></span> <span data-ttu-id="2a8ff-136">Der Befehl verwendet auch das `Out-File` Cmdlet, um das resultierende HTML an eine Datei mit dem Namen Proc.htm zu senden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-136">The command also uses the `Out-File` cmdlet to send the resulting HTML to a file named Proc.htm.</span></span>

<span data-ttu-id="2a8ff-137">Der zweite Befehl verwendet das `Invoke-Item` Cmdlet, um `Proc.htm` im Standardbrowser zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-137">The second command uses the `Invoke-Item` cmdlet to open the `Proc.htm` in the default browser.</span></span>

### <span data-ttu-id="2a8ff-138">Beispiel 5: Erstellen einer Webseite zum Anzeigen von Dienst Objekten</span><span class="sxs-lookup"><span data-stu-id="2a8ff-138">Example 5: Create a web page to display service objects</span></span>

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

<span data-ttu-id="2a8ff-139">Dieser Befehl erstellt eine HTML-Seite der Dienst Objekte, die vom `Get-Service` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-139">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="2a8ff-140">Der Befehl verwendet den **cssuri** -Parameter, um ein Cascading Stylesheet für die HTML-Seite anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-140">The command uses the **CssUri** parameter to specify a cascading style sheet for the HTML page.</span></span>

<span data-ttu-id="2a8ff-141">Der **cssuri** -Parameter fügt dem resultierenden HTML-Code ein zusätzliches `<link rel="stylesheet" type="text/css" href="test.css">` Tag hinzu.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-141">The **CssUri** parameter adds an additional `<link rel="stylesheet" type="text/css" href="test.css">` tag to the resulting HTML.</span></span> <span data-ttu-id="2a8ff-142">Das HREF-Attribut im Tag enthält den Namen des Stylesheets.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-142">The HREF attribute in the tag contains the name of the style sheet.</span></span>

### <span data-ttu-id="2a8ff-143">Beispiel 6: Erstellen einer Webseite zum Anzeigen von Dienst Objekten</span><span class="sxs-lookup"><span data-stu-id="2a8ff-143">Example 6: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -As LIST | Out-File services.htm
```

<span data-ttu-id="2a8ff-144">Dieser Befehl erstellt eine HTML-Seite der Dienst Objekte, die vom `Get-Service` Cmdlet zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-144">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="2a8ff-145">Der Befehl verwendet den **As** -Parameter, um ein Listenformat anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-145">The command uses the **As** parameter to specify a list format.</span></span> <span data-ttu-id="2a8ff-146">Das-Cmdlet `Out-File` sendet das resultierende HTML an die `Services.htm` Datei.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-146">The cmdlet `Out-File` sends the resulting HTML to the `Services.htm` file.</span></span>

### <span data-ttu-id="2a8ff-147">Beispiel 7: Erstellen einer Webtabelle für das aktuelle Datum</span><span class="sxs-lookup"><span data-stu-id="2a8ff-147">Example 7: Create a web table for the current date</span></span>

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

<span data-ttu-id="2a8ff-148">Dieser Befehl verwendet `ConvertTo-Html` , um eine HTML-Tabelle des aktuellen Datums zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-148">This command uses `ConvertTo-Html` to generate an HTML table of the current date.</span></span> <span data-ttu-id="2a8ff-149">Der Befehl verwendet das `Get-Date` Cmdlet, um das aktuelle Datum zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-149">The command uses the `Get-Date` cmdlet to get the current date.</span></span> <span data-ttu-id="2a8ff-150">Er verwendet einen Pipeline Operator (|), um die Ergebnisse an das `ConvertTo-Html` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-150">It uses a pipeline operator (|) to send the results to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="2a8ff-151">Der- `ConvertTo-Html` Befehl enthält den **Fragment** -Parameter, der die Ausgabe auf eine HTML-Tabelle beschränkt.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-151">The `ConvertTo-Html` command includes the **Fragment** parameter, which limits the output to an HTML table.</span></span> <span data-ttu-id="2a8ff-152">Daher werden die anderen Elemente einer HTML-Seite wie die `<HEAD>`- und `<BODY>`-Tags ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-152">As a result, the other elements of an HTML page, such as the `<HEAD>` and `<BODY>` tags, are omitted.</span></span>

### <span data-ttu-id="2a8ff-153">Beispiel 8: Erstellen einer Webseite zum Anzeigen von PowerShell-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="2a8ff-153">Example 8: Create a web page to display PowerShell events</span></span>

```powershell
Get-EventLog -Log "Windows PowerShell" | ConvertTo-Html -Property id, level, task
```

<span data-ttu-id="2a8ff-154">Dieser Befehl verwendet das `Get-EventLog` Cmdlet, um Ereignisse aus dem Windows PowerShell-Ereignisprotokoll zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-154">This command uses the `Get-EventLog` cmdlet to get events from the Windows PowerShell event log.</span></span>

<span data-ttu-id="2a8ff-155">Er verwendet einen Pipeline Operator ( `|` ), um die Ereignisse an das `ConvertTo-Html` Cmdlet zu senden, das die Ereignisse in das HTML-Format konvertiert.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-155">It uses a pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet, which converts the events to HTML format.</span></span>

<span data-ttu-id="2a8ff-156">Der `ConvertTo-Html` Befehl verwendet den **Property** -Parameter, um nur die Eigenschaften " **ID** ", " **Level** " und " **Task** " des Ereignisses auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-156">The `ConvertTo-Html` command uses the **Property** parameter to select only the **ID** , **Level** , and **Task** properties of the event.</span></span>

### <span data-ttu-id="2a8ff-157">Beispiel 9: Erstellen einer Webseite zum Anzeigen der angegebenen Dienste</span><span class="sxs-lookup"><span data-stu-id="2a8ff-157">Example 9: Create a web page to display specified services</span></span>

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

<span data-ttu-id="2a8ff-158">Mit diesem Befehl wird eine Webseite erstellt und geöffnet, auf der die Dienste auf dem Computer angezeigt werden, die mit beginnen. Sie verwendet die Parameter **Title** , **Body** , **precontent** und **postcontent** von, `ConvertTo-Html` um die Ausgabe anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-158">This command creates and opens a Web page that displays the services on the computer that begin with A. It uses the **Title** , **Body** , **PreContent** , and **PostContent** parameters of `ConvertTo-Html` to customize the output.</span></span>

<span data-ttu-id="2a8ff-159">Der erste Teil des Befehls verwendet das- `Get-Service` Cmdlet, um die Dienste auf dem Computer zu erhalten, die mit beginnen. Der Befehl verwendet einen Pipeline Operator ( `|` ), um die Ergebnisse an das `ConvertTo-Html` Cmdlet zu senden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-159">The first part of the command uses the `Get-Service` cmdlet to get the services on the computer that begin with A. The command uses a pipeline operator (`|`) to send the results to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="2a8ff-160">Der Befehl verwendet auch das `Out-File` Cmdlet, um die Ausgabe an die Services.htm Datei zu senden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-160">The command also uses the `Out-File` cmdlet to send the output to the Services.htm file.</span></span>

<span data-ttu-id="2a8ff-161">Ein Semikolon ( `;` ) beendet den ersten Befehl und startet einen zweiten Befehl, der das `Invoke-Item` Cmdlet verwendet, um die `Services.htm` Datei im Standardbrowser zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-161">A semicolon (`;`) ends the first command and starts a second command, which uses the `Invoke-Item` cmdlet to open the `Services.htm` file in the default browser.</span></span>

## <span data-ttu-id="2a8ff-162">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2a8ff-162">PARAMETERS</span></span>

### <span data-ttu-id="2a8ff-163">-AS</span><span class="sxs-lookup"><span data-stu-id="2a8ff-163">-As</span></span>

<span data-ttu-id="2a8ff-164">Bestimmt, ob das Objekt als Tabelle oder Liste formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-164">Determines whether the object is formatted as a table or a list.</span></span> <span data-ttu-id="2a8ff-165">Gültige Werte sind **Table** und **List**.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-165">Valid values are **Table** and **List**.</span></span> <span data-ttu-id="2a8ff-166">Der Standardwert ist **Table**.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-166">The default value is **Table**.</span></span>

<span data-ttu-id="2a8ff-167">Der **Tabellen** Wert generiert eine HTML-Tabelle, die dem PowerShell-Tabellenformat ähnelt.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-167">The **Table** value generates an HTML table that resembles the PowerShell table format.</span></span> <span data-ttu-id="2a8ff-168">Die Kopfzeile zeigt die Eigenschaftennamen an.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-168">The header row displays the property names.</span></span> <span data-ttu-id="2a8ff-169">Jede Tabellenzeile stellt ein Objekt dar und zeigt die Werte des Objekts für jede Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-169">Each table row represents an object and displays the object's values for each property.</span></span>

<span data-ttu-id="2a8ff-170">Der **Listen** Wert generiert eine zweispaltige HTML-Tabelle für jedes Objekt, das dem PowerShell-Listenformat ähnelt.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-170">The **List** value generates a two-column HTML table for each object that resembles the PowerShell list format.</span></span> <span data-ttu-id="2a8ff-171">Die erste Spalte zeigt den Namen der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-171">The first column displays the property name.</span></span> <span data-ttu-id="2a8ff-172">In der zweiten Spalte wird der Eigenschafts Wert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-172">The second column displays the property value.</span></span>

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

### <span data-ttu-id="2a8ff-173">-Text</span><span class="sxs-lookup"><span data-stu-id="2a8ff-173">-Body</span></span>

<span data-ttu-id="2a8ff-174">Gibt den Text an, der nach dem `<BODY>`-Starttag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-174">Specifies the text to add after the opening `<BODY>` tag.</span></span> <span data-ttu-id="2a8ff-175">Standardmäßig enthält diese Position keinen Text.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-175">By default, there is no text in that position.</span></span>

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

### <span data-ttu-id="2a8ff-176">-Cssuri</span><span class="sxs-lookup"><span data-stu-id="2a8ff-176">-CssUri</span></span>

<span data-ttu-id="2a8ff-177">Gibt den Uniform Resource Identifier (URI) des Cascading Style Sheet (CSS) an, das auf die HTML-Datei angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-177">Specifies the Uniform Resource Identifier (URI) of the cascading style sheet (CSS) that is applied to the HTML file.</span></span> <span data-ttu-id="2a8ff-178">Der URI ist in einem Stylesheet-Link in der Ausgabe enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-178">The URI is included in a style sheet link in the output.</span></span>

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

### <span data-ttu-id="2a8ff-179">-Fragment</span><span class="sxs-lookup"><span data-stu-id="2a8ff-179">-Fragment</span></span>

<span data-ttu-id="2a8ff-180">Generiert nur eine HTML-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-180">Generates only an HTML table.</span></span> <span data-ttu-id="2a8ff-181">Die Tags HTML, HEAD, TITLE und BODY werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-181">The HTML, HEAD, TITLE, and BODY tags are omitted.</span></span>

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

### <span data-ttu-id="2a8ff-182">-Head</span><span class="sxs-lookup"><span data-stu-id="2a8ff-182">-Head</span></span>

<span data-ttu-id="2a8ff-183">Gibt den Inhalt des `<HEAD>`-Tags an.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-183">Specifies the content of the `<HEAD>` tag.</span></span> <span data-ttu-id="2a8ff-184">Der Standardwert ist `<title\>HTML TABLE</title>`.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-184">The default is `<title\>HTML TABLE</title>`.</span></span> <span data-ttu-id="2a8ff-185">Wenn Sie den **Head** -Parameter verwenden, wird der **Title** -Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-185">If you use the **Head** parameter, the **Title** parameter is ignored.</span></span>

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

### <span data-ttu-id="2a8ff-186">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2a8ff-186">-InputObject</span></span>

<span data-ttu-id="2a8ff-187">Gibt die Objekte an, die im HTML-Format dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-187">Specifies the objects to be represented in HTML.</span></span> <span data-ttu-id="2a8ff-188">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-188">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="2a8ff-189">Wenn Sie diesen Parameter verwenden, um mehrere Objekte zu senden, z. b. alle Dienste auf einem Computer, `ConvertTo-Html` erstellt eine Tabelle, in der die Eigenschaften einer Sammlung oder eines Arrays von Objekten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-189">If you use this parameter to submit multiple objects, such as all of the services on a computer, `ConvertTo-Html` creates a table that displays the properties of a collection or of an array of objects.</span></span> <span data-ttu-id="2a8ff-190">Verwenden Sie zum Erstellen einer Tabelle der einzelnen Objekte den Pipeline-Operator, um die Objekte an zu übergeben `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="2a8ff-190">To create a table of the individual objects, use the pipeline operator to pipe the objects to `ConvertTo-Html`.</span></span>

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

### <span data-ttu-id="2a8ff-191">-Postcontent</span><span class="sxs-lookup"><span data-stu-id="2a8ff-191">-PostContent</span></span>

<span data-ttu-id="2a8ff-192">Gibt Text an, der nach dem `</TABLE>`-Endtag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-192">Specifies text to add after the closing `</TABLE>` tag.</span></span> <span data-ttu-id="2a8ff-193">Standardmäßig enthält diese Position keinen Text.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-193">By default, there is no text in that position.</span></span>

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

### <span data-ttu-id="2a8ff-194">-Vorab Inhalt</span><span class="sxs-lookup"><span data-stu-id="2a8ff-194">-PreContent</span></span>

<span data-ttu-id="2a8ff-195">Gibt den Text an, der vor dem `<TABLE>`-Starttag hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-195">Specifies text to add before the opening `<TABLE>` tag.</span></span> <span data-ttu-id="2a8ff-196">Standardmäßig enthält diese Position keinen Text.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-196">By default, there is no text in that position.</span></span>

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

### <span data-ttu-id="2a8ff-197">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2a8ff-197">-Property</span></span>

<span data-ttu-id="2a8ff-198">Schließt die angegebenen Eigenschaften der Objekte im HTML-Code ein.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-198">Includes the specified properties of the objects in the HTML.</span></span> <span data-ttu-id="2a8ff-199">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-199">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="2a8ff-200">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-200">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="2a8ff-201">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="2a8ff-201">Valid key-value pairs are:</span></span>

- <span data-ttu-id="2a8ff-202">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="2a8ff-202">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="2a8ff-203">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="2a8ff-203">FormatString - `<string>`</span></span>
- <span data-ttu-id="2a8ff-204">Width- `<int32>` -muss größer sein als `0`</span><span class="sxs-lookup"><span data-stu-id="2a8ff-204">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="2a8ff-205">Der Ausrichtungs Wert kann `Left` , `Center` oder sein. `Right`</span><span class="sxs-lookup"><span data-stu-id="2a8ff-205">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="2a8ff-206">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="2a8ff-206">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="2a8ff-207">-Title</span><span class="sxs-lookup"><span data-stu-id="2a8ff-207">-Title</span></span>

<span data-ttu-id="2a8ff-208">Gibt einen Titel für die HTML-Datei an, d. h. den Text zwischen den `<TITLE>`-Tags.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-208">Specifies a title for the HTML file, that is, the text that appears between the `<TITLE>` tags.</span></span>

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

### <span data-ttu-id="2a8ff-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2a8ff-209">CommonParameters</span></span>

<span data-ttu-id="2a8ff-210">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2a8ff-211">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2a8ff-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2a8ff-212">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="2a8ff-212">INPUTS</span></span>

### <span data-ttu-id="2a8ff-213">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="2a8ff-213">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="2a8ff-214">Sie können ein beliebiges .NET-Objekt an übergeben `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="2a8ff-214">You can pipe any .NET object to `ConvertTo-Html`.</span></span>

## <span data-ttu-id="2a8ff-215">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="2a8ff-215">OUTPUTS</span></span>

### <span data-ttu-id="2a8ff-216">System. String-oder System.Xml.Xml-Dokument</span><span class="sxs-lookup"><span data-stu-id="2a8ff-216">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="2a8ff-217">`ConvertTo-Html` gibt eine Reihe von Zeichen folgen zurück, die gültige HTML enthalten.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-217">`ConvertTo-Html` returns series of strings that comprise valid HTML.</span></span>

## <span data-ttu-id="2a8ff-218">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="2a8ff-218">NOTES</span></span>

<span data-ttu-id="2a8ff-219">Um dieses Cmdlet zu verwenden, übergeben Sie ein oder mehrere Objekte an das Cmdlet, oder verwenden Sie den **Inputobject** -Parameter, um das Objekt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-219">To use this cmdlet, pipe one or more objects to the cmdlet or use the **InputObject** parameter to specify the object.</span></span> <span data-ttu-id="2a8ff-220">Wenn die Eingabe aus mehreren Objekten besteht, ist die Ausgabe dieser beiden Methoden sehr unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-220">When the input consists of multiple objects, the output of these two methods is quite different.</span></span>

- <span data-ttu-id="2a8ff-221">Wenn Sie mehrere Objekte an ein Cmdlet weiterreichen, sendet PowerShell die Objekte nacheinander an das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-221">When you pipe multiple objects to a cmdlet, PowerShell sends the objects to the cmdlet one at a time.</span></span> <span data-ttu-id="2a8ff-222">Daher wird von `ConvertTo-Html` eine Tabelle erstellt, in der die einzelnen Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-222">As a result, `ConvertTo-Html` creates a table that displays the individual objects.</span></span> <span data-ttu-id="2a8ff-223">Wenn Sie beispielsweise die Prozesse auf einem Computer an weiterleiten `ConvertTo-Html` , zeigt die resultierende Tabelle alle Prozesse an.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-223">For example, if you pipe the processes on a computer to `ConvertTo-Html`, the resulting table displays all of the processes.</span></span>

- <span data-ttu-id="2a8ff-224">Wenn Sie den **Inputobject** -Parameter verwenden, um mehrere Objekte zu senden, `ConvertTo-Html` empfängt diese Objekte als Sammlung oder als Array.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-224">When you use the **InputObject** parameter to submit multiple objects, `ConvertTo-Html` receives these objects as a collection or as an array.</span></span> <span data-ttu-id="2a8ff-225">Daher wird eine Tabelle mit dem Array und seinen Eigenschaften erstellt, nicht mit den Elementen im Array.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-225">As a result, it creates a table that displays the array and its properties, not the items in the array.</span></span> <span data-ttu-id="2a8ff-226">Wenn Sie z. b. **Inputobject** verwenden, um die Prozesse auf einem Computer an zu übermitteln `ConvertTo-Html` , zeigt die resultierende Tabelle ein Objekt Array und seine Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="2a8ff-226">For example, if you use **InputObject** to submit the processes on a computer to `ConvertTo-Html`, the resulting table displays an object array and its properties.</span></span>

  <span data-ttu-id="2a8ff-227">Um die XHTML strict DTD einzuhalten, wird das DOCTYPE-Tag entsprechend geändert:</span><span class="sxs-lookup"><span data-stu-id="2a8ff-227">To comply with the XHTML Strict DTD, the DOCTYPE tag is modified accordingly:</span></span>

   `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"   "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"\>`

## <span data-ttu-id="2a8ff-228">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="2a8ff-228">RELATED LINKS</span></span>

[<span data-ttu-id="2a8ff-229">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="2a8ff-229">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="2a8ff-230">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="2a8ff-230">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="2a8ff-231">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="2a8ff-231">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="2a8ff-232">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="2a8ff-232">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="2a8ff-233">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="2a8ff-233">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="2a8ff-234">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="2a8ff-234">Import-Clixml</span></span>](Import-Clixml.md)
