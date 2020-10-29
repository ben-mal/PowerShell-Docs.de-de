---
ms.date: 09/13/2019
title: Erstellen von Get-WinEvent-Abfragen mit FilterHashtable
description: In diesem Artikel erfahren Sie, wie die FilterHashtable von Get-WinEvent zum Abfragen der Windows-Ereignisprotokolle verwendet wird.
ms.openlocfilehash: 8e080f17436d97adda277600cd202a0e6e9283e0
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500605"
---
# <a name="creating-get-winevent-queries-with-filterhashtable"></a><span data-ttu-id="fa6d8-103">Erstellen von Get-WinEvent-Abfragen mit FilterHashtable</span><span class="sxs-lookup"><span data-stu-id="fa6d8-103">Creating Get-WinEvent queries with FilterHashtable</span></span>

<span data-ttu-id="fa6d8-104">Den **Scripting Guy** -Original-Blogbeitrag vom 3. Juni 2014 können Sie unter [Use FilterHashTable to Filter Event Log with PowerShell](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/) (Verwenden von FilterHashTable zum Filtern des Ereignisprotokolls mit PowerShell) lesen.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-104">To read the original June 3, 2014 **Scripting Guy** blog post, see [Use FilterHashTable to Filter Event Log with PowerShell](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/).</span></span>

<span data-ttu-id="fa6d8-105">Dieser Artikel ist ein Auszug des ursprünglichen Blogbeitrags und erläutert die Verwendung des **FilterHashtable** -Parameters des `Get-WinEvent`-Cmdlets zum Filtern von Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-105">This article is an excerpt of the original blog post and explains how to use the `Get-WinEvent` cmdlet's **FilterHashtable** parameter to filter event logs.</span></span> <span data-ttu-id="fa6d8-106">Das PowerShell `Get-WinEvent`-Cmdlet bietet ein leistungsstarkes Verfahren zum Filtern von Windows-Ereignis- und Diagnoseprotokollen.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-106">PowerShell's `Get-WinEvent` cmdlet is a powerful method to filter Windows event and diagnostic logs.</span></span> <span data-ttu-id="fa6d8-107">Die Leistung wird besser, wenn eine `Get-WinEvent`-Abfrage den **FilterHashtable** -Parameter nutzt.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-107">Performance improves when a `Get-WinEvent` query uses the **FilterHashtable** parameter.</span></span>

<span data-ttu-id="fa6d8-108">Bei der Arbeit mit großen Ereignisprotokollen ist es nicht effizient, Objekte die Pipeline hinab an einen `Where-Object`-Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-108">When you work with large event logs, it's not efficient to send objects down the pipeline to a `Where-Object` command.</span></span> <span data-ttu-id="fa6d8-109">Vor PowerShell 6 war das `Get-EventLog`-Cmdlet eine weitere Option, Protokolldaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-109">Prior to PowerShell 6, the `Get-EventLog` cmdlet was another option to get log data.</span></span> <span data-ttu-id="fa6d8-110">Beispielsweise sind die folgenden Befehle zum Filtern der **Microsoft-Windows-Defrag** -Protokolle ineffizient:</span><span class="sxs-lookup"><span data-stu-id="fa6d8-110">For example, the following commands are inefficient to filter the **Microsoft-Windows-Defrag** logs:</span></span>

```powershell
Get-EventLog -LogName Application | Where-Object Source -Match defrag

Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'defrag' }
```

