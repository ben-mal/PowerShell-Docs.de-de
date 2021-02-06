---
description: PowerShell bietet die Möglichkeit, neue Eigenschaften dynamisch hinzuzufügen und die Formatierung der Objekt Ausgabe in die Pipeline zu ändern.
Locale: en-US
ms.date: 08/07/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_calculated_properties?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Calculated_Properties
ms.openlocfilehash: 1f7470a47a24b7c2b8265d180aac49cfec9031f6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602329"
---
# <a name="about-calculated-properties"></a><span data-ttu-id="07645-103">Informationen zu berechneten Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="07645-103">About calculated properties</span></span>

## <a name="short-description"></a><span data-ttu-id="07645-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07645-104">Short Description</span></span>

<span data-ttu-id="07645-105">PowerShell bietet die Möglichkeit, neue Eigenschaften dynamisch hinzuzufügen und die Formatierung der Objekt Ausgabe in die Pipeline zu ändern.</span><span class="sxs-lookup"><span data-stu-id="07645-105">PowerShell provides the ability to dynamically add new properties and alter the formatting of objects output to the pipeline.</span></span>

## <a name="long-description"></a><span data-ttu-id="07645-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07645-106">Long Description</span></span>

<span data-ttu-id="07645-107">Eine Reihe von PowerShell-Cmdlets transformieren, Aggregieren oder verarbeiten Eingabe Objekte in Ausgabe Objekte mithilfe von Parametern, die das Hinzufügen neuer Eigenschaften zu diesen Ausgabe Objekten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="07645-107">A number of PowerShell cmdlets transform, aggregate, or process input objects into output objects using parameters that allow the addition of new properties to those output objects.</span></span> <span data-ttu-id="07645-108">Diese Parameter können verwendet werden, um basierend auf den Werten von Eingabe Objekten neue, berechnete Eigenschaften für Ausgabe Objekte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="07645-108">These parameters can be used to generate new, calculated properties on output objects based on the values of input objects.</span></span>
<span data-ttu-id="07645-109">Die berechnete Eigenschaft wird durch eine [Hash Tabelle](about_hash_tables.md) definiert, die Schlüssel-Wert-Paare enthält, die den Namen der neuen Eigenschaft angeben, einen Ausdruck zum Berechnen des Werts und optionale Formatierungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="07645-109">The calculated property is defined by a [hashtable](about_hash_tables.md) containing key-value pairs that specify the name of the new property, an expression to calculate the value, and optional formatting information.</span></span>

## <a name="supported-cmdlets"></a><span data-ttu-id="07645-110">Unterstützte Cmdlets</span><span class="sxs-lookup"><span data-stu-id="07645-110">Supported cmdlets</span></span>

<span data-ttu-id="07645-111">Die folgenden Cmdlets unterstützen berechnete Eigenschaftswerte für den **Property** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="07645-111">The following cmdlets support calculated property values for the **Property** parameter.</span></span> <span data-ttu-id="07645-112">Die `Format-*` Cmdlets unterstützen auch berechnete Werte für den **GroupBy** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="07645-112">The `Format-*` cmdlets also support calculated values for the **GroupBy** parameter.</span></span>

<span data-ttu-id="07645-113">In der folgenden Liste werden die Cmdlets aufgelistet, die berechnete Eigenschaften und die Schlüssel-Wert-Paare unterstützen, die von den einzelnen Cmdlets unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="07645-113">The following list itemizes the cmdlets that support calculated properties and the key-value pairs that are supported by each cmdlet.</span></span>

- `Compare-Object`
  - `expression`

- `ConvertTo-Html`
  - <span data-ttu-id="07645-114">`name`/`label` -optional (in PowerShell 6. x hinzugefügt)</span><span class="sxs-lookup"><span data-stu-id="07645-114">`name`/`label` - optional (added in PowerShell 6.x)</span></span>
  - `expression`
  - <span data-ttu-id="07645-115">`width` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-115">`width` - optional</span></span>
  - <span data-ttu-id="07645-116">`alignment` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-116">`alignment` - optional</span></span>

- `Format-Custom`
  - `expression`
  - <span data-ttu-id="07645-117">`depth` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-117">`depth` - optional</span></span>

