---
description: Beschreibt, wie Kommentar basierte Hilfe Themen für Funktionen und Skripts geschrieben werden.
keywords: powershell,cmdlet
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comment_based_help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comment_Based_Help
ms.openlocfilehash: c3e02edd6ca33f373b1632160e4a18dc4fb744f2
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94386970"
---
# <a name="about-comment-based-help"></a>Informationen zur Kommentar basierten Hilfe

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt, wie Kommentar basierte Hilfe Themen für Funktionen und Skripts geschrieben werden.

## <a name="long-description"></a>Lange Beschreibung

Sie können Kommentar basierte Hilfe Themen für Funktionen und Skripts schreiben, indem Sie besondere Hilfe Kommentar Schlüsselwörter verwenden.

Das Cmdlet " [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) " zeigt die Kommentar basierte Hilfe im gleichen Format an, in dem die Cmdlet-Hilfe Themen angezeigt werden, die aus XML-Dateien generiert werden. Benutzer können alle Parameter von `Get-Help` , wie z. b. " **ausführlich** ", " **vollständig** ", " **Beispiele** " und " **Online** ", verwenden, um den Inhalt der Kommentar basierten Hilfe anzuzeigen.

Sie können auch XML-basierte Hilfedateien für Funktionen und Skripts schreiben. `Get-Help`Verwenden Sie das-Schlüsselwort, um das Cmdlet für die Suche nach der XML-basierten Hilfedatei für eine Funktion oder ein Skript zu aktivieren `.ExternalHelp` . Ohne dieses Schlüsselwort `Get-Help` können keine XML-basierten Hilfe Themen für Funktionen oder Skripts gefunden werden.

In diesem Thema wird erläutert, wie Sie Hilfe Themen für Funktionen und Skripts schreiben. Weitere Informationen zum Anzeigen von Hilfe Themen für Funktionen und Skripts finden [Sie unter Get-Help](xref:Microsoft.PowerShell.Core.Get-Help).

Die Cmdlets " [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help) " und " [Save-Help](xref:Microsoft.PowerShell.Core.Save-Help) " funktionieren nur in XML-Dateien. Die aktualisierbare Hilfe unterstützt keine Kommentar basierten Hilfe Themen.

## <a name="syntax-for-comment-based-help"></a>Syntax für die Kommentar basierte Hilfe

Die Syntax für die Kommentar basierte Hilfe lautet wie folgt:

```
# .<help keyword>
# <help content>
```

oder

```
<#
.<help keyword>
<help content>
#>
```

Die Kommentar basierte Hilfe wird als eine Reihe von Kommentaren geschrieben. Sie können `#` vor jeder Zeile von Kommentaren ein Kommentar Symbol eingeben, oder Sie können das-Symbol und das-Symbol verwenden, `<#` `#>` um einen Kommentar Block zu erstellen. Alle Zeilen innerhalb des Kommentar Blocks werden als Kommentare interpretiert.

Alle Zeilen in einem Kommentar basierten Hilfethema müssen zusammenhängend sein. Wenn ein Kommentar basiertes Hilfethema einem Kommentar folgt, der nicht Teil des Hilfe Themas ist, muss mindestens eine Leerzeile zwischen der letzten nicht-Hilfe Kommentarzeile und dem Anfang der Kommentar basierten Hilfe vorhanden sein.

Schlüsselwörter definieren jeden Abschnitt der Kommentar basierten Hilfe. Jedem Kommentar basierten Hilfe Schlüsselwort wird ein Punkt vorangestellt `.` . Die Schlüsselwörter können in beliebiger Reihenfolge angezeigt werden. Beim Schlüsselwort Namen wird die Groß-/Kleinschreibung nicht beachtet.

Beispielsweise wird das- `.Description` Schlüsselwort vor einer Beschreibung einer Funktion oder eines Skripts vorangestellt.

```
<#
.Description
Get-Function displays the name and syntax of all functions in the session.
#>
```