<span data-ttu-id="fa6d8-111">Der folgende Befehl verwendet eine Hashtabelle, die die Leistung steigert:</span><span class="sxs-lookup"><span data-stu-id="fa6d8-111">The following command uses a hash table that improves the performance:</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='*defrag'
}
```

## <a name="blog-posts-about-enumeration"></a><span data-ttu-id="fa6d8-112">Blogbeiträge zur Enumeration</span><span class="sxs-lookup"><span data-stu-id="fa6d8-112">Blog posts about enumeration</span></span>

<span data-ttu-id="fa6d8-113">Dieser Artikel enthält Informationen zur Verwendung von Enumerationswerten in einer Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-113">This article presents information about how to use enumerated values in a hash table.</span></span> <span data-ttu-id="fa6d8-114">Weitere Informationen über Enumeration finden Sie in diesen **Scripting Guy** -Blogbeiträgen.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-114">For more information about enumeration, read these **Scripting Guy** blog posts.</span></span> <span data-ttu-id="fa6d8-115">Um eine Funktion zu erstellen, die die Enumerationswerte zurückgibt, lesen Sie [Enumerations and Values](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values) (Enumerationen und Werte).</span><span class="sxs-lookup"><span data-stu-id="fa6d8-115">To create a function that returns the enumerated values, see [Enumerations and Values](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values).</span></span>
<span data-ttu-id="fa6d8-116">Weitere Informationen finden Sie in der [Scripting Guy-Reihe von Blogbeiträgen zur Enumeration](https://devblogs.microsoft.com/scripting/?s=about+enumeration).</span><span class="sxs-lookup"><span data-stu-id="fa6d8-116">For more information, see the [Scripting Guy series of blog posts about enumeration](https://devblogs.microsoft.com/scripting/?s=about+enumeration).</span></span>

## <a name="hash-table-key-value-pairs"></a><span data-ttu-id="fa6d8-117">Schlüssel-Wert-Paare für Hashtabellen</span><span class="sxs-lookup"><span data-stu-id="fa6d8-117">Hash table key-value pairs</span></span>

<span data-ttu-id="fa6d8-118">Um effiziente Abfragen zu erstellen, verwenden Sie das `Get-WinEvent`-Cmdlet mit dem **FilterHashtable** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-118">To build efficient queries, use the `Get-WinEvent` cmdlet with the **FilterHashtable** parameter.</span></span>
<span data-ttu-id="fa6d8-119">**FilterHashtable** akzeptiert eine Hashtabelle als Filter, um bestimmte Informationen aus Windows-Ereignisprotokollen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-119">**FilterHashtable** accepts a hash table as a filter to get specific information from Windows event logs.</span></span> <span data-ttu-id="fa6d8-120">Eine Hashtabelle verwendet **Schlüssel-Wert-Paare** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-120">A hash table uses **key-value** pairs.</span></span> <span data-ttu-id="fa6d8-121">Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables) (Informationen zu Hashtabellen).</span><span class="sxs-lookup"><span data-stu-id="fa6d8-121">For more information about hash tables, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="fa6d8-122">Wenn sich die **Schlüssel-Wert-Paare** in der gleichen Zeile befinden, müssen sie durch ein Semikolon getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-122">If the **key-value** pairs are on the same line, they must be separated by a semicolon.</span></span> <span data-ttu-id="fa6d8-123">Wenn sich jedes **Schlüssel-Wert-Paar** in einer separaten Zeile befindet, ist kein Semikolon erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-123">If each **key-value** pair is on a separate line, the semicolon isn't needed.</span></span> <span data-ttu-id="fa6d8-124">Beispielsweise werden in diesem Artikel **Schlüssel-Wert-Paare** in separaten Zeilen angeordnet und keine Semikola verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-124">For example, this article places **key-value** pairs on separate lines and doesn't use semicolons.</span></span>

<span data-ttu-id="fa6d8-125">Dieses Beispiel nutzt mehrere der **Schlüssel-Wert-Paare** des **FilterHashtable** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-125">This sample uses several of the **FilterHashtable** parameter's **key-value** pairs.</span></span> <span data-ttu-id="fa6d8-126">Die vollständige Abfrage beinhaltet **LogName** , **ProviderName** , **Keywords** , **ID** und **Level** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-126">The completed query includes **LogName** , **ProviderName** , **Keywords** , **ID** , and **Level** .</span></span>

<span data-ttu-id="fa6d8-127">Die akzeptierten **Schlüssel-Wert-Paare** sind in der folgenden Tabelle dargestellt und in der Dokumentation für den [Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable** -Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-127">The accepted **key-value** pairs are shown in the following table and are included in the documentation for the [Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable** parameter.</span></span>

<span data-ttu-id="fa6d8-128">In der folgenden Tabelle sind die Schlüsselnamen und Datentypen aufgelistet und ob für einen Datenwert Platzhalterzeichen akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-128">The following table displays the key names, data types, and whether wildcard characters are accepted for a data value.</span></span>

|    <span data-ttu-id="fa6d8-129">Schlüsselname</span><span class="sxs-lookup"><span data-stu-id="fa6d8-129">Key name</span></span>    | <span data-ttu-id="fa6d8-130">Wertdatentyp</span><span class="sxs-lookup"><span data-stu-id="fa6d8-130">Value data type</span></span> | <span data-ttu-id="fa6d8-131">Platzhalterzeichen akzeptiert?</span><span class="sxs-lookup"><span data-stu-id="fa6d8-131">Accepts wildcard characters?</span></span> |
| -------------- | --------------- | ---------------------------- |
| <span data-ttu-id="fa6d8-132">LogName</span><span class="sxs-lookup"><span data-stu-id="fa6d8-132">LogName</span></span>        | `<String[]>`    | <span data-ttu-id="fa6d8-133">Ja</span><span class="sxs-lookup"><span data-stu-id="fa6d8-133">Yes</span></span>                          |
| <span data-ttu-id="fa6d8-134">ProviderName</span><span class="sxs-lookup"><span data-stu-id="fa6d8-134">ProviderName</span></span>   | `<String[]>`    | <span data-ttu-id="fa6d8-135">Ja</span><span class="sxs-lookup"><span data-stu-id="fa6d8-135">Yes</span></span>                          |
| <span data-ttu-id="fa6d8-136">`Path`</span><span class="sxs-lookup"><span data-stu-id="fa6d8-136">Path</span></span>           | `<String[]>`    | <span data-ttu-id="fa6d8-137">Nein</span><span class="sxs-lookup"><span data-stu-id="fa6d8-137">No</span></span>                           |
| <span data-ttu-id="fa6d8-138">Keywords</span><span class="sxs-lookup"><span data-stu-id="fa6d8-138">Keywords</span></span>       | `<Long[]>`      | <span data-ttu-id="fa6d8-139">Nein</span><span class="sxs-lookup"><span data-stu-id="fa6d8-139">No</span></span>                           |
| <span data-ttu-id="fa6d8-140">id</span><span class="sxs-lookup"><span data-stu-id="fa6d8-140">ID</span></span>             | `<Int32[]>`     | <span data-ttu-id="fa6d8-141">Nein</span><span class="sxs-lookup"><span data-stu-id="fa6d8-141">No</span></span>                           |
| <span data-ttu-id="fa6d8-142">Ebene</span><span class="sxs-lookup"><span data-stu-id="fa6d8-142">Level</span></span>          | `<Int32[]>`     | <span data-ttu-id="fa6d8-143">Nein</span><span class="sxs-lookup"><span data-stu-id="fa6d8-143">No</span></span>                           |
| <span data-ttu-id="fa6d8-144">StartTime</span><span class="sxs-lookup"><span data-stu-id="fa6d8-144">StartTime</span></span>      | `<DateTime>`    | <span data-ttu-id="fa6d8-145">Nein</span><span class="sxs-lookup"><span data-stu-id="fa6d8-145">No</span></span>                           |
| <span data-ttu-id="fa6d8-146">EndTime</span><span class="sxs-lookup"><span data-stu-id="fa6d8-146">EndTime</span></span>        | `<DateTime>`    | <span data-ttu-id="fa6d8-147">Nein</span><span class="sxs-lookup"><span data-stu-id="fa6d8-147">No</span></span>                           |
| <span data-ttu-id="fa6d8-148">UserID</span><span class="sxs-lookup"><span data-stu-id="fa6d8-148">UserID</span></span>         | `<SID>`         | <span data-ttu-id="fa6d8-149">Nein</span><span class="sxs-lookup"><span data-stu-id="fa6d8-149">No</span></span>                           |
| <span data-ttu-id="fa6d8-150">Daten</span><span class="sxs-lookup"><span data-stu-id="fa6d8-150">Data</span></span>           | `<String[]>`    | <span data-ttu-id="fa6d8-151">Nein</span><span class="sxs-lookup"><span data-stu-id="fa6d8-151">No</span></span>                           |
| `<named-data>` | `<String[]>`    | <span data-ttu-id="fa6d8-152">Nein</span><span class="sxs-lookup"><span data-stu-id="fa6d8-152">No</span></span>                           |

<span data-ttu-id="fa6d8-153">Der `<named-data>`-Schlüssel stellt ein benanntes Ereignisdatenfeld dar.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-153">The `<named-data>` key represents a named event data field.</span></span> <span data-ttu-id="fa6d8-154">Beispielsweise kann das Perflib-Ereignis 1008 die folgenden Ereignisdaten enthalten:</span><span class="sxs-lookup"><span data-stu-id="fa6d8-154">For example, the Perflib event 1008 can contain the following event data:</span></span>

```xml
<EventData>
  <Data Name="Service">BITS</Data>
  <Data Name="Library">C:\Windows\System32\bitsperf.dll</Data>
  <Data Name="Win32Error">2</Data>