- `Format-List`
  - <span data-ttu-id="07645-118">`name`/`label` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-118">`name`/`label` - optional</span></span>
  - `expression`
  - <span data-ttu-id="07645-119">`formatstring` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-119">`formatstring` - optional</span></span>

  <span data-ttu-id="07645-120">Derselbe Satz von Schlüssel-Wert-Paaren gilt auch für berechnete Eigenschaftswerte, die an den **GroupBy** -Parameter für alle `Format-*` Cmdlets übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="07645-120">This same set of key-value pairs also apply to calculated property values passed to the **GroupBy** parameter for all `Format-*` cmdlets.</span></span>

- `Format-Table`
  - <span data-ttu-id="07645-121">`name`/`label` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-121">`name`/`label` - optional</span></span>
  - `expression`
  - <span data-ttu-id="07645-122">`formatstring` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-122">`formatstring` - optional</span></span>
  - <span data-ttu-id="07645-123">`width` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-123">`width` - optional</span></span>
  - <span data-ttu-id="07645-124">`alignment` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-124">`alignment` - optional</span></span>

- `Format-Wide`
  - `expression`
  - <span data-ttu-id="07645-125">`formatstring` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-125">`formatstring` - optional</span></span>

- `Group-Object`
  - `expression`

- `Measure-Object`
  - <span data-ttu-id="07645-126">Unterstützt nur einen Skriptblock für den Ausdruck, nicht eine Hash Tabelle.</span><span class="sxs-lookup"><span data-stu-id="07645-126">Only supports a script block for the expression, not a hashtable.</span></span>
  - <span data-ttu-id="07645-127">Wird in PowerShell 5,1 und älter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="07645-127">Not supported in PowerShell 5.1 and older.</span></span>

- `Select-Object`
  - <span data-ttu-id="07645-128">`name`/`label` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-128">`name`/`label` - optional</span></span>
  - `expression`

- `Sort-Object`
  - `expression`
  - <span data-ttu-id="07645-129">`ascending`/`descending` -optional</span><span class="sxs-lookup"><span data-stu-id="07645-129">`ascending`/`descending` - optional</span></span>

> [!NOTE]
> <span data-ttu-id="07645-130">Der Wert von `expression` kann ein Skriptblock anstelle einer Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="07645-130">The value of the `expression` can be a script block instead of a hashtable.</span></span> <span data-ttu-id="07645-131">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#notes) ".</span><span class="sxs-lookup"><span data-stu-id="07645-131">For more information, see the [Notes](#notes) section.</span></span>

## <a name="hashtable-key-definitions"></a><span data-ttu-id="07645-132">Hash Tabellenschlüssel Definitionen</span><span class="sxs-lookup"><span data-stu-id="07645-132">Hashtable key definitions</span></span>