Der Kommentar Block muss mindestens ein Schlüsselwort enthalten. Einige der Schlüsselwörter, wie z `.EXAMPLE` . b., können oft im gleichen Kommentar Block vorkommen. Der Hilfe Inhalt für jedes Schlüsselwort beginnt in der Zeile nach dem-Schlüsselwort und kann sich über mehrere Zeilen erstrecken.

## <a name="syntax-for-comment-based-help-in-functions"></a>Syntax für die Kommentar basierte Hilfe in Functions

Die Kommentar basierte Hilfe für eine Funktion kann an einem von dreispeicher Orten angezeigt werden:

- Am Anfang des Funktions Texts.
- Am Ende des Funktions Texts.
- Vor dem- `function` Schlüsselwort. Zwischen der letzten Zeile der Funktions Hilfe und dem-Schlüsselwort darf nicht mehr als eine Leerzeile vorhanden sein `function` .

Beispiel:

```powershell
function Get-Function
{
<#
.<help keyword>
<help content>
#>

  # function logic
}
```

oder

```powershell
function Get-Function
{
   # function logic

<#
.<help keyword>
<help content>
#>
}
```

oder

```powershell
<#
.<help keyword>
<help content>
#>
function Get-Function { }
```

## <a name="syntax-for-comment-based-help-in-scripts"></a>Syntax für die Kommentar basierte Hilfe in Skripts

Die Kommentar basierte Hilfe für ein Skript kann an einem der beiden folgenden Speicherorte im Skript angezeigt werden.

- Am Anfang der Skriptdatei. Der Skript Hilfe kann das Skript nur durch Kommentare und leere Zeilen vorangestellt werden.

  Wenn das erste Element im Skript Text (nach der Hilfe) eine Funktionsdeklaration ist, müssen zwischen dem Ende der Skript Hilfe und der Funktionsdeklaration mindestens zwei Leerzeilen vorhanden sein. Andernfalls wird die Hilfe als Hilfe für die Funktion interpretiert, nicht als Hilfe für das Skript.

- Am Ende der Skriptdatei. Wenn das Skript jedoch signiert ist, platzieren Sie die Kommentar basierte Hilfe am Anfang der Skriptdatei. Das Ende des Skripts wird vom Signatur Block belegt.

Beispiel:

```powershell
<#
.<help keyword>
<help content>
#>


function Get-Function { }
```

oder

```powershell
function Get-Function { }

<#
.<help keyword>
<help content>
#>
```

## <a name="syntax-for-comment-based-help-in-script-modules"></a>Syntax für die Kommentar basierte Hilfe in Skript Modulen

In einem Skript Modul `.psm1` verwendet die Kommentar basierte Hilfe die Syntax für Funktionen, nicht die Syntax für Skripts. Sie können die Skript Syntax nicht verwenden, um Hilfe für alle Funktionen bereitzustellen, die in einem Skript Modul definiert sind.

Wenn Sie z. b. das `.ExternalHelp` -Schlüsselwort verwenden, um die XML-basierten Hilfedateien für die Funktionen in einem Skript Modul zu identifizieren, müssen Sie `.ExternalHelp` jeder Funktion einen Kommentar hinzufügen.

```powershell
# .ExternalHelp <XML-file-name>
function <function-name>
{
  ...
}
```

## <a name="comment-based-help-keywords"></a>Kommentar basierte Hilfe Schlüsselwörter

Im folgenden finden Sie gültige Kommentar basierte Hilfe Schlüsselwörter. Sie werden in der Reihenfolge aufgelistet, in der Sie in der Regel in einem Hilfethema zusammen mit der vorgesehenen Verwendung angezeigt werden. Diese Schlüsselwörter können in beliebiger Reihenfolge in der Kommentar basierten Hilfe angezeigt werden, und es wird nicht zwischen Groß-und Kleinschreibung unterschieden.

### <a name="synopsis"></a>. Zusammenfassung

Eine kurze Beschreibung der Funktion oder des Skripts. Dieses Schlüsselwort kann nur einmal in jedem Thema verwendet werden.

### <a name="description"></a>. Beschreibung