</EventData>
```

<span data-ttu-id="fa6d8-155">Sie können diese Ereignisse mit dem folgenden Befehl abfragen:</span><span class="sxs-lookup"><span data-stu-id="fa6d8-155">You can query for these events using the following command:</span></span>

```powershell
Get-WinEvent -FilterHashtable @{LogName='Application'; 'Service'='Bits'}
```

> [!NOTE]
> <span data-ttu-id="fa6d8-156">Ab PowerShell 6 ist das Abfragen von `<named-data>` möglich.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-156">The ability to query for `<named-data>` was added in PowerShell 6.</span></span>

## <a name="building-a-query-with-a-hash-table"></a><span data-ttu-id="fa6d8-157">Erstellen einer Abfrage mit einer Hashtabelle</span><span class="sxs-lookup"><span data-stu-id="fa6d8-157">Building a query with a hash table</span></span>

<span data-ttu-id="fa6d8-158">Es ist sinnvoll, die Hashtabelle aus jeweils einzelnen **Schlüssel-Wert-Paaren** aufzubauen, um die Ergebnisse zu überprüfen und Probleme zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-158">To verify results and troubleshoot problems, it helps to build the hash table one **key-value** pair at a time.</span></span> <span data-ttu-id="fa6d8-159">Die Abfrage ruft Daten aus dem **Anwendungsprotokoll** ab.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-159">The query gets data from the **Application** log.</span></span> <span data-ttu-id="fa6d8-160">Die Hashtabelle ist gleichbedeutend mit `Get-WinEvent –LogName Application`.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-160">The hash table is equivalent to `Get-WinEvent –LogName Application`.</span></span>

<span data-ttu-id="fa6d8-161">Erstellen Sie zunächst die `Get-WinEvent`-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-161">To begin, create the `Get-WinEvent` query.</span></span> <span data-ttu-id="fa6d8-162">Verwenden Sie das **Schlüssel-Wert-Paar** des **FilterHashtable** -Parameters mit dem Schlüssel **LogName** und dem Wert **Application** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-162">Use the **FilterHashtable** parameter's **key-value** pair with the key, **LogName** , and the value, **Application** .</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
}
```