- <span data-ttu-id="07645-133">`name`/`label` : Gibt den Namen der Eigenschaft an, die erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="07645-133">`name`/`label` - Specifies the name of the property being created.</span></span> <span data-ttu-id="07645-134">Sie können `name` oder den zugehörigen Alias, `label` , austauschbar verwenden.</span><span class="sxs-lookup"><span data-stu-id="07645-134">You can use `name` or its alias, `label`, interchangeably.</span></span>
- <span data-ttu-id="07645-135">`expression` : Ein Skriptblock, der zum Berechnen des Werts der neuen Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07645-135">`expression` - A script block used to calculate the value of the new property.</span></span>
- <span data-ttu-id="07645-136">`alignment` -Wird von Cmdlets verwendet, die eine tabellarische Ausgabe erzeugt, um zu definieren, wie die Werte in einer Spalte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="07645-136">`alignment` - Used by cmdlets that produce tabular output to define how the values are displayed in a column.</span></span> <span data-ttu-id="07645-137">Der Wert muss `'left'` , `'center'` oder sein `'right'` .</span><span class="sxs-lookup"><span data-stu-id="07645-137">The value must be `'left'`, `'center'`, or `'right'`.</span></span>
- <span data-ttu-id="07645-138">`formatstring` : Gibt eine Format Zeichenfolge an, die definiert, wie der Wert für die Ausgabe formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="07645-138">`formatstring` - Specifies a format string that defines how the value is formatted for output.</span></span> <span data-ttu-id="07645-139">Weitere Informationen zu Format Zeichenfolgen finden Sie unter [Formatieren von Typen in .net](/dotnet/standard/base-types/formatting-types).</span><span class="sxs-lookup"><span data-stu-id="07645-139">For more information about format strings, see [Format types in .NET](/dotnet/standard/base-types/formatting-types).</span></span>
- <span data-ttu-id="07645-140">`width` : Gibt die maximale Width-Spalte in einer Tabelle an, wenn der Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="07645-140">`width` - Specifies the maximum width column in a table when the value is displayed.</span></span> <span data-ttu-id="07645-141">Der Wert muss größer als sein `0` .</span><span class="sxs-lookup"><span data-stu-id="07645-141">The value must be greater than `0`.</span></span>
- <span data-ttu-id="07645-142">`depth` -Der **tiefen** Parameter von `Format-Custom` gibt die Tiefe der Erweiterung für alle Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="07645-142">`depth` - The **Depth** parameter of `Format-Custom` specifies the depth of expansion for all properties.</span></span> <span data-ttu-id="07645-143">`depth`Mit dem Schlüssel können Sie die Tiefe der Erweiterung pro Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="07645-143">The `depth` key allows you to specify the depth of expansion per property.</span></span>
- <span data-ttu-id="07645-144">`ascending` / `descending` : Hiermit können Sie die Sortierreihenfolge für eine oder mehrere Eigenschaften angeben.</span><span class="sxs-lookup"><span data-stu-id="07645-144">`ascending` / `descending` - Allows you to specify the order of sorting for one or more properties.</span></span> <span data-ttu-id="07645-145">Dies sind boolesche Werte.</span><span class="sxs-lookup"><span data-stu-id="07645-145">These are boolean values.</span></span>

<span data-ttu-id="07645-146">Die Hash Tabelle-Schlüssel müssen nicht ausgeschrieben werden, solange das angegebene namens Präfix eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="07645-146">The hashtable keys need not be spelled out as long as the specified name prefix is unambiguous.</span></span> <span data-ttu-id="07645-147">`n`Kann z. b. anstelle von verwendet werden `Name` und `e` kann anstelle von verwendet werden `Expression` .</span><span class="sxs-lookup"><span data-stu-id="07645-147">For example, `n` can be used in lieu of `Name` and `e` can be used in lieu of `Expression`.</span></span>

## <a name="examples"></a><span data-ttu-id="07645-148">Beispiele</span><span class="sxs-lookup"><span data-stu-id="07645-148">Examples</span></span>

### <a name="compare-object"></a><span data-ttu-id="07645-149">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="07645-149">Compare-Object</span></span>

<span data-ttu-id="07645-150">Mit berechneten Eigenschaften können Sie steuern, wie die Eigenschaften der Eingabe Objekte verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="07645-150">With calculated properties, you can control how the properties of the input objects are compared.</span></span> <span data-ttu-id="07645-151">In diesem Beispiel werden die Werte mit dem Ergebnis der arithmetischen Operation verglichen (Modulus von 2), anstatt die Werte direkt zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="07645-151">In this example, rather than comparing the values directly, the values are compared to the result of the arithmetic operation (modulus of 2).</span></span>

```powershell
Compare-Object @{p=1} @{p=2} -property @{ Expression = { $_.p % 2 } }
```

```Output
 $_.p % 2  SideIndicator
---------- -------------
         0 =>
         1 <=
```

### <a name="convertto-html"></a><span data-ttu-id="07645-152">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="07645-152">ConvertTo-Html</span></span>

<span data-ttu-id="07645-153">`ConvertTo-Html` kann eine Auflistung von-Objekten in eine HTML-Tabelle konvertieren.</span><span class="sxs-lookup"><span data-stu-id="07645-153">`ConvertTo-Html` can convert a collection of objects to an HTML table.</span></span>
<span data-ttu-id="07645-154">Mit berechneten Eigenschaften können Sie steuern, wie die Tabelle dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="07645-154">Calculated properties allow you to control how the table is presented.</span></span>

