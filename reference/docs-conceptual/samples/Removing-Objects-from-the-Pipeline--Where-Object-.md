---
ms.date: 12/23/2019
keywords: powershell,cmdlet
title: Entfernen von Objekten aus der Pipeline – Where-Object
description: Mit dem Where-Object-Cmdlet können Sie Objekte filtern, die an die Pipeline übergeben werden.
ms.openlocfilehash: e744dc671303711f1cbe8cc724a97c3327c1da85
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500112"
---
# <a name="removing-objects-from-the-pipeline-where-object"></a><span data-ttu-id="70e6f-104">Entfernen von Objekten aus der Pipeline (Where-Object)</span><span class="sxs-lookup"><span data-stu-id="70e6f-104">Removing Objects from the Pipeline (Where-Object)</span></span>

<span data-ttu-id="70e6f-105">In PowerShell geschieht es häufig, dass Sie mehr Objekte als gewünscht generieren und an eine Pipeline übergeben.</span><span class="sxs-lookup"><span data-stu-id="70e6f-105">In PowerShell, you often generate and pass along more objects to a pipeline than you want.</span></span> <span data-ttu-id="70e6f-106">Mithilfe der `Format-*`-Cmdlets können Sie die anzuzeigenden Eigenschaften bestimmter Objekte angeben, aber auf diese Weise ist es nicht möglich, ganze Objekte aus der Anzeige zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="70e6f-106">You can specify the properties of particular objects to display by using the `Format-*` cmdlets, but this does not help with the problem of removing entire objects from the display.</span></span> <span data-ttu-id="70e6f-107">Möglicherweise möchten Sie die Objekte vor dem Ende einer Pipeline filtern, um nur für eine Teilmenge der ursprünglich generierten Objekte bestimmte Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="70e6f-107">You may want to filter objects before the end of a pipeline, so you can perform actions on only a subset of the initially-generated objects.</span></span>

<span data-ttu-id="70e6f-108">PowerShell umfasst ein `Where-Object`-Cmdlet, mit dem Sie jedes Objekt in der Pipeline testen können, um es nur dann an die Pipeline zu übergeben, wenn es eine bestimmte Testbedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="70e6f-108">PowerShell includes a `Where-Object` cmdlet that allows you to test each object in the pipeline and only pass it along the pipeline if it meets a particular test condition.</span></span> <span data-ttu-id="70e6f-109">Objekte, die den Test nicht bestehen, werden aus der Pipeline entfernt.</span><span class="sxs-lookup"><span data-stu-id="70e6f-109">Objects that do not pass the test are removed from the pipeline.</span></span> <span data-ttu-id="70e6f-110">Sie geben die Testbedingung als Wert des Parameters **FilterScript** an.</span><span class="sxs-lookup"><span data-stu-id="70e6f-110">You supply the test condition as the value of the **FilterScript** parameter.</span></span>

## <a name="performing-simple-tests-with-where-object"></a><span data-ttu-id="70e6f-111">Ausführen einfacher Tests mit „Where-Object“</span><span class="sxs-lookup"><span data-stu-id="70e6f-111">Performing Simple Tests with Where-Object</span></span>

<span data-ttu-id="70e6f-112">Der Wert von **FilterScript** ist ein *Skriptblock* – d. h. mindestens ein in geschweiften Klammern eingeschlossener PowerShell-Befehl (`{}`) –, der als TRUE oder FALSE ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="70e6f-112">The value of **FilterScript** is a *script block* - one or more PowerShell commands surrounded by braces (`{}`) - that evaluates to true or false.</span></span> <span data-ttu-id="70e6f-113">Diese Skriptblöcke können sehr einfach sein, aber ihre Erstellung erfordert Kenntnisse eines anderen PowerShell-Konzepts: Vergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="70e6f-113">These script blocks can be very simple, but creating them requires knowing about another PowerShell concept, comparison operators.</span></span> <span data-ttu-id="70e6f-114">Mit einem Vergleichsoperator werden die Elemente auf den beiden Seiten des Operators verglichen.</span><span class="sxs-lookup"><span data-stu-id="70e6f-114">A comparison operator compares the items that appear on each side of it.</span></span> <span data-ttu-id="70e6f-115">Vergleichsoperatoren beginnen mit einem Minuszeichen (`-`), gefolgt von einem Namen.</span><span class="sxs-lookup"><span data-stu-id="70e6f-115">Comparison operators begin with a hyphen character (`-`) and are followed by a name.</span></span> <span data-ttu-id="70e6f-116">Die grundlegenden Vergleichsoperatoren können für nahezu jede Art von Objekt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70e6f-116">Basic comparison operators work on almost any kind of object.</span></span> <span data-ttu-id="70e6f-117">Die erweiterten Vergleichsoperatoren können möglicherweise nur mit Text oder Arrays verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70e6f-117">The more advanced comparison operators might only work on text or arrays.</span></span>