<span data-ttu-id="fa6d8-163">Setzen Sie den Aufbau der Hashtabelle mit dem Schlüssel **ProviderName** fort.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-163">Continue to build the hash table with the **ProviderName** key.</span></span> <span data-ttu-id="fa6d8-164">Der **ProviderName** ist der Name, der im Feld **Source** in der **Windows-Ereignisanzeige** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-164">The **ProviderName** is the name that appears in the **Source** field in the **Windows Event Viewer** .</span></span> <span data-ttu-id="fa6d8-165">Beispielsweise **.NET Runtime** im folgenden Screenshot:</span><span class="sxs-lookup"><span data-stu-id="fa6d8-165">For example, **.NET Runtime** in the following screenshot:</span></span>

![Abbildung der Quellen der Windows-Ereignisanzeige](./media/creating-get-winEvent-queries-with-filterhashtable/providername.png)

<span data-ttu-id="fa6d8-167">Aktualisieren Sie die Hashtabelle, und schließen Sie das **Schlüssel-Wert** -Paar mit dem Schlüssel **ProviderName** und dem Wert **.NET Runtime** ein.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-167">Update the hash table and include the **key-value** pair with the key, **ProviderName** , and the value, **.NET Runtime** .</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
}
```

<span data-ttu-id="fa6d8-168">Wenn Ihre Abfrage Daten aus archivierten Ereignisprotokollen abrufen muss, verwenden Sie den Schlüssel **Path** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-168">If your query needs to get data from archived event logs, use the **Path** key.</span></span> <span data-ttu-id="fa6d8-169">Der Wert von **Path** gibt den vollständigen Pfad zur Protokolldatei an.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-169">The **Path** value specifies the full path to the log file.</span></span> <span data-ttu-id="fa6d8-170">Weitere Informationen finden Sie im **Scripting Guy** -Blogbeitrag [Use PowerShell to Parse Saved Event Logs for Errors](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors) (Verwenden von PowerShell zum Analysieren von gespeicherten Ereignisprotokollen auf Fehler).</span><span class="sxs-lookup"><span data-stu-id="fa6d8-170">For more information, see the **Scripting Guy** blog post, [Use PowerShell to Parse Saved Event Logs for Errors](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors).</span></span>

## <a name="using-enumerated-values-in-a-hash-table"></a><span data-ttu-id="fa6d8-171">Verwenden von Enumerationswerten in einer Hashtabelle</span><span class="sxs-lookup"><span data-stu-id="fa6d8-171">Using enumerated values in a hash table</span></span>

<span data-ttu-id="fa6d8-172">**Keywords** ist der nächste Schlüssel in der Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-172">**Keywords** is the next key in the hash table.</span></span> <span data-ttu-id="fa6d8-173">Der Datentyp **Keywords** ist ein Array vom Werttyp `[long]`, der eine große Zahl enthält.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-173">The **Keywords** data type is an array of the `[long]` value type that holds a large number.</span></span> <span data-ttu-id="fa6d8-174">Verwenden Sie den folgenden Befehl, um den Maximalwert von `[long]` zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="fa6d8-174">Use the following command to find the maximum value of `[long]`:</span></span>

```powershell
[long]::MaxValue
```

```Output
9223372036854775807
```

<span data-ttu-id="fa6d8-175">Für den Schlüssel **Keywords** verwendet PowerShell eine Zahl, nicht eine Zeichenfolge, wie etwa **Security** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-175">For the **Keywords** key, PowerShell uses a number, not a string such as **Security** .</span></span> <span data-ttu-id="fa6d8-176">In der **Windows-Ereignisanzeige** werden die **Schlüsselwörter** als Zeichenfolgen dargestellt, sie sind jedoch Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-176">**Windows Event Viewer** displays the **Keywords** as strings, but they are enumerated values.</span></span> <span data-ttu-id="fa6d8-177">Wenn Sie in der Hashtabelle den Schlüssel **Keywords** zusammen mit einem Zeichenfolgenwert verwenden, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-177">In the hash table, if you use the **Keywords** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="fa6d8-178">Öffnen Sie die **Windows-Ereignisanzeige** , und klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-178">Open the **Windows Event Viewer** and from the **Actions** pane, click on **Filter current log** .</span></span>
<span data-ttu-id="fa6d8-179">Im Dropdownmenü **Schlüsselwörter** werden die verfügbaren Schlüsselwörter angezeigt, wie im folgenden Screenshot zu sehen:</span><span class="sxs-lookup"><span data-stu-id="fa6d8-179">The **Keywords** drop-down menu displays the available keywords, as shown in the following screenshot:</span></span>

![Abbildung der Schlüsselwörter der Windows-Ereignisanzeige](./media/creating-get-winEvent-queries-with-filterhashtable/keywords.png)

<span data-ttu-id="fa6d8-181">Verwenden Sie den folgenden Befehl, um die Eigenschaftsnamen für `StandardEventKeywords` anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-181">Use the following command to display the `StandardEventKeywords` property names.</span></span>

```powershell
[System.Diagnostics.Eventing.Reader.StandardEventKeywords] | Get-Member -Static -MemberType Property
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.StandardEventKeywords
Name             MemberType Definition
—-             ———- ———-
AuditFailure     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
AuditSuccess     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
CorrelationHint  Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
CorrelationHint2 Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
EventLogClassic  Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
None             Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
ResponseTime     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
Sqm              Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
WdiContext       Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
WdiDiagnostic    Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
```

<span data-ttu-id="fa6d8-182">Die aufgezählten Werte sind im **.NET Framework** dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-182">The enumerated values are documented in the **.NET Framework** .</span></span> <span data-ttu-id="fa6d8-183">Weitere Informationen finden Sie unter [StandardEventKeywords Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords).</span><span class="sxs-lookup"><span data-stu-id="fa6d8-183">For more information, see [StandardEventKeywords Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords).</span></span>

<span data-ttu-id="fa6d8-184">Die Namen und Enumerationswerte der **Schlüsselwörter** sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fa6d8-184">The **Keywords** names and enumerated values are as follows:</span></span>

| <span data-ttu-id="fa6d8-185">Name</span><span class="sxs-lookup"><span data-stu-id="fa6d8-185">Name</span></span>             |  <span data-ttu-id="fa6d8-186">Wert</span><span class="sxs-lookup"><span data-stu-id="fa6d8-186">Value</span></span>            |
| ---------------- | ------------------|
| <span data-ttu-id="fa6d8-187">AuditFailure</span><span class="sxs-lookup"><span data-stu-id="fa6d8-187">AuditFailure</span></span>     | <span data-ttu-id="fa6d8-188">4503599627370496</span><span class="sxs-lookup"><span data-stu-id="fa6d8-188">4503599627370496</span></span>  |
| <span data-ttu-id="fa6d8-189">AuditSuccess</span><span class="sxs-lookup"><span data-stu-id="fa6d8-189">AuditSuccess</span></span>     | <span data-ttu-id="fa6d8-190">9007199254740992</span><span class="sxs-lookup"><span data-stu-id="fa6d8-190">9007199254740992</span></span>  |
| <span data-ttu-id="fa6d8-191">CorrelationHint2</span><span class="sxs-lookup"><span data-stu-id="fa6d8-191">CorrelationHint2</span></span> | <span data-ttu-id="fa6d8-192">18014398509481984</span><span class="sxs-lookup"><span data-stu-id="fa6d8-192">18014398509481984</span></span> |
| <span data-ttu-id="fa6d8-193">EventLogClassic</span><span class="sxs-lookup"><span data-stu-id="fa6d8-193">EventLogClassic</span></span>  | <span data-ttu-id="fa6d8-194">36028797018963968</span><span class="sxs-lookup"><span data-stu-id="fa6d8-194">36028797018963968</span></span> |
| <span data-ttu-id="fa6d8-195">Sqm</span><span class="sxs-lookup"><span data-stu-id="fa6d8-195">Sqm</span></span>              | <span data-ttu-id="fa6d8-196">2251799813685248</span><span class="sxs-lookup"><span data-stu-id="fa6d8-196">2251799813685248</span></span>  |
| <span data-ttu-id="fa6d8-197">WdiDiagnostic</span><span class="sxs-lookup"><span data-stu-id="fa6d8-197">WdiDiagnostic</span></span>    | <span data-ttu-id="fa6d8-198">1125899906842624</span><span class="sxs-lookup"><span data-stu-id="fa6d8-198">1125899906842624</span></span>  |
| <span data-ttu-id="fa6d8-199">WdiContext</span><span class="sxs-lookup"><span data-stu-id="fa6d8-199">WdiContext</span></span>       | <span data-ttu-id="fa6d8-200">562949953421312</span><span class="sxs-lookup"><span data-stu-id="fa6d8-200">562949953421312</span></span>   |
| <span data-ttu-id="fa6d8-201">ResponseTime</span><span class="sxs-lookup"><span data-stu-id="fa6d8-201">ResponseTime</span></span>     | <span data-ttu-id="fa6d8-202">281474976710656</span><span class="sxs-lookup"><span data-stu-id="fa6d8-202">281474976710656</span></span>   |
| <span data-ttu-id="fa6d8-203">Keine</span><span class="sxs-lookup"><span data-stu-id="fa6d8-203">None</span></span>             | <span data-ttu-id="fa6d8-204">0</span><span class="sxs-lookup"><span data-stu-id="fa6d8-204">0</span></span>                 |

<span data-ttu-id="fa6d8-205">Aktualisieren Sie die Hashtabelle, und schließen Sie das **Schlüssel-Wert-Paar** mit dem Schlüssel **Keywords** und dem **EventLogClassic** -Aufzählungswert **36028797018963968** ein.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-205">Update the hash table and include the **key-value** pair with the key, **Keywords** , and the **EventLogClassic** enumeration value, **36028797018963968** .</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
}
```