```powershell
Get-Alias |
  ConvertTo-Html Name,
                 Definition,
                 @{
                    name='ParameterCount'
                    expr={$_.Parameters.Keys.Count}
                    align='center'
                 } |
    Out-File .\aliases.htm -Force
```

<span data-ttu-id="07645-155">In diesem Beispiel wird eine HTML-Tabelle erstellt, die eine Liste der PowerShell-Aliase und die number-Parameter für jeden Alias Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="07645-155">This example creates an HTML table containing a list of PowerShell aliases and the number parameters for each aliased command.</span></span> <span data-ttu-id="07645-156">Die Werte der **parameterCount** -Spalte werden zentriert.</span><span class="sxs-lookup"><span data-stu-id="07645-156">The values of **ParameterCount** column are centered.</span></span>

### <a name="format-custom"></a><span data-ttu-id="07645-157">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="07645-157">Format-Custom</span></span>

<span data-ttu-id="07645-158">`Format-Custom` stellt eine benutzerdefinierte Ansicht eines Objekts in einem Format bereit, das einer Klassendefinition ähnelt.</span><span class="sxs-lookup"><span data-stu-id="07645-158">`Format-Custom` provides a custom view of an object in a format similar to a class definition.</span></span> <span data-ttu-id="07645-159">Komplexere Objekte können Elemente enthalten, die tief in komplexe Typen geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="07645-159">More complex objects can contain members that are deeply nested with complex types.</span></span> <span data-ttu-id="07645-160">Der **tiefen** Parameter von `Format-Custom` gibt die Tiefe der Erweiterung für alle Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="07645-160">The **Depth** parameter of `Format-Custom` specifies the depth of expansion for all properties.</span></span> <span data-ttu-id="07645-161">`depth`Mit dem Schlüssel können Sie die Tiefe der Erweiterung pro Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="07645-161">The `depth` key allows you to specify the depth of expansion per property.</span></span>

<span data-ttu-id="07645-162">In diesem Beispiel vereinfacht der `depth` Schlüssel die benutzerdefinierte Ausgabe für das `Get-Date` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="07645-162">In this example, the `depth` key simplifies the custom output for the `Get-Date` cmdlet.</span></span> <span data-ttu-id="07645-163">`Get-Date` Gibt ein **DateTime** -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="07645-163">`Get-Date` returns a **DateTime** object.</span></span> <span data-ttu-id="07645-164">Die **Date** -Eigenschaft dieses Objekts ist auch ein **DateTime** -Objekt, sodass das-Objekt eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="07645-164">The **Date** property of this object is also a **DateTime** object, so the object is nested.</span></span>

```powershell
Get-Date | Format-Custom @{expr={$_.Date};depth=1},TimeOfDay
```

```Output
class DateTime
{
  $_.Date =
    class DateTime
    {
      Date = 8/7/2020 12:00:00 AM
      Day = 7
      DayOfWeek = Friday
      DayOfYear = 220
      Hour = 0
      Kind = Local
      Millisecond = 0
      Minute = 0
      Month = 8
      Second = 0
      Ticks = 637323552000000000
      TimeOfDay = 00:00:00
      Year = 2020
      DateTime = Friday, August 07, 2020 12:00:00 AM
    }
  TimeOfDay =
    class TimeSpan
    {
      Ticks = 435031592302
      Days = 0
      Hours = 12
      Milliseconds = 159
      Minutes = 5
      Seconds = 3
      TotalDays = 0.503508787386574
      TotalHours = 12.0842108972778
      TotalMilliseconds = 43503159.2302
      TotalMinutes = 725.052653836667
      TotalSeconds = 43503.1592302
    }
}
```

### <a name="format-list"></a><span data-ttu-id="07645-165">Format-List</span><span class="sxs-lookup"><span data-stu-id="07645-165">Format-List</span></span>

<span data-ttu-id="07645-166">In diesem Beispiel verwenden wir berechnete Eigenschaften, um den Namen und das Format der Ausgabe von zu ändern `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="07645-166">In this example, we use calculated properties to change the name and format of the output from `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem *.json -File |
  Format-List Fullname,
              @{
                 name='Modified'
                 expression={$_.LastWriteTime}
                 formatstring='O'
              },
              @{
                 name='Size'
                 expression={$_.Length/1KB}
                 formatstring='N2'
              }