Eine ausführliche Beschreibung der Funktion oder des Skripts. Dieses Schlüsselwort kann nur einmal in jedem Thema verwendet werden.

### <a name="parameter"></a>. Parame

Die Beschreibung eines Parameters. Fügen Sie `.PARAMETER` für jeden Parameter in der Funktion oder Skript Syntax ein Schlüsselwort hinzu.

Geben Sie den Parameternamen in derselben Zeile wie das `.PARAMETER` Schlüsselwort ein. Geben Sie die Parameter Beschreibung in den Zeilen nach dem `.PARAMETER` Schlüsselwort ein. Windows PowerShell interpretiert den gesamten Text zwischen der `.PARAMETER` Zeile und dem nächsten Schlüsselwort oder dem Ende des Kommentar Blocks als Teil der Parameter Beschreibung.
Die Beschreibung kann Absatz Umbrüche einschließen.

```
.PARAMETER  <Parameter-Name>
```

Die Parameter Schlüsselwörter können in beliebiger Reihenfolge im Kommentar Block angezeigt werden, aber die Funktion oder Skript Syntax bestimmt die Reihenfolge, in der die Parameter (und deren Beschreibungen) im Hilfethema angezeigt werden. Ändern Sie die-Syntax, um die Reihenfolge zu ändern.

Sie können auch eine Parameter Beschreibung angeben, indem Sie einen Kommentar in der Funktions-oder Skript Syntax direkt vor dem Variablennamen des Parameters platzieren. Damit dies funktioniert, müssen Sie auch über einen Kommentar Block mit mindestens einem Schlüsselwort verfügen.

Wenn Sie sowohl einen Syntax Kommentar als auch ein `.PARAMETER` Schlüsselwort verwenden, wird die Beschreibung `.PARAMETER` verwendet, die dem Schlüsselwort zugeordnet ist, und der Syntax Kommentar wird ignoriert.

```powershell
<#
.SYNOPSIS
    Short description here
#>
function Verb-Noun {
    [CmdletBinding()]
    param (
        # This is the same as .Parameter
        [string]$Computername
    )
    # Verb the Noun on the computer
}
```

### <a name="example"></a>. Beispiel

Ein Beispiel Befehl, der die Funktion oder das Skript verwendet, optional gefolgt von der Beispielausgabe und einer Beschreibung. Wiederholen Sie dieses Schlüsselwort für jedes Beispiel.

### <a name="inputs"></a>. Ungs

Die .NET-Typen von Objekten, die an die Funktion oder das Skript weitergeleitet werden können. Sie können auch eine Beschreibung der Eingabe Objekte einschließen.

### <a name="outputs"></a>. Ausgaben

Der .NET-Typ der Objekte, die vom Cmdlet zurückgegeben werden. Sie können auch eine Beschreibung der zurückgegebenen Objekte einschließen.

### <a name="notes"></a>. Anmerkungen

Zusätzliche Informationen über die Funktion oder das Skript.

### <a name="link"></a>. Verknüpfen

Der Name eines verwandten Themas. Der Wert wird in der Zeile unterhalb von angezeigt. Link "-Schlüsselwort und muss einem Kommentar Symbol vorangestellt sein, oder es muss `#` in den Kommentar Block eingeschlossen werden.

Wiederholen Sie das `.LINK` Schlüsselwort für jedes verwandte Thema.

Dieser Inhalt wird im Abschnitt Verwandte Links des Hilfe Themas angezeigt.

Das `.Link` Schlüsselwort Content kann auch eine Uniform Resource Identifier (URI) zu einer Online Version desselben Hilfe Themas enthalten. Die Online Version wird geöffnet, wenn Sie den **Online-** Parameter von verwenden `Get-Help` . Der URI muss mit "http" oder "https" beginnen.

### <a name="component"></a>. Zulieferern

Der Name der Technologie oder des Features, die bzw. das von der Funktion oder dem Skript verwendet wird bzw. mit dem Sie verknüpft ist. Der **Component** -Parameter von `Get-Help` verwendet diesen Wert, um die von zurückgegebenen Suchergebnisse zu filtern `Get-Help` .

