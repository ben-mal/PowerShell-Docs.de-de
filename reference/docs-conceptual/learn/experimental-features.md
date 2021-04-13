---
ms.date: 12/14/2020
title: Verwenden experimenteller Features in PowerShell
description: In diesem Artikel wird beschrieben, welche experimentellen Features verfügbar sind und wie sie verwendet werden.
ms.openlocfilehash: 828a962ca46e5563874ff1c941c46c8a0624f3d8
ms.sourcegitcommit: f6cc3752463b254f6ba7fc14c1e4532ad33f06bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2021
ms.locfileid: "107216893"
---
# <a name="using-experimental-features-in-powershell"></a>Verwenden experimenteller Features in PowerShell

Die Unterstützung experimenteller Features in PowerShell stellt einen Mechanismus bereit, über den experimentelle Features und vorhandene stabile Features in PowerShell oder PowerShell-Modulen parallel genutzt werden können.

Ein experimentelles Feature ist ein Feature, dessen Design noch nicht finalisiert wurde. Das Feature wird bereitgestellt, damit die Benutzer es testen und Feedback dazu senden können. Sobald ein experimentelles Feature finalisiert wurde, werden die Designänderungen zu Breaking Changes.

> [!CAUTION]
> Experimentelle Features sind nicht für den Einsatz in der Produktion vorgesehen, da Auswirkungen auf die Lauffähigkeit möglich sind. Experimentelle Features werden nicht offiziell unterstützt. Wir freuen uns jedoch über Feedback und Fehlermeldungen. Sie können Probleme im [GitHub-Quellrepository](https://github.com/PowerShell/PowerShell/issues/new/choose) melden.

Weitere Informationen zum Aktivieren oder Deaktivieren dieser Features finden Sie unter [Grundlegendes zu experimentellen Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).

## <a name="available-features"></a>Verfügbare Features

Dieser Artikel beschreibt, welche experimentellen Features verfügbar sind und wie sie verwendet werden.

|                            Name                            |   6.2   |   7.0   |   7.1   |   7.2   |
| ---------------------------------------------------------- | :-----: | :-----: | :-----: | :-----: |
| PSTempDrive (allgemeine Unterstützung in PS 7.0 und höher)                        | &check; |         |         |         |
| PSUseAbbreviationExpansion (allgemeine Unterstützung in PS 7.0 und höher)         | &check; |         |         |         |
| PSNullConditionalOperators (Mainstream in PS 7.1+)         |         | &check; |         |         |
| PSUnixFileStat (nur Nicht-Windows; üblich ab PowerShell 7.1)  |         | &check; |         |         |
| PSCommandNotFoundSuggestion                                | &check; | &check; | &check; | &check; |
| PSImplicitRemotingBatching                                 | &check; | &check; | &check; | &check; |
| Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace |         | &check; | &check; | &check; |
| PSDesiredStateConfiguration.InvokeDscResource              |         | &check; | &check; | &check; |
| PSNativePSPathResolution                                   |         |         | &check; | &check; |
| PSCultureInvariantReplaceOperator                          |         |         | &check; | &check; |
| PSNotApplyErrorActionToStderr                              |         |         | &check; | &check; |
| PSSubsystemPluginModel                                     |         |         | &check; | &check; |
| PSAnsiProgress                                             |         |         |         | &check; |
| PSAnsiRendering                                            |         |         |         | &check; |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a>Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace

In PowerShell 7.0 aktiviert das Experiment den Parameter **BreakAll** für die Cmdlets `Debug-Runspace` und `Debug-Job`, damit Benutzer entscheiden können, ob PowerShell an der aktuellen Stelle sofort unterbrechen soll, wenn ein Debugger angefügt wird.

In PowerShell 7.1 fügt dieses Experiment auch den Parameter **Runspace** den `*-PSBreakpoint`-Cmdlets hinzu.

- `Disable-PSBreakpoint`
- `Enable-PSBreakpoint`
- `Get-PSBreakpoint`
- `Remove-PSBreakpoint`
- `Set-PSBreakpoint`

Der **Runspace**-Parameter gibt ein **Runspace**-Objekt an, mit dem im angegebenen Runspace mit Haltepunkt	en interagiert wird.

```powershell
Start-Job -ScriptBlock {
    Set-PSBreakpoint -Command Start-Sleep
    Start-Sleep -Seconds 10
}

$runspace = Get-Runspace -Id 1

$breakpoint = Get-PSBreakPoint -Runspace $runspace
```

In diesem Beispiel wird ein Auftrag gestartet und ein Haltepunkt ist für die Ausführung des `Set-PSBreakPoint` festgelegt. Der Runspace wird in einer Variablen gespeichert und mit dem **Runspace**-Parameter an den `Get-PSBreakPoint`-Befehl übergeben. Sie können dann den Haltepunkt in der `$breakpoint`-Variablen überprüfen.

## <a name="psansirendering"></a>PSAnsiRendering

Dieses Experiment wurde in PowerShell 7.2 hinzugefügt. Mithilfe dieses Features können Sie ändern, auf welche Weise die PowerShell-Engine Text ausgibt, und Sie können die automatische Variable `$PSStyle` hinzufügen, um das ANSI-Rendering der Zeichenfolgenausgabe zu steuern.

```powershell
PS> $PSStyle | Get-Member

   TypeName: System.Management.Automation.PSStyle

Name             MemberType Definition
----             ---------- ----------
Equals           Method     bool Equals(System.Object obj)
FormatHyperlink  Method     string FormatHyperlink(string text, uri link)
GetHashCode      Method     int GetHashCode()
GetType          Method     type GetType()
ToString         Method     string ToString()
Background       Property   System.Management.Automation.PSStyle+BackgroundColor Background {get;}
Blink            Property   string Blink {get;}
BlinkOff         Property   string BlinkOff {get;}
Bold             Property   string Bold {get;}
BoldOff          Property   string BoldOff {get;}
Foreground       Property   System.Management.Automation.PSStyle+ForegroundColor Foreground {get;}
Formatting       Property   System.Management.Automation.PSStyle+FormattingData Formatting {get;}
Hidden           Property   string Hidden {get;}
HiddenOff        Property   string HiddenOff {get;}
Italic           Property   string Italic {get;}
ItalicOff        Property   string ItalicOff {get;}
OutputRendering  Property   System.Management.Automation.OutputRendering OutputRendering {get;set;}
Progress         Property   System.Management.Automation.PSStyle+ProgressConfiguration Progress {get;}
Reset            Property   string Reset {get;}
Reverse          Property   string Reverse {get;}
ReverseOff       Property   string ReverseOff {get;}
Strikethrough    Property   string Strikethrough {get;}
StrikethroughOff Property   string StrikethroughOff {get;}
Underline        Property   string Underline {get;}
UnderlineOff     Property   string UnderlineOff {get;}
```

Die Basismember geben Zeichenfolgen von ANSI-Escapesequenzen zurück, die ihren Namen zugeordnet sind. Die Werte können beliebig angepasst werden.

Weitere Informationen finden Sie unter [about_Automatic_Variables](/powershell/module/Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).

> [!NOTE]
> C# Entwickler können auf `PSStyle` als Singleton zugreifen. Dies sieht wie folgt aus:
>
> ```csharp
> string output = $"{PSStyle.Instance.Foreground.Red}{PSStyle.Instance.Bold}Hello{PSStyle.Instance.Reset}";
> ```
>
> `PSStyle` ist im Namespace „System.Management.Automation“ enthalten.

Zusammen mit dem Zugriff auf `$PSStyle` werden dadurch Änderungen an der PowerShell-Engine eingeführt. Das PowerShell-Formatierungssystem wird aktualisiert, um `$PSStyle.OutputRendering` zu berücksichtigen.

- Der Typ `StringDecorated` wird hinzugefügt, damit ANSI-Escapezeichenfolgen verarbeitet werden können.
- Die boolesche Eigenschaft `string IsDecorated` wird hinzugefügt, wenn die Zeichenfolge ANSI-Escapesequenzen enthält. Dabei wird berücksichtigt, ob die Zeichenfolge die Elemente „ESC“ und „C1 CSI“ enthält.
- Die Eigenschaft `Length` gibt _nur_ die Länge des Texts ohne die ANSI-Escapesequenzen zurück.
- Die Methode `StringDecorated Substring(int contentLength)` gibt eine Teilzeichenfolge zurück, die beim Index 0 beginnt und bis zur Inhaltslänge reicht, die nicht Teil der ANSI-Escapesequenzen ist. Dies ist notwendig, damit Zeichenfolgen durch Tabellenformatierungen abgeschnitten und ANSI-Escapesequenzen beibehalten werden können, die keinen druckbaren Zeichenbereich belegen.
- Die Methode `string ToString()` bleibt unverändert und gibt die Klartextversion der Zeichenfolge zurück.
- Die Methode `string ToString(bool Ansi)` gibt die unformatierte ANSI Embedded-Zeichenfolge zurück, wenn der Parameter `Ansi` „true“ ist. Andernfalls wird eine Klartextversion zurückgegeben, aus der die ANSI-Escapesequenzen entfernt wurden.

`FormatHyperlink(string text, uri link)` gibt eine Zeichenfolge zurück, die eine ANSI-Escapesequenz zum Ergänzen von Hyperlinks enthält. Einige Terminalhosts wie der [Windows-Terminal](https://www.microsoft.com/p/windows-terminal/9n0dx20hk701) unterstützen dieses Markup, wodurch der gerenderte Text im Terminal klickbar wird.

## <a name="psansiprogress"></a>PSAnsiProgress

Dieses Experiment wurde in PowerShell 7.2 hinzugefügt. Mit der Funktion wird das `$PSStyle.Progress`-Mitglied hinzugefügt, und Sie können das Rendern von Statusansichtsleisten steuern.

- `$PSStyle.Progress.Style`: Eine ANSI-Zeichenfolge, die den Renderingstil festlegt.
- `$PSStyle.Progress.MaxWidth`: Legt die maximale Breite der Ansicht fest. Für die Konsolenbreite auf `0` festlegen.
  Der Standardwert lautet `120`.
- `$PSStyle.Progress.View`: Eine Enumeration mit den Werten `Minimal` und `Classic`. `Classic` ist das vorhandene Rendering ohne Änderungen. `Minimal` ist ein einzeiliges minimales Rendering. `Minimal` ist die Standardeinstellung.

Im folgenden Beispiel wird der Renderingstil auf eine minimale Statusanzeige aktualisiert.

```powershell
$PSStyle.Progress.View.Minimal
```

> [!NOTE]
> Um dieses Feature verwenden zu können, muss das experimentelle Feature **PSAnsiRendering** aktiviert sein.

## <a name="pscommandnotfoundsuggestion"></a>PSCommandNotFoundSuggestion

Empfiehlt potenzielle Befehle basierend auf einer Fuzzysuche nach einer **CommandNotFoundException**.

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a>PSCultureInvariantReplaceOperator

Wenn der linke Operand in einer `-replace`-Operatoranweisung keine Zeichenfolge ist, wird dieser Operand in eine Zeichenfolge konvertiert.

Ist dieses Feature deaktiviert, führt der `-replace`-Operator eine Zeichenfolgenkonvertierung mit Kulturerkennung durch.
Wenn Ihre Kultur beispielsweise auf „Französisch (fr)“ festgelegt ist, wird der Wert `1.2` in die Zeichenfolge `1,2` konvertiert.

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

Bei aktiviertem Feature:

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a>PSDesiredStateConfiguration.InvokeDscResource

Aktiviert die Kompilierung in MOF auf Nicht-Windows-Systemen sowie die Verwendung von `Invoke-DSCResource` ohne LCM.

## <a name="psimplicitremotingbatching"></a>PSImplicitRemotingBatching

Dieses Feature untersucht den Befehl, der in die Shell eingegeben wurde. Wenn alle Befehle implizite Remotingproxybefehle sind, die eine einfache Pipeline bilden, werden die Befehle in einem Batch zusammengefasst und als eine einzige Remotepipeline aufgerufen.

Beispiel:

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

Wie oben gezeigt, werden bei Aktivierung des Features für die Batcherstellung alle drei impliziten Remotingproxybefehle (`Get-AllProcesses`, `Select-Custom`, `Group-Stuff`) in der Remotesitzung ausgeführt, und es wird nur das Ergebnis der Pipeline an den Client zurückgegeben. Dies verringert die Datenmenge, die zwischen Client und Remotesitzung gesendet wird und reduziert außerdem den Aufwand für die Objektserialisierung und -deserialisierung.

## <a name="psnativepspathresolution"></a>PSNativePSPathResolution

Bei Übergabe eines PSDrive-Pfads mit Verwendung des FileSystem-Anbieters an einen nativen Befehl wird der aufgelöste Dateipfad an den nativen Pfad Befehl übergeben. Dies bedeutet, dass ein Befehl wie `code temp:/test.txt` jetzt wie erwartet funktioniert.

Darüber hinaus gilt unter Windows Folgendes: Wenn der Pfad mit `~` beginnt, wird dieser in den vollständigen Pfad aufgelöst und an den nativen Befehl übergeben. In beiden Fällen wird der Pfad auf die Verzeichnistrennzeichen für das jeweilige Betriebssystem normalisiert.

- Handelt es sich bei dem Pfad nicht um ein PSDrive oder `~` (unter Windows), erfolgt keine Pfadnormalisierung.
- Wird der Pfad in einfachen Anführungszeichen angegeben, wird er nicht aufgelöst und als Literal betrachtet.

## <a name="psnotapplyerroractiontostderr"></a>PSNotApplyErrorActionToStderr

Wenn dieses experimentelle Feature aktiviert ist, werden Fehlerdatensätze, die von nativen Befehlen umgeleitet werden, wie bei der Verwendung von Umleitungsoperatoren (`2>&1`), nicht in die `$Error`-Variable geschrieben, und die Einstellungsvariable `$ErrorActionPreference` beeinflusst die umgeleitete Ausgabe nicht.

Viele native Befehle schreiben in `stderr` als alternativen Stream für weitere Informationen. Dieses Verhalten kann beim Durchsehen von Fehlern Verwirrung verursachen, oder die zusätzlichen Ausgabeinformationen können für den Benutzer verloren gehen, wenn `$ErrorActionPreference` auf einen Zustand festgelegt ist, der die Ausgabe unterdrückt.

Wenn ein nativer Befehl einen Exitcode ungleich 0 (null) aufweist, wird `$?` auf `$false` festgelegt. Wenn der Exitcode 0 (null) ist, wird `$?` auf `$true` festgelegt.

## <a name="psnullconditionaloperators"></a>PSNullConditionalOperators

Hiermit werden neue Operatoren für den NULL-bedingten Memberzugriff eingeführt: `?.` und `?[]`. Operatoren für den NULL-Memberzugriff können für Skalar- und Arraytypen verwendet werden. Geben Sie den Wert des Members zurück, auf den zugegriffen wurde, wenn die Variable ungleich NULL ist. Lautet der Wert der Variablen NULL, geben Sie NULL zurück.

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

Es wird auf die Eigenschaft `propname` zugegriffen, und ihr Wert wird nur zurückgegeben, wenn `$x` nicht NULL lautet. Ähnlich wird der Indexer nur verwendet, wenn `$x` nicht NULL lautet. Wenn `$x` NULL ist, wird NULL zurückgegeben.

Die Operatoren `?.` und `?[]` sind Memberzugriffsoperatoren und lassen kein Leerzeichen zwischen dem Variablennamen und dem Operator zu.

Da PowerShell `?` als Bestandteil des Variablennamens zulässt, muss Eindeutigkeit gewährleistet werden, wenn Operatoren ohne Leerzeichen zwischen dem Variablennamen und dem Operator verwendet werden. Zur Unterscheidung muss der Name der Variablen in `{}` eingeschlossen werden. Beispiel: `${x?}?.propertyName` oder `${y}?[0]`.

> [!NOTE]
> Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7.1 und höher jetzt allgemein unterstützt.

## <a name="pstempdrive"></a>PSTempDrive

Erstellt das PSDrive `TEMP:`, das dem temporären Verzeichnispfad des Benutzers zugeordnet ist.

> [!NOTE]
> Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7 und höher jetzt allgemein unterstützt.

## <a name="psunixfilestat"></a>PSUnixFileStat

Dieses Feature bietet ein neues Verhalten zum Einschließen von Daten aus der **stat**-API unter Unix in die Ausgabe des Dateisystemanbieters, um eine Unix-ähnlichere Dateiliste zu ermöglichen. Es wird im Dateisystemanbieter eine neue NoteProperty namens **UnixStat** hinzugefügt, die einen gemeinsamen Ausdruck der `stat(2)`-API aus dem zugrunde liegenden Unix-Typsystem enthält.

Die Ausgabe von `Get-ChildItem` sollte ungefähr wie folgt aussehen:

```powershell
dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

> [!NOTE]
> Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7.1 und höher jetzt allgemein unterstützt.

## <a name="psuseabbreviationexpansion"></a>PSUseAbbreviationExpansion

Dieses Feature aktiviert die Vervollständigung abgekürzter Cmdlets und Funktionen mit der TAB-TASTE:

Beispiel:

- `Import-PowerShellDataFile` gibt `i-psdf<tab>` zurück.
- `u-akvmssdr<tab>` gibt `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval` zurück.

Dies funktioniert nur für die Vervollständigung mit der TAB-TASTE (interaktive Verwendung), deshalb ist `i-psdf` kein gültiger Name eines Cmdlets in einem Skript.

> [!NOTE]
> Dieses Feature befindet sich nicht mehr in der experimentellen Phase und wird in PowerShell 7 und höher jetzt allgemein unterstützt.

## <a name="pssubsystempluginmodel"></a>PSSubsystemPluginModel

Dieses Feature aktiviert das Plug-In-Modell des Subsystems in PowerShell. Es ermöglicht das Trennen von Komponenten von `System.Management.Automation.dll` in einzelne Subsysteme, die sich in einer eigenen Assembly befinden. Diese Trennung reduziert den Speicherbedarf des Datenträgers der Kern-Engine von PowerShell. Zudem werden diese Komponenten zu optionalen Features für eine Minimalinstallation von PowerShell.

Derzeit wird nur das Subsystem **CommandPredictor** unterstützt. Dieses Subsystem wird zusammen mit dem PSReadLine-Modul zum Bereitstellen benutzerdefinierter Vorhersage-Plug-Ins verwendet. Zukünftig können **Job**, **CommandCompleter**, **Remoting** und andere Komponenten in Subsystemassemblys außerhalb von `System.Management.Automation.dll` getrennt werden.

Das experimentelle Feature enthält das neue Cmdlet [Get-PSSubsystem](xref:Microsoft.PowerShell.Core.Get-PSSubsystem). Dieses Cmdlet ist nur verfügbar, wenn das Feature aktiviert ist. Es gibt Informationen zu den Subsystemen zurück, die auf dem System verfügbar sind.