```

```Output
FullName : C:\Git\PS-Docs\PowerShell-Docs\.markdownlint.json
Modified : 2020-07-23T10:26:28.4092457-07:00
Size     : 2.40

FullName : C:\Git\PS-Docs\PowerShell-Docs\.openpublishing.publish.config.json
Modified : 2020-07-23T10:26:28.4092457-07:00
Size     : 2.25

FullName : C:\Git\PS-Docs\PowerShell-Docs\.openpublishing.redirection.json
Modified : 2020-07-27T13:05:24.3887629-07:00
Size     : 324.60
```

### <a name="format-table"></a><span data-ttu-id="07645-167">Format-Table</span><span class="sxs-lookup"><span data-stu-id="07645-167">Format-Table</span></span>

<span data-ttu-id="07645-168">In diesem Beispiel fügt die berechnete Eigenschaft eine **Typeigenschaft** hinzu, die verwendet wird, um die Dateien nach dem Inhaltstyp zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="07645-168">In this example, the calculated property adds a **Type** property used to classify the files by the content type.</span></span>

```powershell
Get-ChildItem -File |
  Sort-Object extension |
    Format-Table Name, Length -GroupBy @{
      name='Type'
      expression={
        switch ($_.extension) {
          '.md'   {'Content'}
          ''      {'Metacontent'}
          '.ps1'  {'Automation'}
          '.yml'  {'Automation'}
          default {'Configuration'}
        }
      }
    }
```

```Output
   Type: Metacontent

Name              Length
----              ------
ThirdPartyNotices   1229
LICENSE-CODE        1106
LICENSE            19047

   Type: Configuration

Name                                Length
----                                ------
.editorconfig                          183
.gitattributes                         419
.gitignore                             228
.markdownlint.json                    2456
.openpublishing.publish.config.json   2306
.openpublishing.redirection.json    332394
.localization-config                   232

   Type: Content

Name            Length
----            ------
README.md         3355
CONTRIBUTING.md    247

   Type: Automation

Name                      Length
----                      ------
.openpublishing.build.ps1    796
build.ps1                   7495
ci.yml                       645
ci-steps.yml                2035
daily.yml                   1271
```

### <a name="format-wide"></a><span data-ttu-id="07645-169">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="07645-169">Format-Wide</span></span>

<span data-ttu-id="07645-170">Mit dem- `Format-Wide` Cmdlet können Sie den Wert einer Eigenschaft für Objekte in einer Sammlung als mehrspaltige Liste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="07645-170">The `Format-Wide` cmdlet allows you to display the value of one property for objects in a collection as a multi-column list.</span></span>

<span data-ttu-id="07645-171">In diesem Beispiel möchten wir den Dateinamen und die Größe (in Kilobyte) als Breite Auflistung sehen.</span><span class="sxs-lookup"><span data-stu-id="07645-171">For this example, we want to see the filename and the size (in kilobytes) as a wide listing.</span></span> <span data-ttu-id="07645-172">Da `Format-Wide` mehr als eine Eigenschaft nicht anzeigt, wird eine berechnete Eigenschaft verwendet, um den Wert von zwei Eigenschaften zu einem einzelnen Wert zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="07645-172">Since `Format-Wide` does not display more than one property, we use a calculated property to combine the value of two properties into a single value.</span></span>

```powershell
Get-ChildItem -File |
  Format-Wide -Property @{e={'{0} ({1:N2}kb)' -f $_.name,($_.length/1kb)}}
