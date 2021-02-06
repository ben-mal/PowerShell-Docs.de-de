---
title: Styleguide für die PowerShell-Dokumentation
description: Dieser Artikel enthält die Stilregeln für das Schreiben von PowerShell-Dokumentation.
ms.date: 12/09/2020
ms.topic: conceptual
ms.openlocfilehash: 6f23f63cffc9fed9cbbcf84539875bfaf4247732
ms.sourcegitcommit: 61765d08321623743dc5db5367160f6982fe7857
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "99596530"
---
# <a name="powershell-docs-style-guide"></a>Styleguide für die PowerShell-Dokumentation

Dieser Artikel enthält die spezifischen Stilanweisungen für Inhalte der PowerShell-Dokumentation. Es basiert auf den Informationen, die in der [Übersicht](overview.md#get-started-writing-docs)beschrieben werden.

## <a name="product-terminology"></a>Produktterminologie

Es gibt mehrere Varianten von PowerShell.

- **PowerShell**: Dies ist die Standardvariante. Wir sehen uns an, dass PowerShell 7 und darüber hinaus die richtige PowerShell ist.
- **PowerShell Core-** : PowerShell basierend auf .NET Core. Die Verwendung des Begriffs " **Core** " sollte auf Fälle beschränkt werden, in denen er von Windows PowerShell unterschieden werden muss.
- **Windows PowerShell**:- PowerShell basierend auf .NET Framework. Windows PowerShell wird nur für Windows ausgeliefert und erfordert das gesamte Framework.

  Im Allgemeinen können Verweise auf "Windows PowerShell" in der-Dokumentation in _PowerShell_ geändert werden.
  "Windows PowerShell" sollte bei der Erörterung von _Windows PowerShell_-spezifischem Verhalten verwendet werden.

Verwandte Produkte

- **Visual Studio Code (vs Code)** : Dies ist der kostenlose Open Source-Editor von Microsoft. Bei der ersten Erwähnung sollte der vollständige Name verwendet werden. Anschließend können Sie **VS Code** verwenden. Verwenden Sie "vscode" nicht.
- **PowerShell-Erweiterung für Visual Studio Code**: Mit dieser Erweiterung wird VS Code in die bevorzugte IDE für PowerShell umgewandelt. Bei der ersten Erwähnung sollte der vollständige Name verwendet werden. Anschließend können Sie **PowerShell-Erweiterung** verwenden.
- **Azure PowerShell**: Dies ist die Sammlung von PowerShell-Modulen, mit denen Azure-Dienste verwaltet werden.
- **Azure PowerShell**: Dies ist die Sammlung von PowerShell-Modulen, mit denen die Hybrid Cloud-Lösung von Microsoft verwaltet wird.

## <a name="markdown-specifics"></a>Besonderheiten von Markdown

Das Microsoft Open Publishing System (OPS), mit dem unsere Dokumentation erstellt wird, verwendet [markdig][], um die Markdown-Dokumente zu verarbeiten. Markdig analysiert die Dokumente auf der Grundlage der Regeln der aktuellen [CommonMark][]-Spezifikation.

Die neue CommonMark-Spezifikation ist weitaus strenger im Hinblick auf den Aufbau einiger Markdown-Elemente. Beachten Sie die Detailinformationen in diesem Dokument genau.

### <a name="blank-lines-spaces-and-tabs"></a>Leerzeilen, Leerzeichen und Tabstoppzeichen

Leerzeilen signalisieren darüber hinaus in Markdown das Ende eines Blocks. Zwischen Markdown-Blöcken unterschiedlicher Typen (z. B. zwischen einem Absatz und einer Liste oder einem Header) sollte eine einzelne Leerzeile stehen.

Mehrere aufeinander folgende leere Zeilen werden als einzelne leere Zeile in HTML dargestellt. Sie dienen keinem Zweck.
In einem Codeblock brechen aufeinander folgende leere Zeilen den Codeblock aus.

Entfernen Sie zusätzliche Leerzeichen am Zeilenende.

> [!NOTE]
> Abstände sind in Markdown wichtig. Verwenden Sie immer Leerzeichen anstelle harter Tabstoppzeichen. Nachgestellte Leerzeichen können sich auf das Rendern von Markdown auswirken.

### <a name="titles-and-headings"></a>Titel und Überschriften

Verwenden Sie nur [ATX-Überschriften][atx] (#-Formatvorlage, im Gegensatz zu Überschriften der `=`- oder `-`-Formatvorlagen).

- Verwenden Sie normale Groß-/Kleinschreibung – nur Eigennamen und der erste Buchstabe eines Titels oder einer Überschrift sollten groß geschrieben werden
- Zwischen dem `#` und dem ersten Buchstaben des Titels muss ein einfaches Leerzeichen stehen
- Überschriften sollten von einer einzelnen Leerzeile umgeben sein
- Nur eine Überschrift der Ebene H1 pro Dokument
- Überschriftebenen sollten um 1 erhöht werden. Ebenen nicht überspringen
- Verwenden Sie kein Fett oder anderes Markup in Headern.

### <a name="limit-line-length-to-100-characters"></a>Begrenzen Sie die Zeilenlänge auf 100 Zeichen

Dies gilt für konzeptionelle Artikel und die Cmdlet-Referenz. Das Beschränken der Zeilenlänge verbessert die Lesbarkeit von git-Diffs und git-Verlauf. Es erleichtert außerdem anderen Autoren das Einbringen ihres Beitrags.

Verwenden Sie die Erweiterung [Reflow Markdown][reflow] in Visual Studio Code, um Absätze komfortabel umzubrechen, sodass sie in die erforderliche Zeilenlänge passen.

Klassische Hilfethemen (About_topics) sind auf 80 Zeichen beschränkt. Genauere Informationen finden Sie unter [Formatieren von About_ Dateien](#formatting-about_-files).

### <a name="lists"></a>Listen

Wenn die Liste mehrere Sätze oder Absätze enthält, sollten Sie eine untergeordnete Kopfzeile anstelle einer Liste verwenden.

Eine Liste sollte von einer einzelnen Leerzeile umgeben sein.

#### <a name="unordered-lists"></a>Unsortierte Listen

Beenden Sie Listenelemente nicht mit einem Zeitraum, es sei denn, Sie enthalten mehrere Sätze. Verwenden Sie das Bindestrich Zeichen (`-`) für Listenelement Aufzählungen. Dadurch wird die Verwechselung mit fettem oder kursivem Markup vermieden, für das das Sternchen [`*`] verwendet wird. Um einen Absatz oder andere Elemente unter einem Aufzählungselement einzuschließen, fügen Sie einen Zeilenumbruch ein, und richten Sie den Einzug am ersten Zeichen nach dem Aufzählungszeichen aus.

Beispiel:

```markdown
This is a list that contain child elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Child bullet item

    Sentence explaining the child bullet.

- Second bullet item
- Third bullet item
```

Dies ist eine Liste, die untergeordnete Elemente unter einem Aufzählungs Element enthält.

- Erstes Aufzählungselement

  Satz zur Erläuterung des ersten Aufzählungszeichens.

  - Aufzählungs Element

    Satz, der die untergeordnete Aufzählung erläutert.

- Zweites Aufzählungszeichen
- Drittes Aufzählungszeichen

#### <a name="ordered-lists"></a>Sortierte Listen

Um einen Absatz oder andere Elemente unter einer Aufzählung einzuschließen, richten Sie den Einzug am ersten Zeichen nach der Elementnummer aus. Alle Elemente in einer Liste sollten die Nummer `1.` verwenden, statt jedes einzelne Element zu erhöhen. Beim Rendering erhöht Markdown den Wert automatisch. Dadurch wird die Neuanordnung von Elementen vereinfacht und der Einzug von untergeordnetem Inhalt standardisiert.

Beispiel:

```markdown
1. For the first element, insert a single space after the 1. Long sentences should be
   wrapped to the next line and must line up with the first character after the numbered
   list marker.

   To include a second element (like this one), insert a line break after the first
   and align indentations. The indentation of the second element must line up with
   the first character after the numbered list marker. For single digit items, like
   this one, you indent to column 4. For double digits items, for example item number
   10, you indent to column 5.

1. The next numbered item starts here.
```

Der resultierende Markdown wird wie folgt gerendert:

1. Fügen Sie für das erste Element ein einzelnes Leerzeichen nach der 1 ein. Lange Sätze sollten in die nächste Zeile umbrochen werden und müssen am ersten Zeichen hinter dem nummerierten Listenmarker ausgerichtet werden.

   Um ein zweites Element (wie dieses hier) aufzuführen, fügen Sie nach dem ersten Element einen Zeilenumbruch ein, und richten Sie die Einzüge aus. Der Einzug des zweiten Elements muss am ersten Zeichen hinter dem nummerierten Listenmarker ausgerichtet werden. Für einstellige Elemente wie dieses ziehen Sie in Spalte 4 ein. Für zweistellige Elemente, beispielsweise die Elementnummer 10, ziehen Sie in Spalte 5 ein.

1. Das nächste nummerierte Element beginnt hier.

### <a name="images"></a>Bilder

Die Syntax zum Einschließen eines Bilds lautet wie folgt:

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

Dabei stellt `alt text` eine kurze Beschreibung des Bilds und `<folder path>` einen relativen Pfad zum Bild dar. Alternativtext ist für Bildschirmsprachausgaben für Personen mit eingeschränktem Sehvermögen erforderlich.

Bilder sollten in einem `media/<article-name>` Ordner innerhalb des Ordners gespeichert werden, der den Artikel enthält.
Geben Sie Bilder nicht zwischen Artikeln frei. Erstellen Sie einen Ordner, der mit dem Dateinamen Ihres Artikels im `media`-Ordner übereinstimmt. Kopieren Sie die Bilder für diesen Artikel in diesen neuen Ordner. Wenn ein Bild in mehreren Artikeln verwendet wird, muss jeder Bildordner eine Kopie dieser Bilddatei enthalten. Durch diese Vorgehensweise wird verhindert, dass eine Änderung an einem Bild in einem Artikel sich auf einen anderen Artikel auswirkt.

Die folgenden Bild Dateitypen werden unterstützt: `*.png` , `*.gif` , `*.jpeg` , `*.jpg` , `*.svg`

### <a name="markdown-extensions-supported-by-open-publishing"></a>Von Open Publishing unterstützte Markdownerweiterungen

Das [Microsoft-Dokumentation Authoring Pack](/contribute/how-to-write-docs-auth-pack) enthält Tools, die Features unterstützen, die für unser Veröffentlichungs System eindeutig sind. Warnungen sind eine markdown-Erweiterung zum Erstellen von blockanführungs Zeichen, die auf docs.Microsoft.com mit Farben und Symbolen gerengt werden, die die Bedeutung der Inhalte hervorheben. Die folgenden Warnungstypen werden unterstützt:

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

Diese Warnungen sehen auf docs.microsoft.com folgendermaßen aus:

Notizblock

> [!NOTE]
> Information the user should notice even if skimming.

Tip-Block

> [!TIP]
> Optional information to help a user be more successful.

Wichtiger Block

> [!IMPORTANT]
> Essential information required for user success.

Warn Block

> [!CAUTION]
> Negative potential consequences of an action.

Warnungs Block

> [!WARNING]
> Gefährliche Folgen einer Aktion.

### <a name="hyperlinks"></a>Links

- Hyperlinks müssen die markdown-Syntax verwenden `[friendlyname](url-or-path)` . [Link Verweise][linkref] werden unterstützt.
- Das Veröffentlichungs System unterstützt drei Arten von Verknüpfungen:
  - URL-Links
  - Datei Verknüpfungen
  - Querverweis Verknüpfungen
- Links zu anderen Artikeln auf docs.Microsoft.com müssen Site relative Pfade sein.
- Alle URLs für externe Websites sollten HTTPS verwenden, es sei denn, der Ziel Standort ist ungültig.
- Links müssen einen anzeigen Amen haben, in der Regel den Titel des verknüpften Artikels.
- Alle Elemente im Abschnitt _verknüpfte Verknüpfungen_ im unteren Bereich sollten hyperverknüpft werden.
- Verwenden Sie keine Backticks, Fett oder andere Markup innerhalb der Klammern eines Links.
- Bare-URLs können verwendet werden, wenn Sie einen bestimmten URI dokumentieren. Der URI muss in Backticks eingeschlossen werden. Beispiel:

  ```markdown
  By default, if you don't specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content-on-docsmicrosoftcom"></a>Verknüpfen mit anderem Inhalt auf docs.Microsoft.com

- **URL-Links** zu anderen Artikeln auf docs.Microsoft.com müssen Site relative Pfade sein. Die einfachste Möglichkeit, eine relative Verknüpfung zu erstellen, besteht darin, die URL aus dem Browser zu kopieren und dann aus dem Wert zu entfernen, den `https://docs.microsoft.com/en-us` Sie in markdown eingefügt haben. Gebiets Schemas nicht in URLs in Microsoft-Eigenschaften einschließen (Remove `/en-us` from URL). Entfernen Sie alle unnötigen Abfrage Parameter aus der URL. Zu entfernende Beispiele:

  - `?view=powershell-5.1` : wird zum Verknüpfen mit einer bestimmten Version von PowerShell verwendet.
  - `?redirectedfrom=MSDN` -wird der URL hinzugefügt, wenn Sie von einem alten Artikel an den neuen Speicherort umgeleitet werden

  Wenn Sie eine Verknüpfung mit einer bestimmten Version eines Dokuments herstellen müssen, müssen Sie den `&preserve_view=true` Parameter der Abfrage Zeichenfolge hinzufügen. Beispiel: `?view=powershell-5.1&preserve_view=true`

- Ein **Dateilink** wird verwendet, um eine Verknüpfung zwischen Verweis Artikeln oder einem konzeptionellen Artikel zu einem anderen zu erhalten. Wenn Sie eine Verknüpfung mit einem Referenz Artikel für eine bestimmte Version von PowerShell herstellen müssen, müssen Sie einen URL-Link verwenden.

  - Datei Verknüpfungen enthalten einen relativen Dateipfad (Beispiel: `../folder/file.md` ).
  - Alle Dateipfade verwenden Schrägstriche ( `/` ).

- **Querverweis Verknüpfungen** sind eine spezielle Funktion, die vom Veröffentlichungs System unterstützt wird. Sie können Verweis übergreifende Links in konzeptionellen Artikeln verwenden, um eine Verknüpfung mit der .NET-API oder der Cmdlet-Referenz zu erhalten.

  Links zur .NET-API-Referenz finden Sie unter [Verwenden von Links in der Dokumentation](/contribute/how-to-write-links#xref-cross-reference-links) im Leitfaden "zentrale Mitwirkende".

  Links zur Cmdlet-Referenz haben das folgende Format: `xref:<module-name>.<cmdlet-name>` . Beispielsweise, um eine Verknüpfung mit dem- `Get-Content` Cmdlet im **Microsoft. PowerShell. Management** -Modul zu erhalten.

  `[Get-Content](xref:Microsoft.PowerShell.Management.Get-Content)`

Deep Linking ist sowohl für URL-als auch für Datei Verknüpfungen zulässig. Fügen Sie den Anker am Ende des Zielpfads hinzu.
Beispiel:

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

Weitere Informationen finden Sie unter [Verwenden von Links in der Dokumentation](/contribute/how-to-write-links).

## <a name="formatting-command-syntax-elements"></a>Formatieren von Befehlssyntaxelementen

- Verwenden Sie immer den vollständigen Namen für Cmdlets und Parameter. Vermeiden Sie die Verwendung von Aliasen, es sei denn, Sie demonstrieren den Alias.

- Eigenschaft, Parameter, Objekt, Typnamen, Klassennamen und Klassen Methoden sollten **Fett** formatiert sein.
  - Eigenschafts-und Parameterwerte sollten in Graviszeichen ( `` ` `` ) verpackt werden.
  - Verwenden Sie Backticks, wenn Sie auf Typen verweisen, die in Klammern stehen. Beispiel: `[System.Io.FileInfo]`

- Sprach Schlüsselwörter, Namen von Cmdlets, Funktionen, Variablen, systemeigene EXE-Dateien, Dateipfade und Inline Syntax Beispiele sollten in Graviszeichen ()-Zeichen umschließt werden `` ` `` .

  Beispiel:

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - Wenn Sie einen Parameter bei Namen nennen, sollte der Name **fett** geschrieben werden. Wenn Sie die Verwendung eines Parameters mithilfe eines Bindestrichs als Präfix darstellen, sollte der Parameter von Backticks umschlossen werden. Beispiel:

    ```markdown
    The parameter's name is **Name**, but it's typed as `-Name` when used on the command
    line as a parameter.
    ```

  - Wenn Sie die Verwendung eines externen Befehls veranschaulichen, sollte das Beispiel von Backticks umschlossen werden.
    Fügen Sie die Dateierweiterung immer in den nativen Befehl ein. Beispiel:

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    Durch einschließen der Dateierweiterung wird sichergestellt, dass der richtige Befehl entsprechend der Befehls Rangfolge von PowerShell ausgeführt wird.

- Wenn Sie einen Konzeptartikel schreiben (im Gegensatz zu Referenzinhalten), sollte das erste Vorkommnis eines Cmdlet-Namens ein Link zur Dokumentation des Cmdlets sein. Verwenden Sie keine Backticks, Fett oder andere Markup innerhalb der Klammern eines Links.

  Beispiel:

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  Weitere Informationen finden Sie in diesem Artikel im Abschnitt [Hyperlinks](#hyperlinks) .

## <a name="markdown-for-code-samples"></a>Markdown für Codebeispiele

Markdown unterstützt zwei verschiedene Codestile:

- **Code spannen (Inline)** : gekennzeichnet durch ein einzelnes Graviszeichen ( `` ` `` ). Wird in einem Absatz anstelle als eigenständiger Block verwendet.
- **Code Blöcke** : ein mehrzeiligen Block, der von Triple-Backtick ()-Zeichen folgen umgeben ist `` ``` `` . Code Blöcke können auch über eine sprach Bezeichnung verfügen, die den Backticks folgt. Die sprach Bezeichnung ermöglicht die Syntax Hervorhebung für den Inhalt des Code Blocks.

Alle Codeblöcke sollten in einem Codefence enthalten sein. Verwenden Sie niemals den Einzug für Code Blöcke. Markdown lässt dieses Muster zu, kann jedoch problematisch sein und sollte vermieden werden.

Ein Codeblock ist eine oder mehrere Codezeilen, die von einem Code-Fence mit dreifacher Backtick () umgeben sind `` ``` `` .
Die Codefencemarker müssen vor und nach dem Codebeispiel in einer eigenen Zeile stehen. Der Marker am Anfang des Codeblocks kann eine optionale Sprachbezeichnung aufweisen. Das Open Publishing System (OPS) von Microsoft verwendet die Sprachbezeichnung, um die Funktion der Syntaxhervorhebung zu unterstützen.

Eine vollständige Liste der unterstützten Sprachen [Tags finden Sie im Leitfaden zu den](/contribute/code-in-docs#fenced-code-blocks) zentralisierten Mitwirkenden.

OPS fügt auch eine **Kopieren**-Schaltfläche hinzu, mit der der Inhalt des Codeblocks in die Zwischenablage kopiert wird. Dies ermöglicht es Ihnen, den Code schnell in ein Skript einzufügen, um das Codebeispiel zu testen. Allerdings sind nicht alle Beispiele in unserer Dokumentation unverändert auszuführen. Einige Code Blöcke sind einfache Abbildungen eines PowerShell-Konzepts.

Es gibt drei Typen von Code Blöcken, die in unserer Dokumentation verwendet werden:

1. Syntax Blöcke
1. Anschauliche Beispiele
1. Ausführbare Beispiele

### <a name="syntax-code-blocks"></a>Syntax Code Blöcke

Syntax Code Blöcke werden verwendet, um die syntaktische Struktur eines Befehls zu beschreiben. Verwenden Sie für den codefence kein Sprachtag. In diesem Beispiel werden alle möglichen Parameter des `Get-Command`-Cmdlets veranschaulicht.

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

In diesem Beispiel wird die `for`-Anweisung in allgemeinen Begriffen beschrieben:

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a>Anschauliche Beispiele

Anschauliche Beispiele werden zur Erklärung eines PowerShell-Konzepts verwendet. Sie sollen nicht zur Ausführung in die Zwischenablage kopiert werden. Diese werden am häufigsten für einfache Beispiele verwendet, die einfach zu finden und leicht verständlich sind. Der Codeblock kann die PowerShell-Eingabeaufforderung und Beispielausgabe enthalten.

Im folgenden finden Sie ein einfaches Beispiel zur Veranschaulichung der PowerShell-Vergleichs Operatoren. In diesem Fall ist es nicht beabsichtigt, dieses Beispiel zu kopieren und auszuführen.

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

### <a name="executable-examples"></a>Ausführbare Beispiele

Komplexe Beispiele oder Beispiele, die kopiert und ausgeführt werden sollen, sollten das folgende Markup im Block Format verwenden:

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

Die von PowerShell-Befehlen angezeigte Ausgabe sollte in einen **Ausgabe**-Codeblock eingeschlossen werden, um die Syntaxhervorhebung zu verhindern. Beispiel:

~~~markdown
```powershell
Get-Command -Module Microsoft.PowerShell.Security
```

```Output
CommandType  Name                        Version    Source
-----------  ----                        -------    ------
Cmdlet       ConvertFrom-SecureString    3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       ConvertTo-SecureString      3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-CmsMessage              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Credential              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-PfxCertificate          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       New-FileCatalog             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Protect-CmsMessage          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Test-FileCatalog            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Unprotect-CmsMessage        3.0.0.0    Microsoft.PowerShell.Security
```
~~~

Die **Ausgabe** Code Bezeichnung ist keine offizielle "Sprache", die vom System für die Syntax Hervorhebung unterstützt wird.
Diese Bezeichnung ist jedoch nützlich, da OPS dem Code Feld Rahmen auf der Webseite die Bezeichnung "Output" hinzufügt. Das Codefeld "Output" hat keine Syntax Hervorhebung.

## <a name="coding-style-rules"></a>Codierungsstilregeln

### <a name="avoid-line-continuation-in-code-samples"></a>Vermeiden von Zeilenfortsetzungen in Codebeispielen

Vermeiden Sie Zeilenfortsetzungszeichen (`` ` ``) in PowerShell-Codebeispielen. Diese sind schwer zu erkennen und können Probleme verursachen, wenn am Ende der Zeile zusätzliche Leerzeichen vorhanden sind.

- Verwenden Sie PowerShell-Verteilung, um die Zeilenlänge für Cmdlets mit mehreren Parametern zu verringern.
- Profitieren Sie von den Vorteilen der natürlichen Zeilen Umbruchs von PowerShell, wie z. b. nach senkrechter Zeichen (), `|` öffnenden geschweiften Klammern ( `{` ), Klammern ( `(` ) und eckigen Klammern ( `[` ).

### <a name="avoid-using-powershell-prompts-in-examples"></a>Vermeiden Sie die Verwendung von PowerShell-Eingabeaufforderungen in Beispielen

Die Verwendung der Eingabe Aufforderungs Zeichenfolge wird davon abgeraten und sollte auf Szenarien beschränkt sein, die zur Veranschaulichung der Befehlszeilen Verwendung dienen. Für die meisten dieser Beispiele sollte die Eingabe Aufforderungs Zeichenfolge lauten `PS>` . Diese Eingabeaufforderung ist unabhängig von betriebssystemspezifischen Indikatoren.

In Beispielen sind Aufforderungen erforderlich, um Befehle zu veranschaulichen, mit denen die Eingabeaufforderung geändert wird, oder wenn der angezeigte Pfad für das Szenario wichtig ist. Im folgenden Beispiel wird veranschaulicht, wie die Eingabeaufforderung geändert wird, wenn der Registrierungsanbieter verwendet wird.

```powershell
PS C:\> cd HKCU:\System\
PS HKCU:\System\> dir

    Hive: HKEY_CURRENT_USER\System

Name                   Property
----                   --------
CurrentControlSet
GameConfigStore        GameDVR_Enabled                       : 1
                       GameDVR_FSEBehaviorMode               : 2
                       Win32_AutoGameModeDefaultProfile      : {2, 0, 1, 0...}
                       Win32_GameModeRelatedProcesses        : {1, 0, 1, 0...}
                       GameDVR_HonorUserFSEBehaviorMode      : 0
                       GameDVR_DXGIHonorFSEWindowsCompatible : 0
```

### <a name="dont-use-aliases-in-examples"></a>Verwenden Sie in Beispielen keine Aliase.

Verwenden Sie den vollständigen Namen aller Cmdlets und Parameter, es sei denn, Sie dokumentieren den Alias.
Cmdlet-und Parameternamen müssen die richtigen [Pascal-][] Schreib Namen verwenden.

### <a name="using-parameters-in-examples"></a>Verwenden der Parameter in Beispielen

Vermeiden Sie Positionsparameter. Im Allgemeinen sollten Sie immer den Parameternamen in ein Beispiel einschließen, auch wenn der Parameter eine positionelle ist. Dadurch kommt es zu weniger Verwirrung in Ihren Beispielen.

## <a name="formatting-cmdlet-reference-articles"></a>Cmdlet-Referenz Artikel zum Formatieren

Cmdlet-Referenzartikel weisen eine bestimmte Struktur auf. Diese Struktur wird von [PlatyPS][] definiert.
Platyps generiert die Cmdlet-Hilfe für PowerShell-Module in markdown. Nachdem die Markdowndateien bearbeitet wurden, wird PlatyPS zum Erstellen der MAML-Hilfsdateien für das Cmdlet `Get-Help` verwendet.

PlatyPS verfügt über ein hartcodiertes Schema für Cmdlet-Referenzen, das im Code enthalten ist. Im Dokument [platyPS.schema.md][] wird diese Struktur beschrieben. Verstöße gegen das Schema führen zu Buildfehlern, die behoben werden müssen, bevor Ihr Beitrag akzeptiert werden kann.

- Entfernen Sie keine der ATX-Header Strukturen. PlatyPS erwartet spezifische Überschriften.
- Die Header **Input type** (Eingabetyp) und **Output type** (Ausgabetyp) müssen einen Typ aufweisen. Wenn das Cmdlet keine Eingaben annimmt oder einen Wert zurückgibt, verwenden Sie den Wert `None` .
- Inlinecodespannen können in allen Absätzen verwendet werden.
- Umgrenzte Code Blöcke sind nur im Abschnitt " **Beispiele** " zulässig.

Im platyps-Schema handelt es sich bei **Beispielen** um einen H2-Header. Jedes Beispiel ist ein H3-Header. In einem Beispiel lässt das Schema nicht zu, dass Code Blöcke durch Absätze getrennt werden. Das Schema ermöglicht die folgende Struktur:

```
### Example X - Title sentence

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

Geben Sie für alle Beispiele eine Zahl und einen kurzen Titel an.

Beispiel:

~~~markdown
### Example 1: Get cmdlets, functions, and aliases

This command gets the PowerShell cmdlets, functions, and aliases that are installed on the
computer.

```powershell
Get-Command
```

### Example 2: Get commands in the current session

```powershell
Get-Command -ListImported
```
~~~

## <a name="formatting-about_-files"></a>Formatieren von „About_“-Dateien

`About_*` Dateien werden in markdown geschrieben, aber als nur-Text-Dateien ausgeliefert. Sie verwenden [pandoc][] , um markdown in nur-Text zu konvertieren. `About_*` Dateien werden für die beste Kompatibilität in allen Versionen von PowerShell und mit den Veröffentlichungs Tools formatiert.

Grundlegende Formatierungsrichtlinien:

- Normale Zeilen auf 80 Zeichen begrenzen
- Code Blöcke sind auf 76 Zeichen beschränkt.
- Bei blockanführungs Zeichen (und Warnungen) handelt es sich um 78 Zeichen.
- Bei Verwendung dieser speziellen Meta-Zeichen `\` , `$` und `<` :
  - Innerhalb eines Headers müssen diese Zeichen mit Escapezeichen versehen werden, indem ein führendes `\` Zeichen verwendet oder in Code spannen mithilfe von Graviszeichen () eingeschlossen wird. `` ` ``
  - Innerhalb eines Absatzes sollten diese Zeichen in Code spannen eingefügt werden. Beispiel:

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- Tabellen müssen in 76 Zeichen passen
  - Umschließen Sie Inhalte von Zellen in mehreren Zeilen manuell.
  - Verwenden Sie öffnende und schließende `|`-Zeichen in jeder Zeile.
  - Im folgenden Beispiel wird veranschaulicht, wie eine Tabelle, die Informationen enthält, die in mehreren Zeilen innerhalb einer Zelle umschlossen werden, ordnungsgemäß erstellt wird.

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > Die Einschränkung der 76-Spalte gilt nur für `About_*` Themen. Sie können Breite Spalten in konzeptionellen oder Cmdlet-referenzartikeln verwenden.

## <a name="next-steps"></a>Nächste Schritte

[Checkliste für Redakteure](editorial-checklist.md)

<!-- link references -->
[atx]: https://github.github.com/gfm/#atx-headings
[CommonMark]: https://spec.commonmark.org/
[markdig]: https://github.com/lunet-io/markdig
[Pandoc]: https://pandoc.org
[Pascal-schreibgeschützte]: https://en.wikipedia.org/wiki/PascalCase
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[PlatyPS]: https://github.com/powershell/platyps
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
[linkref]: https://spec.commonmark.org/0.29/#link-reference-definitions
