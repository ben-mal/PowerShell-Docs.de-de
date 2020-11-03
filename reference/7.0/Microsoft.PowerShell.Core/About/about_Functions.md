---
description: Beschreibt das Erstellen und Verwenden von Funktionen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions
ms.openlocfilehash: 25ef4d3f12752bfabc47d6519988d0da3d5ab0db
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220676"
---
# <a name="about-functions"></a>Informationen zu Functions

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt das Erstellen und Verwenden von Funktionen in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

Eine Funktion ist eine Liste von PowerShell-Anweisungen, die einen Namen haben, den Sie zuweisen. Wenn Sie eine Funktion ausführen, geben Sie den Namen der Funktion ein. Die Anweisungen in der Liste werden so ausgeführt, als würden Sie Sie an der Eingabeaufforderung eingegeben haben.

Funktionen können so einfach wie die folgenden sein:

```powershell
function Get-PowerShellProcess { Get-Process PowerShell }
```

Eine Funktion kann auch so komplex sein wie ein Cmdlet oder ein Anwendungsprogramm.

Ebenso wie Cmdlets können Funktionen über Parameter verfügen. Die Parameter können benannte, Positions-, Switch-oder dynamische Parameter sein. Funktionsparameter können in der Befehlszeile oder in der Pipeline gelesen werden.

Funktionen können Werte zurückgeben, die angezeigt, Variablen zugewiesen oder an andere Funktionen oder Cmdlets übergeben werden können. Sie können auch einen Rückgabewert mit dem- `return` Schlüsselwort angeben. Das- `return` Schlüsselwort wirkt sich nicht auf andere Ausgaben aus, die von der Funktion zurückgegeben werden. Das- `return` Schlüsselwort beendet jedoch die-Funktion in dieser Zeile. Weitere Informationen finden Sie unter [about_Return](about_Return.md).

Die Anweisungs Liste der Funktion kann unterschiedliche Typen von Anweisungs Listen mit den Schlüsselwörtern `Begin` , `Process` und enthalten `End` . In dieser Anweisung werden Eingaben aus der Pipeline anders behandelt.

Ein Filter ist eine besondere Art von Funktion, die das `Filter` Schlüsselwort verwendet.

Funktionen können auch wie Cmdlets fungieren. Sie können eine Funktion erstellen, die genau wie ein Cmdlet funktioniert, ohne die Programmierung zu verwenden `C#` . Weitere Informationen finden Sie unter [about_Functions_Advanced](about_Functions_Advanced.md).

## <a name="syntax"></a>Syntax

Im folgenden finden Sie die Syntax für eine Funktion:

```
function [<scope:>]<name> [([type]$parameter1[,[type]$parameter2])]
{
  param([type]$parameter1 [,[type]$parameter2])
  dynamicparam {<statement list>}
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

Eine Funktion umfasst die folgenden Elemente:

- Ein- `Function` Schlüsselwort
- Ein Bereich (optional)
- Ein Name, den Sie auswählen
- Beliebig viele benannte Parameter (optional)
- Mindestens ein in geschweiften Klammern eingeschlossener PowerShell-Befehl `{}`

Weitere Informationen zum `Dynamicparam` -Schlüsselwort und zu dynamischen Parametern in-Funktionen finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

## <a name="simple-functions"></a>Einfache Funktionen

Funktionen müssen nicht kompliziert sein, um nützlich zu sein. Die einfachsten Funktionen haben das folgende Format:

```
function <function-name> {statements}
```

Die folgende Funktion startet beispielsweise PowerShell mit der Option als Administrator ausführen.

```powershell
function Start-PSAdmin {Start-Process PowerShell -Verb RunAs}
```

Geben Sie Folgendes ein, um die-Funktion zu verwenden: `Start-PSAdmin`

Um der Funktion Anweisungen hinzuzufügen, geben Sie jede Anweisung in einer separaten Zeile ein, oder verwenden Sie ein Semikolon, `;` um die Anweisungen zu trennen.

Die folgende Funktion findet z. b `.jpg` . alle Dateien in den Verzeichnissen des aktuellen Benutzers, die nach dem Startdatum geändert wurden.

```powershell
function Get-NewPix
{
  $start = Get-Date -Month 1 -Day 1 -Year 2010
  $allpix = Get-ChildItem -Path $env:UserProfile\*.jpg -Recurse
  $allpix | Where-Object {$_.LastWriteTime -gt $Start}
}
```

Sie können eine Toolbox mit nützlichen kleinen Funktionen erstellen. Fügen Sie diese Funktionen zum PowerShell-Profil hinzu, wie in [about_Profiles](about_Profiles.md) und weiter unten in diesem Thema beschrieben.

## <a name="function-names"></a>Funktionsnamen

Sie können einer Funktion einen beliebigen Namen zuweisen, aber Funktionen, die Sie für andere freigeben, sollten den Benennungs Regeln folgen, die für alle PowerShell-Befehle eingerichtet wurden.

Funktionsnamen sollten aus einem Verb-Substantiv-paar bestehen, in dem das Verb die von der Funktion ausgeführten Aktion identifiziert, und das Substantiv identifiziert das Element, auf dem das Cmdlet die Aktion ausführt.

Functions sollten die Standard Verben verwenden, die für alle PowerShell-Befehle genehmigt wurden. Diese Verben helfen uns, die Befehlsnamen für die Benutzer einfach, konsistent und leicht verständlich zu halten.

Weitere Informationen zu den standardmäßigen PowerShell-Verben finden Sie unter [genehmigte Verben](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) in der Microsoft-Dokumentation.

## <a name="functions-with-parameters"></a>Funktionen mit Parametern

Sie können Parameter mit Funktionen verwenden, einschließlich benannter Parameter, Positions Parameter, Schalter Parameter und dynamischer Parameter. Weitere Informationen zu dynamischen Parametern in Funktionen finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

### <a name="named-parameters"></a>benannten Parametern

Sie können beliebig viele benannte Parameter definieren. Sie können einen Standardwert für benannte Parameter einschließen, wie weiter unten in diesem Thema beschrieben.

Sie können Parameter innerhalb der geschweiften Klammern mithilfe des `Param` Schlüssel Worts definieren, wie in der folgenden Beispiel Syntax gezeigt:

```
function <name> {
  param ([type]$parameter1[,[type]$parameter2])
  <statement list>
}
```

Sie können Parameter auch außerhalb der geschweiften Klammern ohne das- `Param` Schlüsselwort definieren, wie in der folgenden Beispiel Syntax gezeigt:

```powershell
function <name> [([type]$parameter1[,[type]$parameter2])] {
  <statement list>
}
```

Im folgenden finden Sie ein Beispiel für diese alternative Syntax.

```powershell
Function Add-Numbers($one, $two) {
    $one + $two
}
```

Während die erste Methode bevorzugt wird, gibt es keinen Unterschied zwischen diesen beiden Methoden.

Wenn Sie die Funktion ausführen, wird der Wert, den Sie für einen Parameter angeben, einer Variablen zugewiesen, die den Parameternamen enthält. Der Wert dieser Variablen kann in der-Funktion verwendet werden.

Das folgende Beispiel ist eine Funktion mit dem Namen `Get-SmallFiles` . Diese Funktion verfügt über einen- `$Size` Parameter. Die-Funktion zeigt alle Dateien an, die kleiner als der Wert des `$Size` -Parameters sind, und schließt Verzeichnisse aus:

```powershell
function Get-SmallFiles {
  Param($Size)
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

In der-Funktion können Sie die- `$Size` Variable verwenden, bei der es sich um den für den-Parameter definierten Namen handelt.

Wenn Sie diese Funktion verwenden möchten, geben Sie den folgenden Befehl ein:

```powershell
Get-SmallFiles -Size 50
```

Sie können auch einen Wert für einen benannten Parameter ohne den Parameternamen eingeben.
Der folgende Befehl gibt z. b. das gleiche Ergebnis wie ein Befehl, der den **size** -Parameter benennt:

```powershell
Get-SmallFiles 50
```

Um einen Standardwert für einen Parameter zu definieren, geben Sie ein Gleichheitszeichen und den Wert nach dem Parameternamen ein, wie in der folgenden Variation des `Get-SmallFiles` Beispiels gezeigt:

```powershell
function Get-SmallFiles ($Size = 100) {
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

Wenn Sie `Get-SmallFiles` ohne einen Wert eingeben, wird von der-Funktion 100 zugewiesen `$size` . Wenn Sie einen Wert angeben, verwendet die Funktion diesen Wert.

Optional können Sie eine kurze Hilfe Zeichenfolge bereitstellen, die den Standardwert des Parameters beschreibt, indem Sie das **psdefaultvalue** -Attribut zur Beschreibung des Parameters hinzufügen und die **Help** -Eigenschaft von **psdefaultvalue** angeben. Fügen Sie zum Bereitstellen einer Hilfe Zeichenfolge, die den Standardwert (100) des **size** -Parameters in der `Get-SmallFiles` Funktion beschreibt, das **psdefaultvalue** -Attribut hinzu, wie im folgenden Beispiel gezeigt.

```powershell
function Get-SmallFiles {
  param (
      [PSDefaultValue(Help = '100')]
      $Size = 100
  )
}
```

Weitere Informationen zur **psdefaultvalue** -Attribut Klasse finden Sie unter [psdefaultvalue-Attribut](/dotnet/api/system.management.automation.psdefaultvalueattribute)Elemente.

### <a name="positional-parameters"></a>Positions Parameter

Ein Positions Parameter ist ein Parameter ohne Parameternamen. PowerShell verwendet die Reihenfolge der Parameterwerte, um jeden Parameterwert einem Parameter in der Funktion zuzuordnen.

Wenn Sie Positions Parameter verwenden, geben Sie einen oder mehrere Werte nach dem Funktionsnamen ein. Positions Parameterwerte werden der `$args` Array Variablen zugewiesen.
Der Wert, der auf den Funktionsnamen folgt, wird der ersten Position im `$args` Array zugewiesen `$args[0]` .

Die folgende `Get-Extension` Funktion fügt die `.txt` Dateinamenerweiterung einem Dateinamen hinzu, den Sie angeben:

```powershell
function Get-Extension {
  $name = $args[0] + ".txt"
  $name
}
```

```powershell
Get-Extension myTextFile
```

```Output
myTextFile.txt
```

### <a name="switch-parameters"></a>Parameter wechseln

Bei einem Switch handelt es sich um einen Parameter, der keinen Wert erfordert. Stattdessen geben Sie den Funktionsnamen gefolgt vom Namen des Switch-Parameters ein.

Um einen Switch-Parameter zu definieren, geben Sie den Typ `[switch]` vor dem Parameternamen an, wie im folgenden Beispiel gezeigt:

```powershell
function Switch-Item {
  param ([switch]$on)
  if ($on) { "Switch on" }
  else { "Switch off" }
}
```

Wenn Sie den `On` Switch-Parameter nach dem Funktionsnamen eingeben, zeigt die Funktion "Switch on" an. Ohne den Switch-Parameter wird "Switch Off" angezeigt.

```powershell
Switch-Item -on
```

```Output
Switch on
```

```powershell
Switch-Item
```

```Output
Switch off
```

Sie können einen **booleschen** Wert auch einem Switch zuweisen, wenn Sie die Funktion ausführen, wie im folgenden Beispiel gezeigt:

```powershell
Switch-Item -on:$true
```

```Output
Switch on
```

```powershell
Switch-Item -on:$false
```

```Output
Switch off
```

## <a name="using-splatting-to-represent-command-parameters"></a>Verwenden von splatting zur Darstellung von Befehlsparametern

Mithilfe von Verteilung können Sie die Parameter eines Befehls darstellen. Diese Funktion wird in Windows PowerShell 3,0 eingeführt.

Verwenden Sie diese Technik in Funktionen, die Befehle in der Sitzung aufzurufen. Sie müssen die Befehlsparameter nicht deklarieren oder aufzählen oder die Funktion ändern, wenn sich die Befehlsparameter ändern.

Die folgende Beispiel Funktion Ruft das `Get-Command` Cmdlet auf. Der Befehl verwendet `@Args` , um die Parameter von darzustellen `Get-Command` .

```powershell
function Get-MyCommand { Get-Command @Args }
```

Sie können alle Parameter von verwenden, `Get-Command` Wenn Sie die-Funktion aufzurufen `Get-MyCommand` . Die Parameter und Parameterwerte werden mithilfe von an den Befehl übergeben `@Args` .

```powershell
Get-MyCommand -Name Get-ChildItem
```

```Output
CommandType     Name                ModuleName
-----------     ----                ----------
Cmdlet          Get-ChildItem       Microsoft.PowerShell.Management
```

Die `@Args` Funktion verwendet den `$Args` automatischen Parameter, der nicht deklarierte Cmdlet-Parameter und Werte von verbleibenden Argumenten darstellt.

Weitere Informationen zum splatting finden Sie unter [about_Splatting](about_Splatting.md).

## <a name="piping-objects-to-functions"></a>Übergeben von Objekten an Funktionen

Jede Funktion kann Eingaben aus der Pipeline annehmen. Sie können steuern, wie eine Funktion Eingaben aus der Pipeline mit `Begin` den `Process` Schlüsselwörtern, und verarbeitet `End` . Die folgende Beispiel Syntax zeigt die drei Schlüsselwörter:

```
function <name> {
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

Die `Begin` Anweisungs Liste wird nur einmal am Anfang der Funktion ausgeführt.

> [!IMPORTANT]
> Wenn Ihre Funktion einen- `Begin` `Process` oder- `End` Block definiert, muss sich der gesamte Code innerhalb dieser Blöcke befinden. Wenn *ein* Block definiert ist, wird kein Code außerhalb der Blöcke erkannt.

Die `Process` Anweisungs Liste wird einmal für jedes Objekt in der Pipeline ausgeführt.
Während der- `Process` Block ausgeführt wird, wird jedes Pipeline Objekt der `$_` automatischen Variablen zugewiesen, einem Pipeline Objekt gleichzeitig.

Nachdem die Funktion alle Objekte in der Pipeline empfangen hat, wird die `End` Anweisungs Liste einmal ausgeführt. Wenn kein- `Begin` ,-oder-Schlüsselwort verwendet wird `Process` `End` , werden alle-Anweisungen wie eine `End` Anweisungs Liste behandelt.

Die folgende Funktion verwendet das- `Process` Schlüsselwort. Die-Funktion zeigt Beispiele aus der Pipeline an:

```powershell
function Get-Pipeline
{
  process {"The value is: $_"}
}
```

Um diese Funktion zu veranschaulichen, geben Sie eine durch Kommas getrennte Liste von Zahlen ein, wie im folgenden Beispiel gezeigt:

```powershell
1,2,4 | Get-Pipeline
```

```Output
The value is: 1
The value is: 2
The value is: 4
```

Wenn Sie eine Funktion in einer Pipeline verwenden, werden die an die Funktion weitergeleiteten Objekte der `$input` automatischen Variablen zugewiesen. Die-Funktion führt-Anweisungen mit dem- `Begin` Schlüsselwort aus, bevor Objekte aus der Pipeline stammen. Die Funktion führt-Anweisungen mit dem- `End` Schlüsselwort aus, nachdem alle-Objekte von der Pipeline empfangen wurden.

Das folgende Beispiel zeigt die `$input` Automatische Variable mit `Begin` den `End` Schlüsselwörtern und.

```powershell
function Get-PipelineBeginEnd
{
  begin {"Begin: The input is $input"}
  end {"End:   The input is $input" }
}
```

Wenn diese Funktion mithilfe der Pipeline ausgeführt wird, werden die folgenden Ergebnisse angezeigt:

```powershell
1,2,4 | Get-PipelineBeginEnd
```

```Output
Begin: The input is
End:   The input is 1 2 4
```

Wenn die- `Begin` Anweisung ausgeführt wird, verfügt die-Funktion nicht über die Eingabe aus der Pipeline. Die-Anweisung wird ausgeführt, `End` nachdem die-Funktion die-Werte aufweist.

Wenn die Funktion über ein `Process` Schlüsselwort verfügt, wird jedes Objekt in `$input` aus entfernt `$input` und zugewiesen `$_` . Das folgende Beispiel enthält eine `Process` Anweisungs Liste:

```powershell
function Get-PipelineInput
{
  process {"Processing:  $_ " }
  end {"End:   The input is: $input" }
}
```

In diesem Beispiel wird jedes Objekt, das an die Funktion weitergeleitet wird, an die `Process` Anweisungs Liste gesendet. Die- `Process` Anweisungen werden für jedes Objekt ausgeführt, ein Objekt gleichzeitig. Die `$input` Automatische Variable ist leer, wenn die Funktion das `End` Schlüsselwort erreicht.

```powershell
1,2,4 | Get-PipelineInput
```

```Output
Processing:  1
Processing:  2
Processing:  4
End:   The input is:
```

Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](about_Automatic_Variables.md#using-enumerators) .

## <a name="filters"></a>Filter

Ein Filter ist ein Funktionstyp, der für jedes Objekt in der Pipeline ausgeführt wird. Ein Filter ähnelt einer Funktion mit allen zugehörigen Anweisungen in einem- `Process` Block.

Die Syntax eines Filters lautet wie folgt:

```
filter [<scope:>]<name> {<statement list>}
```

Der folgende Filter nimmt Protokolleinträge aus der Pipeline und zeigt dann entweder den gesamten Eintrag oder nur den Nachrichten Teil des Eintrags an:

```powershell
filter Get-ErrorLog ([switch]$message)
{
  if ($message) { Out-Host -InputObject $_.Message }
  else { $_ }
}
```

## <a name="function-scope"></a>Funktionsbereich

Eine Funktion ist in dem Bereich vorhanden, in dem Sie erstellt wurde.

Wenn eine Funktion Teil eines Skripts ist, steht die Funktion den Anweisungen innerhalb dieses Skripts zur Verfügung. Standardmäßig ist eine Funktion in einem Skript an der Eingabeaufforderung nicht verfügbar.

Sie können den Gültigkeitsbereich einer Funktion angeben. Beispielsweise wird die-Funktion dem globalen Gültigkeitsbereich im folgenden Beispiel hinzugefügt:

```powershell
function global:Get-DependentSvs {
  Get-Service | Where-Object {$_.DependentServices}
}
```

Wenn sich eine Funktion im globalen Gültigkeitsbereich befindet, können Sie die-Funktion in Skripts, in Funktionen und in der Befehlszeile verwenden.

Funktionen erstellen in der Regel einen Bereich. Die Elemente, die in einer Funktion erstellt werden, z. b. Variablen, sind nur im Funktionsbereich vorhanden.

Weitere Informationen zum Gültigkeitsbereich von PowerShell finden Sie unter [about_Scopes](about_Scopes.md).

## <a name="finding-and-managing-functions-using-the-function-drive"></a>Suchen und Verwalten von Funktionen mit dem Function:-Laufwerk

Alle Funktionen und Filter in PowerShell werden automatisch auf dem Laufwerk gespeichert `Function:` . Dieses Laufwerk wird vom PowerShell- **Funktions** Anbieter verfügbar gemacht.

Wenn Sie auf das `Function:` Laufwerk verweisen, geben Sie einen Doppelpunkt nach der **Funktion** ein, genauso wie beim Verweisen auf das- `C` oder- `D` Laufwerk eines Computers.

Der folgende Befehl zeigt alle Funktionen in der aktuellen PowerShell-Sitzung an:

```powershell
Get-ChildItem function:
```

Die Befehle in der Funktion werden als Skriptblock in der Definition-Eigenschaft der Funktion gespeichert. Wenn Sie z. b. die Befehle in der Hilfe Funktion von PowerShell anzeigen möchten, geben Sie Folgendes ein:

```powershell
(Get-ChildItem function:help).Definition
```

Sie können auch die folgende Syntax verwenden.

```powershell
$function:help
```

Weitere Informationen zum `Function:` Laufwerk finden Sie im Hilfethema für den **Funktions** Anbieter. Geben Sie `Get-Help Function` ein.

## <a name="reusing-functions-in-new-sessions"></a>Wieder verwenden von Funktionen in neuen Sitzungen

Wenn Sie an der PowerShell-Eingabeaufforderung eine Funktion eingeben, wird die Funktion Teil der aktuellen Sitzung. Sie ist bis zum Ende der Sitzung verfügbar.

Wenn Sie Ihre Funktion in allen PowerShell-Sitzungen verwenden möchten, fügen Sie die Funktion Ihrem PowerShell-Profil hinzu. Weitere Informationen zu Profilen finden Sie unter [about_Profiles](about_Profiles.md).

Sie können Ihre Funktion auch in einer PowerShell-Skriptdatei speichern. Geben Sie Ihre Funktion in eine Textdatei ein, und speichern Sie die Datei mit der `.ps1` Dateinamenerweiterung.

## <a name="writing-help-for-functions"></a>Schreiben von Hilfe für Funktionen

Das- `Get-Help` Cmdlet ruft Hilfe für Funktionen sowie für Cmdlets, Anbieter und Skripts ab. Um Hilfe zu einer Funktion zu erhalten, geben Sie `Get-Help` gefolgt vom Funktionsnamen ein.

Wenn Sie beispielsweise Hilfe für die Funktion benötigen, geben Sie Folgendes ein `Get-MyDisks` :

```powershell
Get-Help Get-MyDisks
```

Sie können die Hilfe für eine Funktion mit einer der beiden folgenden Methoden schreiben:

- Comment-Based Hilfe zu Funktionen

  Erstellen Sie ein Hilfethema mithilfe von speziellen Schlüsselwörtern in den Kommentaren. Um eine Kommentar basierte Hilfe für eine Funktion zu erstellen, müssen die Kommentare am Anfang oder Ende des Funktions Texts oder in den Zeilen platziert werden, die dem Function-Schlüsselwort vorangestellt sind. Weitere Informationen zur Kommentar basierten Hilfe finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md).

- XML-Based Hilfe zu Funktionen

  Erstellen Sie ein XML-basiertes Hilfethema, z. b. den Typ, der in der Regel für Cmdlets erstellt wird. Die XML-basierte Hilfe ist erforderlich, wenn Sie Hilfe Themen in mehreren Sprachen lokalisieren.

  Um die Funktion dem XML-basierten Hilfethema zuzuordnen, verwenden Sie das `.ExternalHelp` Kommentar basierte Hilfe Schlüsselwort. Ohne dieses Schlüsselwort `Get-Help` kann das Funktions Hilfethema nicht finden, und Aufrufe von `Get-Help` für die Funktion geben nur automatisch generierte Hilfe zurück.

  Weitere Informationen zum- `ExternalHelp` Schlüsselwort finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md). Weitere Informationen zur XML-basierten Hilfe finden Sie unter [How to Write Cmdlet Help](https://go.microsoft.com/fwlink/?LinkID=123415) in der MSDN Library.

## <a name="see-also"></a>Weitere Informationen:

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Comment_Based_Help](about_Comment_Based_Help.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)

[about_Parameters](about_Parameters.md)

[about_Profiles](about_Profiles.md)

[about_Scopes](about_Scopes.md)

[about_Script_Blocks](about_Script_Blocks.md)

[about_Function_provider](about_Function_provider.md)