### <a name="role"></a>. Spielen

Der Name der Benutzerrolle für das Hilfethema. Der **Role** -Parameter von `Get-Help` verwendet diesen Wert, um die von zurückgegebenen Suchergebnisse zu filtern `Get-Help` .

### <a name="functionality"></a>. Alitäts

Die Schlüsselwörter, die die beabsichtigte Verwendung der Funktion beschreiben. Der- **Funktions** Parameter von `Get-Help` verwendet diesen Wert, um die von zurückgegebenen Suchergebnisse zu filtern `Get-Help` .

### <a name="forwardhelptargetname"></a>. Forwardhelptargetname

Leitet das Hilfethema für den angegebenen Befehl um. Sie können Benutzer zu jedem beliebigen Hilfethema umleiten, einschließlich der Hilfe Themen für eine Funktion, ein Skript, ein Cmdlet oder einen Anbieter.

```powershell
# .FORWARDHELPTARGETNAME <Command-Name>
```

### <a name="forwardhelpcategory"></a>. Forwardhelpcategory

Gibt die Hilfe Kategorie des Elements in an `.ForwardHelpTargetName` . Gültige Werte sind `Alias` , `Cmdlet` , `HelpFile` , `Function` , `Provider` , `General` , `FAQ` , `Glossary` , `ScriptCommand` , `ExternalScript` , `Filter` oder `All` . Verwenden Sie dieses Schlüsselwort, um Konflikte zu vermeiden, wenn Befehle mit demselben Namen vorhanden sind.

```powershell
# .FORWARDHELPCATEGORY <Category>
```

### <a name="remotehelprunspace"></a>. Remotehelprunspace

Gibt eine Sitzung an, die das Hilfethema enthält. Geben Sie eine Variable ein, die ein **PSSession** -Objekt enthält. Dieses Schlüsselwort wird vom [Export-PSSession-](xref:Microsoft.PowerShell.Utility.Export-PSSession) Cmdlet verwendet, um die Hilfe Themen für die exportierten Befehle zu suchen.

```powershell
# .REMOTEHELPRUNSPACE <PSSession-variable>
```

### <a name="externalhelp"></a>. Externalhelp "

Gibt eine XML-basierte Hilfedatei für das Skript oder die Funktion an.

```powershell
# .EXTERNALHELP <XML Help File>
```

Das `.ExternalHelp` Schlüsselwort ist erforderlich, wenn eine Funktion oder ein Skript in XML-Dateien dokumentiert ist. Ohne dieses Schlüsselwort `Get-Help` kann die XML-basierte Hilfedatei für die Funktion oder das Skript nicht finden.

Das- `.ExternalHelp` Schlüsselwort hat Vorrang vor anderen Kommentar basierten Hilfe Schlüsselwörtern. Wenn `.ExternalHelp` vorhanden ist, wird von keine `Get-Help` Kommentar basierte Hilfe angezeigt, auch wenn kein Hilfethema gefunden werden kann, das mit dem Wert des `.ExternalHelp` Schlüssel Worts übereinstimmt.

Wenn die Funktion von einem Modul exportiert wird, legen Sie den Wert des- `.ExternalHelp` Schlüssel Worts auf einen Dateinamen ohne Pfad fest. `Get-Help` sucht nach dem angegebenen Dateinamen in einem sprachspezifischen Unterverzeichnis des Modul Verzeichnisses. Der Name der XML-basierten Hilfedatei für eine Funktion ist nicht erforderlich, aber es wird empfohlen, das folgende Format zu verwenden:

```
<ScriptModule.psm1>-help.xml
```

Wenn die Funktion nicht in einem Modul enthalten ist, fügen Sie einen Pfad zur XML-basierten Hilfedatei ein. Wenn der Wert einen Pfad enthält und der Pfad Benutzeroberflächen kulturspezifische Unterverzeichnisse enthält, `Get-Help` durchsucht die Unterverzeichnisse rekursiv nach einer XML-Datei mit dem Namen des Skripts oder der Funktion in Übereinstimmung mit den für Windows eingerichteten sprach Fall Back Standards, ebenso wie in einem Modul Verzeichnis.