```

```Output
.editorconfig (0.18kb)                          .gitattributes (0.41kb)
.gitignore (0.22kb)                             .localization-config (0.23kb)
.markdownlint.json (2.40kb)                     .openpublishing.build.ps1 (0.78kb)
.openpublishing.publish.config.json (2.25kb)    .openpublishing.redirection.json (324.60kb)
build.ps1 (7.32kb)                              ci.yml (0.63kb)
ci-steps.yml (1.99kb)                           CONTRIBUTING.md (0.24kb)
daily.yml (1.24kb)                              LICENSE (18.60kb)
LICENSE-CODE (1.08kb)                           README.md (3.28kb)
ThirdPartyNotices (1.20kb)
```

### <a name="group-object"></a><span data-ttu-id="07645-173">Group-Object</span><span class="sxs-lookup"><span data-stu-id="07645-173">Group-Object</span></span>

<span data-ttu-id="07645-174">Das- `Group-Object` Cmdlet zeigt Objekte in Gruppen basierend auf dem Wert einer angegebenen Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="07645-174">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span> <span data-ttu-id="07645-175">In diesem Beispiel zählt die berechnete Eigenschaft die Anzahl der Dateien jedes Inhaltstyps.</span><span class="sxs-lookup"><span data-stu-id="07645-175">In this example, the calculated property counts the number of files of each content type.</span></span>

```powershell
Get-ChildItem -File |
  Sort-Object extension |
    Group-Object -NoElement -Property @{
      expression={
        switch ($_.extension) {
          '.md'   {'Content'}
          ''      {'Metacontent'}
          '.ps1'  {'Automation'}
          '.yml'  {'Automation'}
          default {'Configuration'}
        }
      }
    }
```

```Output
Count Name
----- ----
    5 Automation
    7 Configuration
    2 Content
    3 Metacontent
```

### <a name="measure-object"></a><span data-ttu-id="07645-176">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="07645-176">Measure-Object</span></span>

<span data-ttu-id="07645-177">Das- `Measure-Object` Cmdlet berechnet die numerischen Eigenschaften von Objekten.</span><span class="sxs-lookup"><span data-stu-id="07645-177">The `Measure-Object` cmdlet calculates the numeric properties of objects.</span></span> <span data-ttu-id="07645-178">In diesem Beispiel verwenden wir eine berechnete Eigenschaft, um die Anzahl (**Summe**) der Zahlen (zwischen 1 und 10) abzurufen, die gleichmäßig durch 3 teilbar sind.</span><span class="sxs-lookup"><span data-stu-id="07645-178">In this example, we use a calculated property to get the count (**Sum**) of the numbers, between 1 and 10, that are evenly divisible by 3.</span></span>

```powershell
1..10 | Measure-Object -Property {($_ % 3) -eq 0} -Sum
```

```Output
Count             : 10
Average           :
Sum               : 3
Maximum           :
Minimum           :
StandardDeviation :
Property          : ($_ % 3) -eq 0
```

> [!NOTE]
> <span data-ttu-id="07645-179">Im Gegensatz zu anderen-Cmdlets `Measure-Object` akzeptiert keine Hash Tabelle für berechnete Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="07645-179">Unlike the other cmdlets, `Measure-Object` does not accept a hashtable for calculated properties.</span></span> <span data-ttu-id="07645-180">Sie müssen einen Skriptblock verwenden.</span><span class="sxs-lookup"><span data-stu-id="07645-180">You must use a script block.</span></span>

### <a name="select-object"></a><span data-ttu-id="07645-181">Select-Object</span><span class="sxs-lookup"><span data-stu-id="07645-181">Select-Object</span></span>

<span data-ttu-id="07645-182">Sie können berechnete Eigenschaften verwenden, um der Objekt Ausgabe mit dem-Cmdlet zusätzliche Elemente hinzuzufügen `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="07645-182">You can use calculated properties to add additional members to the objects output with the `Select-Object` cmdlet.</span></span> <span data-ttu-id="07645-183">In diesem Beispiel werden die PowerShell-Aliase aufgelistet, die mit dem Buchstaben beginnen `C` .</span><span class="sxs-lookup"><span data-stu-id="07645-183">In this example, we are listing the PowerShell aliases that begin with the letter `C`.</span></span> <span data-ttu-id="07645-184">Mithilfe `Select-Object` von geben wir den Alias, das Cmdlet, dem er zugeordnet ist, und die Anzahl der für das Cmdlet definierten Parameter an.</span><span class="sxs-lookup"><span data-stu-id="07645-184">Using `Select-Object`, we output the alias, the cmdlet it's mapped to, and a count for the number of parameters defined for the cmdlet.</span></span> <span data-ttu-id="07645-185">Mithilfe einer berechneten Eigenschaft können wir die **parameterCount** -Eigenschaft erstellen.</span><span class="sxs-lookup"><span data-stu-id="07645-185">Using a calculated property, we can create the **ParameterCount** property.</span></span>