### <a name="keywords-static-property-value-optional"></a><span data-ttu-id="fa6d8-206">Statischer Eigenschaftswert der Keywords-Eigenschaft (optional)</span><span class="sxs-lookup"><span data-stu-id="fa6d8-206">Keywords static property value (optional)</span></span>

<span data-ttu-id="fa6d8-207">Der Schlüssel **Keywords** ist aufgezählt, Sie können in der Hashtabellenabfrage aber einen statischen Eigenschaftsnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-207">The **Keywords** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="fa6d8-208">Anstatt die zurückgegebene Zeichenfolge zu verwenden, muss der Eigenschaftsname mit der Eigenschaft **Value__** in einen Wert konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-208">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="fa6d8-209">Beispielsweise verwendet das folgende Skript die Eigenschaft **Value__** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-209">For example, the following script uses the **Value__** property.</span></span>

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventKeywords]::EventLogClassic
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=$C.Value__
}
```

## <a name="filtering-by-event-id"></a><span data-ttu-id="fa6d8-210">Filtern nach Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="fa6d8-210">Filtering by Event Id</span></span>

<span data-ttu-id="fa6d8-211">Um spezifischere Daten zu erhalten, werden die Ergebnisse der Abfrage nach der **Ereignis-ID** gefiltert. Auf die **Ereignis-ID** wird in der Hashtabelle in Form des Schlüssels **ID** Bezug genommen, und der Wert ist eine spezifische **Ereignis-ID** . In der **Windows-Ereignisanzeige** wird die **Ereignis-ID** angezeigt. In diesem Beispiel wird die **Ereignis-ID 1023** verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-211">To get more specific data, the query's results are filtered by **Event Id** . The **Event Id** is referenced in the hash table as the key **ID** and the value is a specific **Event Id** . The **Windows Event Viewer** displays the **Event Id** . This example uses **Event Id 1023** .</span></span>

<span data-ttu-id="fa6d8-212">Aktualisieren Sie die Hashtabelle, und schließen Sie das **Schlüssel-Wert-Paar** mit dem Schlüssel **ID** und dem Wert **1023** ein.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-212">Update the hash table and include the **key-value** pair with the key, **ID** and the value, **1023** .</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
}
```