Weitere Informationen zum XML-basierten Hilfedatei Format in der Cmdlet-Hilfe finden [Sie unter How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-comment-based-help-topics).

## <a name="autogenerated-content"></a>Automatisch generierter Inhalt

Der Name, die Syntax, die Parameterliste, die Parameter Attribut Tabelle, allgemeine Parameter und Hinweise werden vom `Get-Help` Cmdlet automatisch generiert.

### <a name="name"></a>Name

Der **namens** Abschnitt eines Funktions Hilfe Themas wird aus dem Funktionsnamen in der Funktions Syntax entnommen. Der **Name** eines Skript Hilfe Themas wird aus dem Skript Dateiname entnommen. Um den Namen oder die Groß Schreibung zu ändern, ändern Sie die Funktions Syntax oder den Dateinamen des Skripts.

### <a name="syntax"></a>Syntax

Der Abschnitt **Syntax** des Hilfe Themas wird aus der Funktion oder der Skript Syntax generiert. Um der Hilfe Themen Syntax Details hinzuzufügen, z. b. den .NET-Typ eines Parameters, fügen Sie der Syntax das Detail hinzu. Wenn Sie keinen Parametertyp angeben, wird der **Objekttyp** als Standardwert eingefügt.

### <a name="parameter-list"></a>Parameterliste

Die Parameterliste im Hilfethema wird aus der Funktions-oder Skript Syntax und aus den Beschreibungen generiert, die Sie mit dem- `.Parameter` Schlüsselwort hinzufügen. Die Funktionsparameter werden im **Parameter** Abschnitt des Hilfe Themas in derselben Reihenfolge angezeigt, in der Sie in der Funktion oder Skript Syntax angezeigt werden. Die Schreibweise und die Groß-/Kleinschreibung von Parameternamen werden auch aus der Syntax entnommen. Der durch das-Schlüsselwort angegebene Parameter Name ist nicht betroffen `.Parameter` .

### <a name="common-parameters"></a>Allgemeine Parameter

Die **allgemeinen Parameter** werden der Syntax und der Parameterliste des Hilfe Themas hinzugefügt, auch wenn Sie keine Auswirkung haben. Weitere Informationen zu den allgemeinen Parametern finden Sie unter [about_CommonParameters](about_CommonParameters.md).

### <a name="parameter-attribute-table"></a>Parameter Attribut Tabelle

`Get-Help` generiert die Tabelle mit Parameter Attributen, die angezeigt wird, wenn Sie den **Full** -Parameter oder **Parameter** -Parameter von verwenden `Get-Help` . Der Wert der Attribute **Required** , **Position** und **default** value wird aus der Funktion oder der Skript Syntax entnommen.

Standardwerte und ein Wert für Platzhalter **Zeichen annehmen** werden nicht in der Parameter-Attribut Tabelle angezeigt, auch wenn Sie in der Funktion oder im Skript definiert sind. Um Benutzer zu unterstützen, geben Sie diese Informationen in der Parameter Beschreibung an.

### <a name="remarks"></a>Hinweise

Der Abschnitt " **Hinweise** " des Hilfe Themas wird automatisch aus dem Namen der Funktion oder des Skripts generiert. Der Inhalt kann nicht geändert oder beeinflusst werden.

## <a name="examples"></a>Beispiele

### <a name="comment-based-help-for-a-function"></a>Kommentar basierte Hilfe für eine Funktion

Die folgende Beispiel Funktion enthält eine Kommentar basierte Hilfe:

```powershell
function Add-Extension
{
param ([string]$Name,[string]$Extension = "txt")
$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name.
Takes any strings for the file name or extension.

.PARAMETER Name
Specifies the file name.

.PARAMETER Extension
Specifies the extension. "Txt" is the default.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension
or file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

Die Ergebnisse lauten wie folgt:

```powershell
Get-Help -Name "Add-Extension" -Full
```

```Output
NAME