```powershell
$aliases = Get-Alias c* |
  Select-Object Name,
                Definition,
                @{
                    name='ParameterCount'
                    expr={$_.Parameters.Keys.Count}
                }
$aliases | Get-Member
$aliases
```

```Output
   TypeName: Selected.System.Management.Automation.AliasInfo

Name           MemberType   Definition
----           ----------   ----------
Equals         Method       bool Equals(System.Object obj)
GetHashCode    Method       int GetHashCode()
GetType        Method       type GetType()
ToString       Method       string ToString()
Definition     NoteProperty string Definition=Get-Content
Name           NoteProperty string Name=cat
ParameterCount NoteProperty System.Int32 ParameterCount=21

Name    Definition         ParameterCount
----    ----------         --------------
cat     Get-Content                    21
cd      Set-Location                   15
cdd     Push-MyLocation                 1
chdir   Set-Location                   15
clc     Clear-Content                  20
clear   Clear-Host                      0
clhy    Clear-History                  17
cli     Clear-Item                     20
clp     Clear-ItemProperty             22
cls     Clear-Host                      0
clv     Clear-Variable                 19
cnsn    Connect-PSSession              29
compare Compare-Object                 20
copy    Copy-Item                      24
cp      Copy-Item                      24
cpi     Copy-Item                      24
cpp     Copy-ItemProperty              23
cvpa    Convert-Path                   13
```

### <a name="sort-object"></a><span data-ttu-id="07645-186">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="07645-186">Sort-Object</span></span>

<span data-ttu-id="07645-187">Mithilfe der berechneten Eigenschaften können Sie Daten in verschiedenen Reihen Folgen pro Eigenschaft sortieren.</span><span class="sxs-lookup"><span data-stu-id="07645-187">Using the calculated properties, you can sort data in different orders per property.</span></span> <span data-ttu-id="07645-188">In diesem Beispiel werden Daten aus einer CSV-Datei in aufsteigender Reihenfolge nach **Datum** sortiert.</span><span class="sxs-lookup"><span data-stu-id="07645-188">This example sorts data from a CSV file in ascending order by **Date**.</span></span> <span data-ttu-id="07645-189">Allerdings werden die Zeilen innerhalb jedes Datums in absteigender Reihenfolge nach **unitssold** sortiert.</span><span class="sxs-lookup"><span data-stu-id="07645-189">But within each date, it sorts the rows in descending order by **UnitsSold**.</span></span>

```powershell
Import-Csv C:\temp\sales-data.csv |
  Sort-Object Date, @{expr={$_.UnitsSold}; desc=$true}, Salesperson  |
    Select-Object Date, Salesperson, UnitsSold
```

```Output
Date       Salesperson UnitsSold
----       ----------- ---------
2020-08-01 Sally       3
2020-08-01 Anne        2
2020-08-01 Fred        1
2020-08-02 Anne        6
2020-08-02 Fred        2
2020-08-02 Sally       0
2020-08-03 Anne        5
2020-08-03 Sally       3
2020-08-03 Fred        1
2020-08-04 Anne        2
2020-08-04 Fred        2
2020-08-04 Sally       2
```

## <a name="notes"></a><span data-ttu-id="07645-190">Notizen</span><span class="sxs-lookup"><span data-stu-id="07645-190">Notes</span></span>