> [!NOTE]
> <span data-ttu-id="70e6f-118">Bei PowerShell-Vergleichsoperatoren wird beim Arbeiten mit Text die Groß-/Kleinschreibung standardmäßig nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="70e6f-118">By default, when working with text, PowerShell comparison operators are case-insensitive.</span></span>

<span data-ttu-id="70e6f-119">Aus Analysegründen werden Symbole wie `<`, `>` und `=` nicht als Vergleichsoperatoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="70e6f-119">Due to parsing considerations, symbols such as `<`,`>`, and `=` are not used as comparison operators.</span></span> <span data-ttu-id="70e6f-120">Stattdessen bestehen Vergleichsoperatoren aus Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="70e6f-120">Instead, comparison operators are comprised of letters.</span></span> <span data-ttu-id="70e6f-121">In der folgenden Tabelle sind die grundlegenden Vergleichsoperatoren aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="70e6f-121">The basic comparison operators are listed in the following table.</span></span>

| <span data-ttu-id="70e6f-122">Vergleichsoperator</span><span class="sxs-lookup"><span data-stu-id="70e6f-122">Comparison Operator</span></span> |                  <span data-ttu-id="70e6f-123">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="70e6f-123">Meaning</span></span>                   |    <span data-ttu-id="70e6f-124">Beispiel (gibt „true“ zurück)</span><span class="sxs-lookup"><span data-stu-id="70e6f-124">Example (returns true)</span></span>    |
| ------------------- | ------------------------------------------ | ---------------------------- |
| <span data-ttu-id="70e6f-125">-eq</span><span class="sxs-lookup"><span data-stu-id="70e6f-125">-eq</span></span>                 | <span data-ttu-id="70e6f-126">Ist gleich</span><span class="sxs-lookup"><span data-stu-id="70e6f-126">is equal to</span></span>                                | <span data-ttu-id="70e6f-127">1 -eq 1</span><span class="sxs-lookup"><span data-stu-id="70e6f-127">1 -eq 1</span></span>                      |
| <span data-ttu-id="70e6f-128">-ne</span><span class="sxs-lookup"><span data-stu-id="70e6f-128">-ne</span></span>                 | <span data-ttu-id="70e6f-129">Ist ungleich</span><span class="sxs-lookup"><span data-stu-id="70e6f-129">Is not equal to</span></span>                            | <span data-ttu-id="70e6f-130">1 -ne 2</span><span class="sxs-lookup"><span data-stu-id="70e6f-130">1 -ne 2</span></span>                      |
| <span data-ttu-id="70e6f-131">-lt</span><span class="sxs-lookup"><span data-stu-id="70e6f-131">-lt</span></span>                 | <span data-ttu-id="70e6f-132">Ist kleiner als</span><span class="sxs-lookup"><span data-stu-id="70e6f-132">Is less than</span></span>                               | <span data-ttu-id="70e6f-133">1 -lt 2</span><span class="sxs-lookup"><span data-stu-id="70e6f-133">1 -lt 2</span></span>                      |
| <span data-ttu-id="70e6f-134">-le</span><span class="sxs-lookup"><span data-stu-id="70e6f-134">-le</span></span>                 | <span data-ttu-id="70e6f-135">Ist kleiner als oder gleich</span><span class="sxs-lookup"><span data-stu-id="70e6f-135">Is less than or equal to</span></span>                   | <span data-ttu-id="70e6f-136">1 -le 2</span><span class="sxs-lookup"><span data-stu-id="70e6f-136">1 -le 2</span></span>                      |
| <span data-ttu-id="70e6f-137">-gt</span><span class="sxs-lookup"><span data-stu-id="70e6f-137">-gt</span></span>                 | <span data-ttu-id="70e6f-138">Ist größer als</span><span class="sxs-lookup"><span data-stu-id="70e6f-138">Is greater than</span></span>                            | <span data-ttu-id="70e6f-139">2 -gt 1</span><span class="sxs-lookup"><span data-stu-id="70e6f-139">2 -gt 1</span></span>                      |
| <span data-ttu-id="70e6f-140">-ge</span><span class="sxs-lookup"><span data-stu-id="70e6f-140">-ge</span></span>                 | <span data-ttu-id="70e6f-141">Ist größer als oder gleich</span><span class="sxs-lookup"><span data-stu-id="70e6f-141">Is greater than or equal to</span></span>                | <span data-ttu-id="70e6f-142">2 -ge 1</span><span class="sxs-lookup"><span data-stu-id="70e6f-142">2 -ge 1</span></span>                      |
| <span data-ttu-id="70e6f-143">-like</span><span class="sxs-lookup"><span data-stu-id="70e6f-143">-like</span></span>               | <span data-ttu-id="70e6f-144">Entspricht (Platzhaltervergleich für Text)</span><span class="sxs-lookup"><span data-stu-id="70e6f-144">Is like (wildcard comparison for text)</span></span>     | <span data-ttu-id="70e6f-145">"file.doc" -like "f\*.do?"</span><span class="sxs-lookup"><span data-stu-id="70e6f-145">"file.doc" -like "f\*.do?"</span></span>    |
| <span data-ttu-id="70e6f-146">-notlike</span><span class="sxs-lookup"><span data-stu-id="70e6f-146">-notlike</span></span>            | <span data-ttu-id="70e6f-147">Entspricht nicht (Platzhaltervergleich für Text)</span><span class="sxs-lookup"><span data-stu-id="70e6f-147">Is not like (wildcard comparison for text)</span></span> | <span data-ttu-id="70e6f-148">"file.doc" -notlike "p\*.doc"</span><span class="sxs-lookup"><span data-stu-id="70e6f-148">"file.doc" -notlike "p\*.doc"</span></span> |
| <span data-ttu-id="70e6f-149">-contains</span><span class="sxs-lookup"><span data-stu-id="70e6f-149">-contains</span></span>           | <span data-ttu-id="70e6f-150">Enthält</span><span class="sxs-lookup"><span data-stu-id="70e6f-150">Contains</span></span>                                   | <span data-ttu-id="70e6f-151">1,2,3 -contains 1</span><span class="sxs-lookup"><span data-stu-id="70e6f-151">1,2,3 -contains 1</span></span>            |
| <span data-ttu-id="70e6f-152">-notcontains</span><span class="sxs-lookup"><span data-stu-id="70e6f-152">-notcontains</span></span>        | <span data-ttu-id="70e6f-153">Enthält nicht</span><span class="sxs-lookup"><span data-stu-id="70e6f-153">Does not contain</span></span>                           | <span data-ttu-id="70e6f-154">1,2,3 -notcontains 4</span><span class="sxs-lookup"><span data-stu-id="70e6f-154">1,2,3 -notcontains 4</span></span>         |