Add-Extension

SYNOPSIS

Adds a file name extension to a supplied name.

SYNTAX

Add-Extension [[-Name] <String>] [[-Extension] <String>]
[<CommonParameters>]

DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

PARAMETERS

-Name
Specifies the file name.

Required?                    false
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-Extension
Specifies the extension. "Txt" is the default.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type
"get-help about_commonparameters".

INPUTS
None. You cannot pipe objects to Add-Extension.

OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

Example 1

PS> extension -name "File"
File.txt

Example 2

PS> extension -name "File" -extension "doc"
File.doc

Example 3

PS> extension "File" "doc"
File.doc

RELATED LINKS

http://www.fabrikam.com/extension.html
Set-Item
```

### <a name="parameter-descriptions-in-function-syntax"></a>Parameter Beschreibungen in der Funktions Syntax

Dieses Beispiel ist mit dem vorherigen identisch, mit dem Unterschied, dass die Parameter Beschreibungen in die Funktions Syntax eingefügt werden. Dieses Format ist besonders nützlich, wenn die Beschreibungen kurz sind.

```powershell
function Add-Extension
{
param
(

[string]
#Specifies the file name.
$name,

[string]
#Specifies the file name extension. "Txt" is the default.
$extension = "txt"
)

$name = $name + "." + $extension
$name

<#
.SYNOPSIS

Adds a file name extension to a supplied name.

.DESCRIPTION

Adds a file name extension to a supplied name. Takes any strings for the
file name or extension.

.INPUTS

None. You cannot pipe objects to Add-Extension.

.OUTPUTS

System.String. Add-Extension returns a string with the extension or
file name.

.EXAMPLE

PS> extension -name "File"
File.txt

.EXAMPLE

PS> extension -name "File" -extension "doc"
File.doc

.EXAMPLE

PS> extension "File" "doc"
File.doc

.LINK

http://www.fabrikam.com/extension.html

.LINK

Set-Item
#>
}
```

### <a name="comment-based-help-for-a-script"></a>Kommentar basierte Hilfe für ein Skript

Das folgende Beispielskript enthält eine Kommentar basierte Hilfe. Beachten Sie die leeren Zeilen zwischen dem schließenden `#>` und der- `Param` Anweisung. In einem Skript, das keine `Param` -Anweisung enthält, müssen mindestens zwei Leerzeilen zwischen dem letzten Kommentar im Hilfethema und der ersten Funktionsdeklaration vorhanden sein. Ohne diese leeren Zeilen ordnet das `Get-Help` Hilfethema der Funktion zu, nicht dem Skript.

```powershell
<#
.SYNOPSIS

Performs monthly data updates.

.DESCRIPTION

The Update-Month.ps1 script updates the registry with new data generated
during the past month and generates a report.

.PARAMETER InputPath
Specifies the path to the CSV-based input file.

.PARAMETER OutputPath
Specifies the name and path for the CSV-based output file. By default,
MonthlyUpdates.ps1 generates a name from the date and time it runs, and
saves the output in the local directory.

.INPUTS

None. You cannot pipe objects to Update-Month.ps1.

.OUTPUTS

None. Update-Month.ps1 does not generate any output.

.EXAMPLE

PS> .\Update-Month.ps1

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

.EXAMPLE

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath `
C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
...
```

Der folgende Befehl ruft die Skript Hilfe ab. Da sich das Skript nicht in einem Verzeichnis befindet, das in der `$env:Path` Umgebungsvariablen aufgelistet ist, `Get-Help` muss der Befehl, mit dem die Skript Hilfe abgerufen wird, den Skript Pfad angeben.

```powershell
Get-Help -Path .\update-month.ps1 -Full
```

```Output
# NAME

C:\ps-test\Update-Month.ps1

# SYNOPSIS

Performs monthly data updates.

# SYNTAX

C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
<String>] [<CommonParameters>]