- <span data-ttu-id="07645-191">Sie können den Ausdrucks Skriptblock _direkt_ als Argument angeben, anstatt ihn als `Expression` Eintrag in einer Hash Tabelle anzugeben.</span><span class="sxs-lookup"><span data-stu-id="07645-191">You may specify the expression script block _directly_, as an argument, rather than specifying it as the `Expression` entry in a hashtable.</span></span> <span data-ttu-id="07645-192">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="07645-192">For example:</span></span>

  ```powershell
  '1', '10', '2' | Sort-Object { [int] $_ }
  ```

  <span data-ttu-id="07645-193">Dieses Beispiel eignet sich für Cmdlets, die keine Eigenschaft über den Schlüssel benötigen (oder unterstützen) `Name` , wie z `Sort-Object` . b `Group-Object` ., und `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="07645-193">This example is convenient for cmdlets that do not require (or support) naming a property via the `Name` key, such as `Sort-Object`, `Group-Object`, and `Measure-Object`.</span></span>

  <span data-ttu-id="07645-194">Für Cmdlets, die das Benennen der Eigenschaft unterstützen, wird der Skriptblock in eine Zeichenfolge konvertiert und als Name der Eigenschaft in der Ausgabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="07645-194">For cmdlets that support naming the property, the script block is converted to a string and used as the name of the property in the output.</span></span>

- <span data-ttu-id="07645-195">`Expression` Skriptblöcke _werden in unter_ geordneten Bereichen ausgeführt, was bedeutet, dass die Variablen des Aufrufers nicht direkt geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="07645-195">`Expression` script blocks run in _child_ scopes, meaning that the caller's variables cannot be directly modified.</span></span>

- <span data-ttu-id="07645-196">Die Pipeline Logik wird auf die Ausgabe von `Expression` Skript Blöcken angewendet.</span><span class="sxs-lookup"><span data-stu-id="07645-196">Pipeline logic is applied to the output from `Expression` script blocks.</span></span> <span data-ttu-id="07645-197">Dies bedeutet, dass die Ausgabe eines Arrays mit einem Element bewirkt, dass dieses Array entpackt wird.</span><span class="sxs-lookup"><span data-stu-id="07645-197">This means that outputting a single-element array causes that array to be unwrapped.</span></span>

- <span data-ttu-id="07645-198">Bei den meisten Cmdlets werden Fehler in Ausdrucks Skript Blöcken in Ruhe Fällen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="07645-198">For most cmdlets, errors inside expression script blocks are quietly ignored.</span></span>
  <span data-ttu-id="07645-199">Für `Sort-Object` werden Anweisungs abschließende und Skript Abbruch Fehler _ausgegeben_ , die-Anweisung wird jedoch nicht beendet.</span><span class="sxs-lookup"><span data-stu-id="07645-199">For `Sort-Object`, statement-terminating and script-terminating errors are _output_ but they do not terminate the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="07645-200">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07645-200">See Also</span></span>

[<span data-ttu-id="07645-201">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="07645-201">about_Hash_Tables</span></span>](about_hash_tables.md)

[<span data-ttu-id="07645-202">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="07645-202">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="07645-203">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="07645-203">ConvertTo-Html</span></span>](xref:Microsoft.PowerShell.Utility.ConvertTo-Html)

[<span data-ttu-id="07645-204">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="07645-204">Format-Custom</span></span>](xref:Microsoft.PowerShell.Utility.Format-Custom)

[<span data-ttu-id="07645-205">Format-List</span><span class="sxs-lookup"><span data-stu-id="07645-205">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)

[<span data-ttu-id="07645-206">Format-Table</span><span class="sxs-lookup"><span data-stu-id="07645-206">Format-Table</span></span>](xref:Microsoft.PowerShell.Utility.Format-Table)

[<span data-ttu-id="07645-207">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="07645-207">Format-Wide</span></span>](xref:Microsoft.PowerShell.Utility.Format-Wide)

[<span data-ttu-id="07645-208">Group-Object</span><span class="sxs-lookup"><span data-stu-id="07645-208">Group-Object</span></span>](xref:Microsoft.PowerShell.Utility.Group-Object)

[<span data-ttu-id="07645-209">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="07645-209">Measure-Object</span></span>](xref:Microsoft.PowerShell.Utility.Measure-Object)

[<span data-ttu-id="07645-210">Select-Object</span><span class="sxs-lookup"><span data-stu-id="07645-210">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="07645-211">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="07645-211">Sort-Object</span></span>](xref:Microsoft.PowerShell.Utility.Sort-Object)

[<span data-ttu-id="07645-212">Formatieren von Typen in .NET</span><span class="sxs-lookup"><span data-stu-id="07645-212">Format types in .NET</span></span>](/dotnet/standard/base-types/formatting-types)
