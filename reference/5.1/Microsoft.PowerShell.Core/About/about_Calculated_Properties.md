---
description: PowerShell bietet die Möglichkeit, neue Eigenschaften dynamisch hinzuzufügen und die Formatierung der Objekt Ausgabe in die Pipeline zu ändern.
Locale: en-US
ms.date: 10/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_calculated_properties?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Calculated_Properties
ms.openlocfilehash: 4dd7912c7e1a976e20f92093a47355f3a3291093
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223004"
---
# <a name="about-calculated-properties"></a>Informationen zu berechneten Eigenschaften

## <a name="short-description"></a>Kurze Beschreibung

PowerShell bietet die Möglichkeit, neue Eigenschaften dynamisch hinzuzufügen und die Formatierung der Objekt Ausgabe in die Pipeline zu ändern.

## <a name="long-description"></a>Lange Beschreibung

Eine Reihe von PowerShell-Cmdlets transformieren, Aggregieren oder verarbeiten Eingabe Objekte in Ausgabe Objekte mithilfe von Parametern, die das Hinzufügen neuer Eigenschaften zu diesen Ausgabe Objekten ermöglichen. Diese Parameter können verwendet werden, um basierend auf den Werten von Eingabe Objekten neue, berechnete Eigenschaften für Ausgabe Objekte zu generieren.
Die berechnete Eigenschaft wird durch eine [Hash Tabelle](about_hash_tables.md) definiert, die Schlüssel-Wert-Paare enthält, die den Namen der neuen Eigenschaft angeben, einen Ausdruck zum Berechnen des Werts und optionale Formatierungsinformationen.

## <a name="supported-cmdlets"></a>Unterstützte Cmdlets

Die folgenden Cmdlets unterstützen berechnete Eigenschaftswerte für den **Property** -Parameter. Die `Format-*` Cmdlets unterstützen auch berechnete Werte für den **GroupBy** -Parameter.

In der folgenden Liste werden die Cmdlets aufgelistet, die berechnete Eigenschaften und die Schlüssel-Wert-Paare unterstützen, die von den einzelnen Cmdlets unterstützt werden.

- `Compare-Object`
  - `expression`

- `ConvertTo-Html`
  - `name`/`label` -optional (in PowerShell 6. x hinzugefügt)
  - `expression`
  - `width` -optional
  - `alignment` -optional

- `Format-Custom`
  - `expression`
  - `depth` -optional

- `Format-List`
  - `name`/`label` -optional
  - `expression`
  - `formatstring` -optional

  Derselbe Satz von Schlüssel-Wert-Paaren gilt auch für berechnete Eigenschaftswerte, die an den **GroupBy** -Parameter für alle `Format-*` Cmdlets übergeben werden.

- `Format-Table`
  - `name`/`label` -optional
  - `expression`
  - `formatstring` -optional
  - `width` -optional
  - `alignment` -optional

- `Format-Wide`
  - `expression`
  - `formatstring` -optional

- `Group-Object`
  - `expression`

- `Measure-Object`
  - Unterstützt nur einen Skriptblock für den Ausdruck, nicht eine Hash Tabelle.
  - Wird in PowerShell 5,1 und älter nicht unterstützt.

- `Select-Object`
  - `name`/`label` -optional
  - `expression`

- `Sort-Object`
  - `expression`
  - `ascending`/`descending` -optional

> [!NOTE]
> Der Wert von `expression` kann ein Skriptblock anstelle einer Hash Tabelle sein. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#notes) ".

## <a name="hashtable-key-definitions"></a>Hash Tabellenschlüssel Definitionen