<span data-ttu-id="70e6f-155">In `Where-Object`-Skriptblöcken dient die spezielle Variable `$_` zum Verweisen auf das aktuelle Objekt in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="70e6f-155">`Where-Object` script blocks use the special variable `$_` to refer to the current object in the pipeline.</span></span> <span data-ttu-id="70e6f-156">Es folgt ein Beispiel für die Funktionsweise.</span><span class="sxs-lookup"><span data-stu-id="70e6f-156">Here is an example of how it works.</span></span> <span data-ttu-id="70e6f-157">Wenn Sie über eine Liste mit Zahlen verfügen und nur diejenigen zurückgegeben möchten, die kleiner als 3 sind, können Sie die Zahlen mit `Where-Object` folgendermaßen filtern:</span><span class="sxs-lookup"><span data-stu-id="70e6f-157">If you have a list of numbers, and only want to return the ones that are less than 3, you can use `Where-Object` to filter the numbers by typing:</span></span>

```
1,2,3,4 | Where-Object {$_ -lt 3}
1
2
```

## <a name="filtering-based-on-object-properties"></a><span data-ttu-id="70e6f-158">Filtern basierend auf Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="70e6f-158">Filtering Based on Object Properties</span></span>

<span data-ttu-id="70e6f-159">Da `$_` auf das aktuelle Pipelineobjekt verweist, können wir für unsere Tests auf seine Eigenschaften zugreifen.</span><span class="sxs-lookup"><span data-stu-id="70e6f-159">Since `$_` refers to the current pipeline object, we can access its properties for our tests.</span></span>