## <a name="filtering-by-level"></a><span data-ttu-id="fa6d8-213">Filtern nach Ebene</span><span class="sxs-lookup"><span data-stu-id="fa6d8-213">Filtering by Level</span></span>

<span data-ttu-id="fa6d8-214">Um die Ergebnisse weiter einzugrenzen und nur Ereignisse aufzunehmen, die Fehler darstellen, verwenden Sie den Schlüssel **Level** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-214">To further refine the results and include only events that are errors, use the **Level** key.</span></span>
<span data-ttu-id="fa6d8-215">In der **Windows-Ereignisanzeige** wird der **Level** als Zeichenfolgenwert dargestellt, es handelt sich jedoch um Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-215">**Windows Event Viewer** displays the **Level** as string values, but they are enumerated values.</span></span> <span data-ttu-id="fa6d8-216">Wenn Sie in der Hashtabelle den Schlüssel **Level** zusammen mit einem Zeichenfolgenwert verwenden, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-216">In the hash table, if you use the **Level** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="fa6d8-217">**Level** weist Werte wie **Error** , **Warning** oder **Informational** auf.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-217">**Level** has values such as **Error** , **Warning** , or **Informational** .</span></span> <span data-ttu-id="fa6d8-218">Verwenden Sie den folgenden Befehl, um die Eigenschaftsnamen für `StandardEventLevel` anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-218">Use the following command to display the `StandardEventLevel` property names.</span></span>

