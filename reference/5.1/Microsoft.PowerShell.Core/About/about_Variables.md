---
description: Beschreibt, wie Variablen Werte speichern, die in PowerShell verwendet werden können.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Variables
ms.openlocfilehash: 59a611cf49635f0391d3f3cc18bcf6d06a688638
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223215"
---
# <a name="about-variables"></a>Informationen zu Variablen

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt, wie Variablen Werte speichern, die in PowerShell verwendet werden können.

## <a name="long-description"></a>Lange Beschreibung

Sie können alle Typen von Werten in PowerShell-Variablen speichern. Speichern Sie z. b. die Ergebnisse von Befehlen, und speichern Sie Elemente, die in Befehlen und Ausdrücken verwendet werden, wie z. b. Namen, Pfade, Einstellungen und Werte.

Eine Variable ist eine Speichereinheit, in der Werte gespeichert werden. In PowerShell werden Variablen durch Text Zeichenfolgen dargestellt, die mit einem Dollarzeichen ( `$` ) beginnen, z `$a` . b., `$process` oder `$my_var` .

Bei Variablennamen wird die Groß-/Kleinschreibung nicht beachtet, und Sie können Leerzeichen und Sonderzeichen enthalten Variablennamen, die Sonderzeichen und Leerzeichen enthalten, sind jedoch schwer zu verwenden und sollten vermieden werden. Weitere Informationen finden Sie unter [Variablennamen, die Sonderzeichen enthalten](#variable-names-that-include-special-characters).

Es gibt mehrere verschiedene Arten von Variablen in PowerShell.

- Vom Benutzer erstellte Variablen: vom Benutzer erstellte Variablen werden erstellt und verwaltet. Standardmäßig existieren die Variablen, die Sie in der PowerShell-Befehlszeile erstellen, nur, während das PowerShell-Fenster geöffnet ist. Wenn das PowerShell-Fenster geschlossen wird, werden die Variablen gelöscht. Um eine Variable zu speichern, fügen Sie Sie Ihrem PowerShell-Profil hinzu. Sie können auch Variablen in Skripts mit dem globalen, Skript-oder lokalen Gültigkeitsbereich erstellen.

- Automatische Variablen: automatische Variablen speichern den Status von PowerShell. Diese Variablen werden von PowerShell erstellt, und PowerShell ändert ihre Werte nach Bedarf, um Ihre Genauigkeit beizubehalten. Benutzer können den Wert dieser Variablen nicht ändern. Die `$PSHOME` Variable speichert beispielsweise den Pfad zum PowerShell-Installationsverzeichnis.

  Weitere Informationen, eine Liste und eine Beschreibung der automatischen Variablen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).

- Einstellungs Variablen: Einstellungs Variablen speichern Benutzereinstellungen für PowerShell. Diese Variablen werden von PowerShell erstellt und mit Standardwerten aufgefüllt. Benutzer können die Werte dieser Variablen ändern. Beispielsweise legt die- `$MaximumHistoryCount` Variable die maximale Anzahl von Einträgen im Sitzungsverlauf fest.

  Weitere Informationen, eine Liste und eine Beschreibung der Einstellungs Variablen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).

## <a name="working-with-variables"></a>Arbeiten mit Variablen

Um eine neue Variable zu erstellen, verwenden Sie eine Zuweisungsanweisung, um der Variablen einen Wert zuzuweisen. Sie müssen die Variable nicht deklarieren, bevor Sie Sie verwenden. Der Standardwert aller Variablen ist `$null` .

Geben Sie ein, um eine Liste aller Variablen in der PowerShell-Sitzung zu erhalten `Get-Variable` . Die Variablennamen werden ohne das vorangehende Dollar `$` Zeichen () angezeigt, das für den Verweis auf Variablen verwendet wird.

Beispiel:

```powershell
$MyVariable = 1, 2, 3

$Path = "C:\Windows\System32"
```

Variablen sind nützlich, um die Ergebnisse von Befehlen zu speichern.

Beispiel:

```powershell
$Processes = Get-Process

$Today = (Get-Date).DateTime
```

Wenn Sie den Wert einer Variablen anzeigen möchten, geben Sie den Variablennamen ein, dem ein Dollarzeichen () vorangestellt ist `$` .

Beispiel:

```powershell
$MyVariable
```

```Output
1
2
3
```

```powershell
$Today
```

```Output
Tuesday, September 3, 2019 09:46:46
```

Um den Wert einer Variablen zu ändern, weisen Sie der Variablen einen neuen Wert zu.

In den folgenden Beispielen wird der Wert der- `$MyVariable` Variablen angezeigt, der Wert der-Variablen geändert und dann der neue Wert angezeigt.

```powershell
$MyVariable = 1, 2, 3
$MyVariable
```

```Output
1
2
3
```