<span data-ttu-id="70e6f-160">Als Beispiel können wir uns die Klasse **Win32_SystemDriver** in WMI anschauen.</span><span class="sxs-lookup"><span data-stu-id="70e6f-160">As an example, we can look at the **Win32_SystemDriver** class in WMI.</span></span> <span data-ttu-id="70e6f-161">Möglicherweise gibt es in einem bestimmten System Hunderte von Systemtreibern, Sie sind aber vielleicht nur an einer bestimmten Auswahl von Systemtreibern interessiert, z. B. an den Treibern, die gerade ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="70e6f-161">There might be hundreds of system drivers on a particular system, but you might only be interested in a particular set of the system drivers, such as those which are currently running.</span></span> <span data-ttu-id="70e6f-162">Für die **Win32_SystemDriver** -Klasse lautet die relevante Eigenschaft **State** .</span><span class="sxs-lookup"><span data-stu-id="70e6f-162">For the **Win32_SystemDriver** class the relevant property is **State** .</span></span> <span data-ttu-id="70e6f-163">Sie können die Systemtreiber so filtern, dass nur die ausgeführten Treiber ausgewählt werden. Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="70e6f-163">You can filter the system drivers, selecting only the running ones by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq 'Running'}
```

<span data-ttu-id="70e6f-164">Dies erzeugt immer noch eine lange Liste.</span><span class="sxs-lookup"><span data-stu-id="70e6f-164">This still produces a long list.</span></span> <span data-ttu-id="70e6f-165">Vielleicht möchten Sie die Liste weiter filtern, um nur die Treiber auszuwählen, die automatisch gestartet werden. Hierzu testen Sie zusätzlich den **StartMode** -Wert:</span><span class="sxs-lookup"><span data-stu-id="70e6f-165">You may want to filter to only select the drivers set to start automatically by testing the **StartMode** value as well:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Auto"}
```

```Output
DisplayName : RAS Asynchronous Media Driver
Name        : AsyncMac
State       : Running
Status      : OK
Started     : True

DisplayName : Audio Stub Driver
Name        : audstub
State       : Running
Status      : OK
Started     : True
...
```

<span data-ttu-id="70e6f-166">Dadurch erhalten Sie eine Vielzahl von Informationen, die Sie nicht mehr benötigen, da bekannt ist, dass die Treiber ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="70e6f-166">This gives us a lot of information we no longer need because we know that the drivers are running.</span></span>
<span data-ttu-id="70e6f-167">In der Tat sind die einzigen Informationen, die Sie an dieser Stelle wahrscheinlich benötigen, der Name und der Anzeigename.</span><span class="sxs-lookup"><span data-stu-id="70e6f-167">In fact, the only information we probably need at this point are the name and the display name.</span></span> <span data-ttu-id="70e6f-168">Der folgende Befehl enthält nur diese zwei Eigenschaften, wodurch eine wesentlich vereinfachte Ausgabe erzeugt wird:</span><span class="sxs-lookup"><span data-stu-id="70e6f-168">The following command includes only those two properties, resulting in much simpler output:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Manual"} |
      Format-Table -Property Name,DisplayName