- `name`/`label` : Gibt den Namen der Eigenschaft an, die erstellt wird. Sie können `name` oder den zugehörigen Alias, `label` , austauschbar verwenden.
- `expression` : Ein Skriptblock, der zum Berechnen des Werts der neuen Eigenschaft verwendet wird.
- `alignment` -Wird von Cmdlets verwendet, die eine tabellarische Ausgabe erzeugt, um zu definieren, wie die Werte in einer Spalte angezeigt werden. Der Wert muss `'left'` , `'center'` oder sein `'right'` .
- `formatstring` : Gibt eine Format Zeichenfolge an, die definiert, wie der Wert für die Ausgabe formatiert wird. Weitere Informationen zu Format Zeichenfolgen finden Sie unter [Formatieren von Typen in .net](/dotnet/standard/base-types/formatting-types).
- `width` : Gibt die maximale Width-Spalte in einer Tabelle an, wenn der Wert angezeigt wird. Der Wert muss größer als sein `0` .
- `depth` -Der **tiefen** Parameter von `Format-Custom` gibt die Tiefe der Erweiterung für alle Eigenschaften an. `depth`Mit dem Schlüssel können Sie die Tiefe der Erweiterung pro Eigenschaft angeben.
- `ascending` / `descending` : Hiermit können Sie die Sortierreihenfolge für eine oder mehrere Eigenschaften angeben. Dies sind boolesche Werte.

Die Hash Tabelle-Schlüssel müssen nicht ausgeschrieben werden, solange das angegebene namens Präfix eindeutig ist. `n`Kann z. b. anstelle von verwendet werden `Name` und `e` kann anstelle von verwendet werden `Expression` .

## <a name="examples"></a>Beispiele

### <a name="compare-object"></a>Compare-Object

Mit berechneten Eigenschaften können Sie steuern, wie die Eigenschaften der Eingabe Objekte verglichen werden. In diesem Beispiel werden die Werte mit dem Ergebnis der arithmetischen Operation verglichen (Modulus von 2), anstatt die Werte direkt zu vergleichen.

```powershell
Compare-Object @{p=1} @{p=2} -property @{ Expression = { $_.p % 2 } }
```

```Output
 $_.p % 2  SideIndicator
---------- -------------
         0 =>
         1 <=
```

### <a name="convertto-html"></a>ConvertTo-Html

`ConvertTo-Html` kann eine Auflistung von-Objekten in eine HTML-Tabelle konvertieren.
Mit berechneten Eigenschaften können Sie steuern, wie die Tabelle dargestellt wird.

```powershell
Get-Alias |
  ConvertTo-Html Name,
                 Definition,
                 @{
                    expr={$_.Parameters.Keys.Count}
                    align='center'
                 } |
    Out-File .\aliases.htm -Force
```

In diesem Beispiel wird eine HTML-Tabelle erstellt, die eine Liste der PowerShell-Aliase und die number-Parameter für jeden Alias Befehl enthält. Die Werte der **parameterCount** -Spalte werden zentriert.

### <a name="format-custom"></a>Format-Custom

`Format-Custom` stellt eine benutzerdefinierte Ansicht eines Objekts in einem Format bereit, das einer Klassendefinition ähnelt. Komplexere Objekte können Elemente enthalten, die tief in komplexe Typen geschachtelt sind. Der **tiefen** Parameter von `Format-Custom` gibt die Tiefe der Erweiterung für alle Eigenschaften an. `depth`Mit dem Schlüssel können Sie die Tiefe der Erweiterung pro Eigenschaft angeben.

In diesem Beispiel vereinfacht der `depth` Schlüssel die benutzerdefinierte Ausgabe für das `Get-Date` Cmdlet. `Get-Date` Gibt ein **DateTime** -Objekt zurück. Die **Date** -Eigenschaft dieses Objekts ist auch ein **DateTime** -Objekt, sodass das-Objekt eingebettet ist.

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

### <a name="format-list"></a>Format-List

In diesem Beispiel verwenden wir berechnete Eigenschaften, um den Namen und das Format der Ausgabe von zu ändern `Get-ChildItem` .

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

### <a name="format-table"></a>Format-Table

In diesem Beispiel fügt die berechnete Eigenschaft eine **Typeigenschaft** hinzu, die verwendet wird, um die Dateien nach dem Inhaltstyp zu klassifizieren.

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

### <a name="format-wide"></a>Format-Wide

Mit dem- `Format-Wide` Cmdlet können Sie den Wert einer Eigenschaft für Objekte in einer Sammlung als mehrspaltige Liste anzeigen.