```powershell
$MyVariable = "The green cat."
$MyVariable
```

```Output
The green cat.
```

Um den Wert einer Variablen zu löschen, verwenden Sie das- `Clear-Variable` Cmdlet, oder ändern Sie den Wert in `$null` .

```powershell
Clear-Variable -Name MyVariable
```

```powershell
$MyVariable = $null
```

Um die Variable zu löschen, verwenden Sie [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) oder [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).

```powershell
Remove-Variable -Name MyVariable
```

```powershell
Remove-Item -Path Variable:\MyVariable
```

## <a name="types-of-variables"></a>Typen von Variablen

Sie können beliebige Objekttypen in einer Variablen speichern, einschließlich Ganzzahlen, Zeichen folgen, Arrays und Hash Tabellen. Und,-Objekte, die Prozesse, Dienste, Ereignisprotokolle und Computer darstellen.

PowerShell-Variablen sind lose typisiert, was bedeutet, dass Sie nicht auf einen bestimmten Objekttyp beschränkt sind. Eine einzelne Variable kann sogar eine Auflistung oder ein Array von unterschiedlichen Objekttypen gleichzeitig enthalten.

Der Datentyp einer Variablen wird durch die .NET-Typen der Werte der Variablen bestimmt. Verwenden [Sie Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member), um den Objekttyp einer Variablen anzuzeigen.

Beispiel:

```powershell
$a = 12                         # System.Int32
$a = "Word"                     # System.String
$a = 12, "Word"                 # array of System.Int32, System.String
$a = Get-ChildItem C:\Windows   # FileInfo and DirectoryInfo types
```

Sie können ein Type-Attribut und eine Cast Notation verwenden, um sicherzustellen, dass eine Variable nur bestimmte Objekttypen oder Objekte enthalten kann, die in diesen Typ konvertiert werden können. Wenn Sie versuchen, einen Wert eines anderen Typs zuzuweisen, versucht PowerShell, den Wert in seinen Typ zu konvertieren. Wenn der Typ nicht konvertiert werden kann, schlägt die Zuweisungsanweisung fehl.

Um Cast Notation zu verwenden, geben Sie vor dem Variablennamen (auf der linken Seite der Zuweisungsanweisung) einen Typnamen ein, der in Klammern eingeschlossen ist. Im folgenden Beispiel wird eine `$number` Variable erstellt, die nur ganze Zahlen enthalten kann, eine `$words` Variable, die nur Zeichen folgen enthalten kann, und eine `$dates` Variable, die nur **DateTime** -Objekte enthalten kann.

```powershell
[int]$number = 8
$number = "12345"  # The string is converted to an integer.
$number = "Hello"
```

```Output
Cannot convert value "Hello" to type "System.Int32". Error: "Input string was
 not in a correct format."
At line:1 char:1
+ $number = "Hello"
+ ~~~~~~~~~~~~~~~~~
+ CategoryInfo          : MetadataError: (:) [],
    ArgumentTransformationMetadataException
+ FullyQualifiedErrorId : RuntimeException
```

```powershell
[string]$words = "Hello"
$words = 2       # The integer is converted to a string.
$words += 10     # The plus (+) sign concatenates the strings.
$words
```

```Output
210
```

```powershell
[datetime] $dates = "09/12/91"  # The string is converted to a DateTime object.
$dates
```

```Output
Thursday, September 12, 1991 00:00:00
```

```powershell
$dates = 10    # The integer is converted to a DateTime object.
$dates
```

```Output
Monday, January 1, 0001 00:00:00
```

## <a name="using-variables-in-commands-and-expressions"></a>Verwenden von Variablen in Befehlen und Ausdrücken

Wenn Sie eine Variable in einem Befehl oder Ausdruck verwenden möchten, geben Sie den Variablennamen ein, dem das Dollarzeichen () vorangestellt ist `$` .

Wenn der Variablenname und das Dollarzeichen nicht in Anführungszeichen eingeschlossen sind oder wenn Sie in doppelte Anführungszeichen ( `"` ) eingeschlossen sind, wird der Wert der Variablen im Befehl oder Ausdruck verwendet.

Wenn der Variablenname und das Dollarzeichen in einfache Anführungszeichen ( `'` ) eingeschlossen sind, wird der Variablenname im Ausdruck verwendet.

Weitere Informationen zum Verwenden von Anführungszeichen in PowerShell finden Sie unter [about_Quoting_Rules](about_Quoting_Rules.md).

In diesem Beispiel wird der Wert der- `$PROFILE` Variablen abgerufen, d. h. der Pfad zur PowerShell-Benutzerprofil Datei in der PowerShell-Konsole.

```powershell
$PROFILE
```

```Output
C:\Users\User01\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```