```powershell
[System.Diagnostics.Eventing.Reader.StandardEventLevel] | Get-Member -Static -MemberType Property
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.StandardEventLevel

Name          MemberType Definition
----          ---------- ----------
Critical      Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Critical {get;}
Error         Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Error {get;}
Informational Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Informational {get;}
LogAlways     Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel LogAlways {get;}
Verbose       Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Verbose {get;}
Warning       Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Warning {get;}
```

<span data-ttu-id="fa6d8-219">Die aufgezählten Werte sind im **.NET Framework** dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-219">The enumerated values are documented in the **.NET Framework** .</span></span> <span data-ttu-id="fa6d8-220">Weitere Informationen finden Sie unter [StandardEventLevel Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel).</span><span class="sxs-lookup"><span data-stu-id="fa6d8-220">For more information, see [StandardEventLevel Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel).</span></span>

<span data-ttu-id="fa6d8-221">Die Namen und Enumerationswerte von **Level** sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fa6d8-221">The **Level** key's names and enumerated values are as follows:</span></span>

| <span data-ttu-id="fa6d8-222">Name</span><span class="sxs-lookup"><span data-stu-id="fa6d8-222">Name</span></span>           | <span data-ttu-id="fa6d8-223">Wert</span><span class="sxs-lookup"><span data-stu-id="fa6d8-223">Value</span></span> |
| -------------- | ----- |
| <span data-ttu-id="fa6d8-224">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="fa6d8-224">Verbose</span></span>        |   <span data-ttu-id="fa6d8-225">5</span><span class="sxs-lookup"><span data-stu-id="fa6d8-225">5</span></span>   |
| <span data-ttu-id="fa6d8-226">Informational</span><span class="sxs-lookup"><span data-stu-id="fa6d8-226">Informational</span></span>  |   <span data-ttu-id="fa6d8-227">4</span><span class="sxs-lookup"><span data-stu-id="fa6d8-227">4</span></span>   |
| <span data-ttu-id="fa6d8-228">Warnung</span><span class="sxs-lookup"><span data-stu-id="fa6d8-228">Warning</span></span>        |   <span data-ttu-id="fa6d8-229">3</span><span class="sxs-lookup"><span data-stu-id="fa6d8-229">3</span></span>   |
| <span data-ttu-id="fa6d8-230">Fehler</span><span class="sxs-lookup"><span data-stu-id="fa6d8-230">Error</span></span>          |   <span data-ttu-id="fa6d8-231">2</span><span class="sxs-lookup"><span data-stu-id="fa6d8-231">2</span></span>   |
| <span data-ttu-id="fa6d8-232">Kritisch</span><span class="sxs-lookup"><span data-stu-id="fa6d8-232">Critical</span></span>       |   <span data-ttu-id="fa6d8-233">1</span><span class="sxs-lookup"><span data-stu-id="fa6d8-233">1</span></span>   |
| <span data-ttu-id="fa6d8-234">LogAlways</span><span class="sxs-lookup"><span data-stu-id="fa6d8-234">LogAlways</span></span>      |   <span data-ttu-id="fa6d8-235">0</span><span class="sxs-lookup"><span data-stu-id="fa6d8-235">0</span></span>   |

<span data-ttu-id="fa6d8-236">Die Hash-Tabelle für die vollständige Abfrage enthält den Schlüssel **Level** und den Wert **2** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-236">The hash table for the completed query includes the key, **Level** , and the value, **2** .</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=2
}
```

### <a name="level-static-property-in-enumeration-optional"></a><span data-ttu-id="fa6d8-237">Statische Level-Eigenschaft in der Enumeration (optional)</span><span class="sxs-lookup"><span data-stu-id="fa6d8-237">Level static property in enumeration (optional)</span></span>

<span data-ttu-id="fa6d8-238">Der Schlüssel **Level** ist aufgezählt, Sie können in der Hashtabellenabfrage aber einen statischen Eigenschaftsnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-238">The **Level** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="fa6d8-239">Anstatt die zurückgegebene Zeichenfolge zu verwenden, muss der Eigenschaftsname mit der Eigenschaft **Value__** in einen Wert konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="fa6d8-239">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="fa6d8-240">Beispielsweise verwendet das folgende Skript die Eigenschaft **Value__** .</span><span class="sxs-lookup"><span data-stu-id="fa6d8-240">For example, the following script uses the **Value__** property.</span></span>

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventLevel]::Informational
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=$C.Value__
}
```