In diesem Beispiel möchten wir den Dateinamen und die Größe (in Kilobyte) als Breite Auflistung sehen. Da `Format-Wide` mehr als eine Eigenschaft nicht anzeigt, wird eine berechnete Eigenschaft verwendet, um den Wert von zwei Eigenschaften zu einem einzelnen Wert zu kombinieren.

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

### <a name="group-object"></a>Group-Object

Das- `Group-Object` Cmdlet zeigt Objekte in Gruppen basierend auf dem Wert einer angegebenen Eigenschaft an. In diesem Beispiel zählt die berechnete Eigenschaft die Anzahl der Dateien jedes Inhaltstyps.

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

### <a name="select-object"></a>Select-Object

Sie können berechnete Eigenschaften verwenden, um der Objekt Ausgabe mit dem-Cmdlet zusätzliche Elemente hinzuzufügen `Select-Object` . In diesem Beispiel werden die PowerShell-Aliase aufgelistet, die mit dem Buchstaben beginnen `C` . Mithilfe `Select-Object` von geben wir den Alias, das Cmdlet, dem er zugeordnet ist, und die Anzahl der für das Cmdlet definierten Parameter an. Mithilfe einer berechneten Eigenschaft können wir die **parameterCount** -Eigenschaft erstellen.

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

### <a name="sort-object"></a>Sort-Object

Mithilfe der berechneten Eigenschaften können Sie Daten in verschiedenen Reihen Folgen pro Eigenschaft sortieren. In diesem Beispiel werden Daten aus einer CSV-Datei in aufsteigender Reihenfolge nach **Datum** sortiert. Allerdings werden die Zeilen innerhalb jedes Datums in absteigender Reihenfolge nach **unitssold** sortiert.

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

## <a name="notes"></a>Notizen

- Sie können den Ausdrucks Skriptblock _direkt_ als Argument angeben, anstatt ihn als `Expression` Eintrag in einer Hash Tabelle anzugeben. Beispiel:

  ```powershell
  '1', '10', '2' | Sort-Object { [int] $_ }
  ```

  Dieses Beispiel eignet sich für Cmdlets, die keine Eigenschaft über den Schlüssel benötigen (oder unterstützen) `Name` , wie z `Sort-Object` . b `Group-Object` ., und `Measure-Object` .

  Für Cmdlets, die das Benennen der Eigenschaft unterstützen, wird der Skriptblock in eine Zeichenfolge konvertiert und als Name der Eigenschaft in der Ausgabe verwendet.

- `Expression` Skriptblöcke _werden in unter_ geordneten Bereichen ausgeführt, was bedeutet, dass die Variablen des Aufrufers nicht direkt geändert werden können.

- Die Pipeline Logik wird auf die Ausgabe von `Expression` Skript Blöcken angewendet. Dies bedeutet, dass die Ausgabe eines Arrays mit einem Element bewirkt, dass dieses Array entpackt wird.

- Bei den meisten Cmdlets werden Fehler in Ausdrucks Skript Blöcken in Ruhe Fällen ignoriert.
  Für `Sort-Object` werden Anweisungs abschließende und Skript Abbruch Fehler _ausgegeben_ , die-Anweisung wird jedoch nicht beendet.

## <a name="see-also"></a>Weitere Informationen

[about_Hash_Tables](about_hash_tables.md)

[Compare-Object](xref:Microsoft.PowerShell.Utility.Compare-Object)

[ConvertTo-Html](xref:Microsoft.PowerShell.Utility.ConvertTo-Html)

[Format-Custom](xref:Microsoft.PowerShell.Utility.Format-Custom)

[Format-List](xref:Microsoft.PowerShell.Utility.Format-List)

[Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table)

[Format-Wide](xref:Microsoft.PowerShell.Utility.Format-Wide)

[Group-Object](xref:Microsoft.PowerShell.Utility.Group-Object)

[Measure-Object](xref:Microsoft.PowerShell.Utility.Measure-Object)

[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object)

[Sort-Object](xref:Microsoft.PowerShell.Utility.Sort-Object)

[Formatieren von Typen in .NET](/dotnet/standard/base-types/formatting-types)