```

```Output
Name              DisplayName
----              -----------
AsyncMac               RAS Asynchronous Media Driver
bindflt                Windows Bind Filter Driver
bowser                 Browser
CompositeBus           Composite Bus Enumerator Driver
condrv                 Console Driver
HdAudAddService        Microsoft 1.1 UAA Function Driver for High Definition Audio Service
HDAudBus               Microsoft UAA Bus Driver for High Definition Audio
HidUsb                 Microsoft HID Class Driver
HTTP                   HTTP Service
igfx                   igfx
IntcDAud               Intel(R) Display Audio
intelppm               Intel Processor Driver
...
```

<span data-ttu-id="70e6f-169">Der Befehl oben umfasst zwei `Where-Object`-Elemente, die aber mithilfe des logischen Operators `-and` wie folgt in einem einzigen `Where-Object`-Element ausgedrückt werden können:</span><span class="sxs-lookup"><span data-stu-id="70e6f-169">There are two `Where-Object` elements in the above command, but they can be expressed in a single `Where-Object` element by using the `-and` logical operator, like this:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {($_.State -eq 'Running') -and ($_.StartMode -eq 'Manual')} |
    Format-Table -Property Name,DisplayName
```

<span data-ttu-id="70e6f-170">In der folgenden Tabelle sind die standardmäßigen logischen Operatoren aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="70e6f-170">The standard logical operators are listed in the following table.</span></span>

| <span data-ttu-id="70e6f-171">Logischer Operator</span><span class="sxs-lookup"><span data-stu-id="70e6f-171">Logical Operator</span></span> |                 <span data-ttu-id="70e6f-172">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="70e6f-172">Meaning</span></span>                  |  <span data-ttu-id="70e6f-173">Beispiel (gibt „true“ zurück)</span><span class="sxs-lookup"><span data-stu-id="70e6f-173">Example (returns true)</span></span>  |
| ---------------- | ---------------------------------------- | ------------------------ |
| <span data-ttu-id="70e6f-174">-and</span><span class="sxs-lookup"><span data-stu-id="70e6f-174">-and</span></span>             | <span data-ttu-id="70e6f-175">Logisches „Und“; „true“, wenn beide Seiten zutreffen</span><span class="sxs-lookup"><span data-stu-id="70e6f-175">Logical and; true if both sides are true</span></span> | <span data-ttu-id="70e6f-176">(1 -eq 1) -and (2 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="70e6f-176">(1 -eq 1) -and (2 -eq 2)</span></span> |
| <span data-ttu-id="70e6f-177">-or</span><span class="sxs-lookup"><span data-stu-id="70e6f-177">-or</span></span>              | <span data-ttu-id="70e6f-178">Logisches „Oder“; „true“, wenn eine der beiden Seiten zutrifft</span><span class="sxs-lookup"><span data-stu-id="70e6f-178">Logical or; true if either side is true</span></span>  | <span data-ttu-id="70e6f-179">(1 -eq 1) -or (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="70e6f-179">(1 -eq 1) -or (1 -eq 2)</span></span>  |
| <span data-ttu-id="70e6f-180">-not</span><span class="sxs-lookup"><span data-stu-id="70e6f-180">-not</span></span>             | <span data-ttu-id="70e6f-181">Logisches „Nicht“; kehrt „true“ und „false“ um</span><span class="sxs-lookup"><span data-stu-id="70e6f-181">Logical not; reverses true and false</span></span>     | <span data-ttu-id="70e6f-182">-not (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="70e6f-182">-not (1 -eq 2)</span></span>           |
| \!               | <span data-ttu-id="70e6f-183">Logisches „Nicht“; kehrt „true“ und „false“ um</span><span class="sxs-lookup"><span data-stu-id="70e6f-183">Logical not; reverses true and false</span></span>     | <span data-ttu-id="70e6f-184">\!(1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="70e6f-184">\!(1 -eq 2)</span></span>              |