In diesem Beispiel werden zwei Befehle angezeigt, die das PowerShell-Profil in **notepad.exe** öffnen können. Im Beispiel mit doppelten Anführungszeichen ( `"` ) wird der Wert der Variablen verwendet.

```powershell
notepad $PROFILE

notepad "$PROFILE"
```

In den folgenden Beispielen werden einfache Anführungs `'` Zeichen () verwendet, mit denen die Variable als Literaltext behandelt wird.

```powershell
'$PROFILE'
```

```Output
$PROFILE
```

```powershell
'Use the $PROFILE variable.'
```

```Output
Use the $PROFILE variable.
```

## <a name="variable-names-that-include-special-characters"></a>Variablennamen, die Sonderzeichen enthalten

Variablennamen beginnen mit einem Dollar `$` Zeichen () und können alphanumerische Zeichen und Sonderzeichen enthalten. Die Länge des Variablen namens ist nur durch den verfügbaren Arbeitsspeicher beschränkt.

Die bewährte Vorgehensweise besteht darin, dass Variablennamen nur alphanumerische Zeichen und den Unterstrich ( `_` ) enthalten. Variablennamen, die Leerzeichen und andere Sonderzeichen enthalten, sind schwer zu verwenden und sollten vermieden werden.

Alphanumerische Variablennamen können folgende Zeichen enthalten:

- Unicode-Zeichen aus diesen Kategorien: **lu** , **ll** , **lt** , **LM** , **Lo** oder **ND**.
- Unterstrich ( `_` ).
- Fragezeichen ( `?` ).

Die folgende Liste enthält die Beschreibungen der Unicode-Kategorie. Weitere Informationen finden Sie unter [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).

- **Lu** -UppercaseLetter
- **Ll** -LowercaseLetter
- **Lt** -TitlecaseLetter
- **LM** -ModifierLetter
- **Lo** -OtherLetter
- **ND** -DecimalDigitNumber

Um einen Variablennamen zu erstellen oder anzuzeigen, der Leerzeichen oder Sonderzeichen enthält, schließen Sie den Variablennamen in die geschweiften Klammern ( `{}` ) ein.
Die geschweiften Klammern leiten PowerShell ein, um die Zeichen des Variablen namens als Literale zu interpretieren.

Variablennamen mit Sonderzeichen können folgende Zeichen enthalten:

- Ein beliebiges Unicode-Zeichen mit den folgenden Ausnahmen:
  - Das schließende geschweifte Klammer `}` Zeichen () (U + 007d).
  - Das Graviszeichen ( `` ` `` )-Zeichen (U + 0060). Mit dem Graviszeichen werden Unicode-Zeichen mit Escapezeichen versehen, sodass Sie als Literale behandelt werden.

PowerShell verfügt über reservierte Variablen `$$` , wie z `$?` . b.,, und, `$^` `$_` die alphanumerische Zeichen und Sonderzeichen enthalten. Weitere Informationen finden Sie unter [about_Automatic_Variables](about_automatic_variables.md).

Der folgende Befehl erstellt beispielsweise die-Variable mit dem Namen `save-items` . Die geschweiften Klammern ( `{}` ) sind erforderlich, da der Variablenname ein Bindestrich ( `-` )-Sonderzeichen enthält.

```powershell
${save-items} = "a", "b", "c"
${save-items}
```

```Output
a
b
c
```

Der folgende Befehl ruft die untergeordneten Elemente in dem Verzeichnis ab, das durch die `ProgramFiles(x86)` Umgebungsvariable dargestellt wird.

```powershell
Get-ChildItem ${env:ProgramFiles(x86)}
```

Um auf einen Variablennamen zu verweisen, der geschweifte Klammern enthält, schließen Sie den Variablennamen in geschweifte Klammern ein, und verwenden Sie das Graviszeichen-Zeichen, um die Klammern zu So erstellen Sie z. b. eine Variable namens `this{value}is` Type:

```powershell
${this`{value`}is} = "This variable name uses braces and backticks."
${this`{value`}is}
```

```Output
This variable name uses braces and backticks.
```

## <a name="variables-and-scope"></a>Variablen und Bereich

Standardmäßig sind Variablen nur in dem Bereich verfügbar, in dem Sie erstellt werden.

Beispielsweise ist eine Variable, die Sie in einer Funktion erstellen, nur innerhalb der-Funktion verfügbar. Eine Variable, die Sie in einem Skript erstellen, ist nur innerhalb des Skripts verfügbar. Wenn Sie das Skript mit einem Punkt versehen, wird die Variable dem aktuellen Gültigkeitsbereich hinzugefügt. Weitere Informationen finden Sie unter [about_Scopes](about_Scopes.md).

Sie können einen bereichsmodifizierer verwenden, um den Standardbereich der Variablen zu ändern. Der folgende Ausdruck erstellt eine Variable mit dem Namen `Computers` . Die Variable verfügt über einen globalen Gültigkeitsbereich, auch wenn Sie in einem Skript oder einer Funktion erstellt wird.

```powershell
$Global:Computers = "Server01"
```

Für Skripts oder Befehle, die außerhalb der Sitzung ausgeführt werden, müssen Sie den bereichsmodifizierer `Using` zum Einbetten von Variablen Werten aus dem aufrufenden Sitzungs Bereich benötigen, damit der Sitzungscode darauf zugreifen kann.

Weitere Informationen finden Sie unter [about_Remote_Variables](about_Remote_Variables.md).

## <a name="saving-variables"></a>Speichern von Variablen

Die von Ihnen erstellten Variablen sind nur in der Sitzung verfügbar, in der Sie Sie erstellen. Sie gehen verloren, wenn Sie die Sitzung schließen.

Um die Variable in jeder PowerShell-Sitzung zu erstellen, die Sie starten, fügen Sie die Variable Ihrem PowerShell-Profil hinzu.

Fügen Sie z. b. den folgenden Befehl in das PowerShell-Profil ein, um den Wert der `$VerbosePreference` Variablen in jeder PowerShell-Sitzung zu ändern.

```powershell
$VerbosePreference = "Continue"
```

Sie können diesen Befehl zu Ihrem PowerShell-Profil hinzufügen, indem Sie die `$PROFILE` Datei in einem Text-Editor öffnen, z. b. **notepad.exe**. Weitere Informationen zu PowerShell-Profilen finden Sie unter [about_Profiles](about_Profiles.md).

## <a name="the-variable-drive"></a>Das Variable:-Laufwerk

Der PowerShell-Variablen Anbieter erstellt ein `Variable:` Laufwerk, das wie ein Dateisystem Laufwerk aussieht und verhält, aber die Variablen in der Sitzung und deren Werte enthält.

Verwenden Sie den folgenden Befehl, um zum Laufwerk zu wechseln `Variable:` :

```powershell
Set-Location Variable:
```

Um die Elemente und Variablen im Laufwerk aufzulisten `Variable:` , verwenden Sie die `Get-Item` `Get-ChildItem` Cmdlets oder.

```powershell
Get-ChildItem Variable:
```

Um den Wert einer bestimmten Variablen zu erhalten, geben Sie mit der Dateisystem Notation den Namen des Laufwerks und den Namen der Variablen an. Um z. b. die `$PSCulture` Automatische Variable zu erhalten, verwenden Sie den folgenden Befehl.

```powershell
Get-Item Variable:\PSCulture
```

```Output
Name                           Value
----                           -----
PSCulture                      en-US
```

Geben Sie Folgendes ein, um weitere Informationen zum `Variable:` Laufwerk und zum PowerShell-Variablen Anbieter anzuzeigen:

```powershell
Get-Help Variable
```

## <a name="variable-syntax-with-provider-paths"></a>Variablen Syntax mit Anbieter Pfaden

Sie können einem Anbieter Pfad das Dollarzeichen () als Präfix voranstellen `$` und auf den Inhalt eines beliebigen Anbieters zugreifen, der die [icontentcmdletprovider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) -Schnittstelle implementiert.

Die folgenden integrierten PowerShell-Anbieter unterstützen diese Notation:

- [about_Environment_Provider](about_Environment_Provider.md)
- [about_Variable_Provider](about_Variable_Provider.md)
- [about_Function_Provider](about_Function_Provider.md)
- [about_Alias_Provider](about_Alias_Provider.md)

## <a name="the-variable-cmdlets"></a>Die Variablen-Cmdlets

PowerShell umfasst einen Satz von Cmdlets, die zum Verwalten von Variablen entwickelt wurden.

Geben Sie Folgendes ein, um die Cmdlets aufzulisten:

```powershell
Get-Command -Noun Variable
```

Um Hilfe zu einem bestimmten Cmdlet zu erhalten, geben Sie Folgendes ein:

```powershell
Get-Help <cmdlet-name>
```

| Cmdlet-Name       | BESCHREIBUNG                                |
| ---------------   | ------------------------------------------ |
| `Clear-Variable`  | Löscht den Wert einer Variablen.           |
| `Get-Variable`    | Ruft die Variablen in der aktuellen Konsole ab. |
| `New-Variable`    | Erstellt eine neue Variable.                    |
| `Remove-Variable` | Löscht eine Variable und ihren Wert.          |
| `Set-Variable`    | Ändert den Wert einer Variablen.           |

## <a name="see-also"></a>Weitere Informationen:

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Preference_Variables](about_Preference_Variables.md)

[about_Profiles](about_Profiles.md)

[about_Quoting_Rules](about_Quoting_Rules.md)

[about_Scopes](about_Scopes.md)

[about_Remote_Variables](about_Remote_Variables.md)