# DESCRIPTION

The Update-Month.ps1 script updates the registry with new data
generated during the past month and generates a report.

# PARAMETERS

-InputPath
Specifies the path to the CSV-based input file.

Required?                    true
Position?                    0
Default value
Accept pipeline input?       false
Accept wildcard characters?

-OutputPath
Specifies the name and path for the CSV-based output file. By
default, MonthlyUpdates.ps1 generates a name from the date
and time it runs, and saves the output in the local directory.

Required?                    false
Position?                    1
Default value
Accept pipeline input?       false
Accept wildcard characters?

<CommonParameters>
This cmdlet supports the common parameters: -Verbose, -Debug,
-ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
-OutBuffer and -OutVariable. For more information, type,
"get-help about_commonparameters".

# INPUTS

None. You cannot pipe objects to Update-Month.ps1.

# OUTPUTS

None. Update-Month.ps1 does not generate any output.

Example 1

PS> .\Update-Month.ps1

Example 2

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

Example 3

PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
C:\Reports\2009\January.csv

# RELATED LINKS
```

### <a name="redirecting-to-an-xml-file"></a>Umleiten an eine XML-Datei

Sie können XML-basierte Hilfe Themen für Funktionen und Skripts schreiben. Obwohl die Kommentar basierte Hilfe einfacher implementiert werden kann, ist die XML-basierte Hilfe für die aktualisierbare Hilfe und die Bereitstellung von Hilfe Themen in mehreren Sprachen erforderlich.

Das folgende Beispiel zeigt die ersten Zeilen des Update-Month.ps1 Skripts.
Das Skript verwendet das- `.ExternalHelp` Schlüsselwort, um den Pfad zu einem XML-basierten Hilfethema für das Skript anzugeben.

Beachten Sie, dass der Wert des- `.ExternalHelp` Schlüssel Worts in derselben Zeile wie das-Schlüsselwort angezeigt wird. Jede andere Platzierung ist wirkungslos.

```powershell
# .ExternalHelp C:\MyScripts\Update-Month-Help.xml

param ([string]$InputPath, [string]$OutPutPath)
function Get-Data { }
...
```

In den folgenden Beispielen werden drei gültige Platzierungs Werte des- `.ExternalHelp` Schlüssel Worts in einer-Funktion gezeigt.

```powershell
function Add-Extension
{
# .ExternalHelp C:\ps-test\Add-Extension.xml

param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

```powershell
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name

# .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

```powershell
# .ExternalHelp C:\ps-test\Add-Extension.xml
function Add-Extension
{
param ([string] $name, [string]$extension = "txt")
$name = $name + "." + $extension
$name
}
```

### <a name="redirecting-to-a-different-help-topic"></a>Umleiten an ein anderes Hilfethema

Der folgende Code ist ein Auszug aus dem Anfang der integrierten Hilfe Funktion in PowerShell, die jeweils einen Bildschirm von Hilfe Text anzeigt.
Da im Hilfethema für das `Get-Help` Cmdlet die Hilfe Funktion beschrieben wird, verwendet die Hilfe Funktion `.ForwardHelpTargetName` die `.ForwardHelpCategory` Schlüsselwörter und, um den Benutzer zum `Get-Help` Cmdlet-Hilfethema umzuleiten.

```powershell
function help
{

<#
.FORWARDHELPTARGETNAME Get-Help
.FORWARDHELPCATEGORY Cmdlet
#>
[CmdletBinding(DefaultParameterSetName='AllUsersView')]
param(
[Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
[System.String]
${Name},
...
```

Der folgende Befehl verwendet dieses Feature:

```powershell
Get-Help -Name help
```

```Output
NAME

Get-Help

SYNOPSIS

Displays information about PowerShell cmdlets and concepts.
...
```

## <a name="see-also"></a>Weitere Informationen

[about_Functions](about_Functions.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Scripts](about_Scripts.md)

[Vorgehensweise beim Schreiben von Cmdlet-Hilfe](https://go.microsoft.com/fwlink/?LinkID=123415)
