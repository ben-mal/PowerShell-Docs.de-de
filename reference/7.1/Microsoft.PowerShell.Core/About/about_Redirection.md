---
description: Erläutert, wie die Ausgabe von PowerShell an Textdateien umgeleitet wird.
Locale: en-US
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_redirection?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Redirection
ms.openlocfilehash: 85b719b7af11cce2396e7d62fcc638007b55c834
ms.sourcegitcommit: b9826dcf402db8a2b6d3eab37edb82c6af113343
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98040897"
---
# <a name="about-redirection"></a>Informationen über die Umleitung

## <a name="short-description"></a>Kurze Beschreibung
Erläutert, wie die Ausgabe von PowerShell an Textdateien umgeleitet wird.

## <a name="long-description"></a>Lange Beschreibung

PowerShell sendet die Ausgabe standardmäßig an den PowerShell-Host. In der Regel handelt es sich hierbei um die Konsolenanwendung. Sie können die Ausgabe jedoch an eine Textdatei weiterleiten, und Sie können die Fehlerausgabe an den regulären Ausgabedatenstrom umleiten.

Zum Umleiten der Ausgabe können Sie die folgenden Methoden verwenden:

- Verwenden Sie das- `Out-File` Cmdlet, das die Befehlsausgabe an eine Textdatei sendet.
  In der Regel verwenden Sie das `Out-File` Cmdlet, wenn Sie die Parameter,, oder verwenden müssen `Encoding` `Force` `Width` `NoClobber` .

- Verwenden `Tee-Object` Sie das-Cmdlet, das die Befehlsausgabe an eine Textdatei sendet und Sie dann an die Pipeline sendet.

- Verwenden Sie die PowerShell-Umleitungs Operatoren. Die Verwendung des Umleitungs Operators mit einem Dateiziel ist mit der Weiterleitung an `Out-File` ohne zusätzliche Parameter funktional äquivalent.

Weitere Informationen zu Streams finden Sie unter [about_Output_Streams](about_Output_Streams.md).

### <a name="redirectable-output-streams"></a>Redirectable-Ausgabestreams

PowerShell unterstützt die Umleitung der folgenden Ausgabedaten Ströme.

| Streich # |      Beschreibung       | Eingeführt in  |    Cmdlet schreiben     |
| -------- | ---------------------- | -------------- | ------------------- |
| 1        | **Erfolg** Streich     | PowerShell 2.0 | `Write-Output`      |
| 2        | **Fehler** Streich       | PowerShell 2.0 | `Write-Error`       |
| 3        | **Warnung** Streich     | PowerShell 3.0 | `Write-Warning`     |
| 4        |  Ausführlich Streich     | PowerShell 3.0 | `Write-Verbose`     |
| 5        | **Debuggen** Streich       | PowerShell 3.0 | `Write-Debug`       |
| 6        | **Informationen** Streich | PowerShell 5.0 | `Write-Information` |
| *        | Alle Streams            | PowerShell 3.0 |                     |

> [!NOTE]
> In PowerShell gibt es auch einen **Fortschritts** Datenstrom, der jedoch keine Umleitung unterstützt.

### <a name="powershell-redirection-operators"></a>PowerShell-Umleitungs Operatoren

Die PowerShell-Umleitungs Operatoren lauten wie folgt, wobei `n` die streamnummer darstellt. Der **Success** Stream ( `1` ) ist der Standardwert, wenn kein Stream angegeben wird.

| Operator |                         BESCHREIBUNG                         | Syntax |
| -------- | ----------------------------------------------------------- | ------ |
| `>`      | Sendet den angegebenen Stream an eine Datei.                            | `n>`   |
| `>>`     | **Anfügen** des angegebenen Streams an eine Datei.                      | `n>>`  |
| `>&1`    | _Leitet_ den angegebenen Stream an den **Erfolgs** Datenstrom um. | `n>&1` |

> [!NOTE]
> Im Gegensatz zu einigen Unix-Shells können Sie nur andere Streams an den **Erfolgs** Datenstrom umleiten.

## <a name="examples"></a>Beispiele

### <a name="example-1-redirect-errors-and-output-to-a-file"></a>Beispiel 1: Umleiten von Fehlern und Ausgaben in eine Datei

Dieses Beispiel wird `dir` für ein Element ausgeführt, das erfolgreich ausgeführt werden kann, und eines, das einen Fehler verursacht.

```powershell
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
```

Es verwendet, `2>&1` um den **Fehler** Datenstrom an den **Success** -Stream umzuleiten und `>` den resultierenden **Erfolgs** Datenstrom an eine Datei mit dem Namen `dir.log`

### <a name="example-2-send-all-success-stream-data-to-a-file"></a>Beispiel 2: Senden aller Erfolgs Datenstrom Daten an eine Datei

In diesem Beispiel werden alle **Erfolgs** Datenstrom Daten an eine Datei mit dem Namen gesendet `script.log` .

```powershell
.\script.ps1 > script.log
```

### <a name="example-3-send-success-warning-and-error-streams-to-a-file"></a>Beispiel 3: Senden von Erfolgs-, Warnungs-und Fehler Datenströmen an eine Datei

Dieses Beispiel zeigt, wie Sie Umleitungs Operatoren kombinieren können, um ein gewünschtes Ergebnis zu erzielen.

```powershell
&{
   Write-Warning "hello"
   Write-Error "hello"
   Write-Output "hi"
} 3>&1 2>&1 > C:\Temp\redirection.log
```

- `3>&1` leitet den **Warnungs** Datenstrom an den **Erfolgs** Datenstrom um.
- `2>&1` leitet den **Fehler** Datenstrom an den **Success** -Stream um (der jetzt auch alle **Warnungs** Datenstrom Daten enthält)
- `>` leitet den **Erfolgs** Datenstrom (der nun sowohl **Warnungs** -als auch **Fehler** Datenströme enthält) in eine Datei mit `C:\temp\redirection.log` dem Namen um.

### <a name="example-4-redirect-all-streams-to-a-file"></a>Beispiel 4: Umleiten aller Streams an eine Datei

In diesem Beispiel werden alle Streams-Ausgaben von einem Skript namens `script.ps1` an eine Datei mit dem Namen gesendet. `script.log`

```powershell
.\script.ps1 *> script.log
```

### <a name="example-5-suppress-all-write-host-and-information-stream-data"></a>Beispiel 5: unterdrücken aller Write-Host-und Informationsdaten Strom Daten

In diesem Beispiel werden alle Datenstrom Daten unterdrückt. Weitere Informationen zu Cmdlets für den **Informations** Strom finden Sie unter [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) und [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) .

```powershell
&{
   Write-Host "Hello"
   Write-Information "Hello" -InformationAction Continue
} 6> $null
```

### <a name="example-6-show-the-effect-of-action-preferences"></a>Beispiel 6: Anzeigen der Auswirkung von Aktions Einstellungen

Aktions Einstellungs Variablen und Parameter können ändern, was in einen bestimmten Stream geschrieben wird. Das Skript in diesem Beispiel zeigt, wie sich der Wert von auf den Wert `$ErrorActionPreference` auswirkt, der in den **Fehler** Datenstrom geschrieben wird.

```powershell
$ErrorActionPreference = 'Continue'
$ErrorActionPreference > log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'SilentlyContinue'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Stop'
$ErrorActionPreference >> log.txt
Try {
    get-item /not-here 2>&1 >> log.txt
}
catch {
    "`tError caught!" >> log.txt
}
$ErrorActionPreference = 'Ignore'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Inquire'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Continue'
```

Wenn Sie dieses Skript ausführen, werden Sie aufgefordert `$ErrorActionPreference` , wenn auf festgelegt ist `Inquire` .

```powershell
PS C:\temp> .\test.ps1

Confirm
Cannot find path 'C:\not-here' because it does not exist.
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): H
Get-Item: C:\temp\test.ps1:23
Line |
  23 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The running command stopped because the user selected the Stop option.
```

Wenn wir die Protokolldatei untersuchen, wird Folgendes angezeigt:

```
PS C:\temp> Get-Content .\log.txt
Continue

Get-Item: C:\temp\test.ps1:3
Line |
   3 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | Cannot find path 'C:\not-here' because it does not exist.

SilentlyContinue
Stop
    Error caught!
Ignore
Inquire
```

## <a name="notes"></a>Hinweise

Die Umleitungs Operatoren, die keine Daten anfügen ( `>` und `n>` ), überschreiben den aktuellen Inhalt der angegebenen Datei ohne Warnung.

Wenn die Datei jedoch eine schreibgeschützte, verborgene oder Systemdatei ist, tritt ein Fehler bei der **Umleitung auf**. Die Anfüge Weiterleitungs Operatoren ( `>>` und `n>>` ) schreiben nicht in eine schreibgeschützte Datei, fügen aber Inhalte an ein System oder eine ausgeblendete Datei an.

Verwenden Sie das Cmdlet mit dem-Parameter, um die Umleitung von Inhalt in eine schreibgeschützte, verborgene oder Systemdatei zu erzwingen `Out-File` `Force` .

Beim Schreiben in Dateien verwenden die Umleitungs Operatoren die `UTF8NoBOM` Codierung. Wenn die Datei eine andere Codierung hat, ist die Ausgabe möglicherweise nicht ordnungsgemäß formatiert. Um in Dateien mit einer anderen Codierung zu schreiben, verwenden Sie das- `Out-File` Cmdlet mit dem- `Encoding` Parameter.

### <a name="potential-confusion-with-comparison-operators"></a>Mögliche Verwirrung mit Vergleichs Operatoren

Der `>` Operator muss nicht mit dem Operator " [größer als](about_Comparison_Operators.md#-gt--ge--lt-and--le) Vergleichs Operator" verwechselt werden (oftmals als `>` in anderen Programmiersprachen bezeichnet).

Abhängig von den verglichenen Objekten kann die Ausgabe mit `>` korrekt erscheinen (da 36 nicht größer als 42 ist).

```powershell
PS> if (36 > 42) { "true" } else { "false" }
false
```

Eine Überprüfung des lokalen Dateisystems kann jedoch sehen, dass eine Datei `42` mit dem Namen mit dem Inhalt geschrieben wurde `36` .

```powershell
PS> dir

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
------          1/02/20  10:10 am              3 42

PS> cat 42
36
```

Wenn Sie versuchen, den umgekehrten Vergleich `<` (kleiner als) zu verwenden, ergibt sich ein Systemfehler:

```powershell
PS> if (36 < 42) { "true" } else { "false" }
ParserError:
Line |
   1 |  if (36 < 42) { "true" } else { "false" }
     |         ~
     | The '<' operator is reserved for future use.
```

Wenn der numerische Vergleich der erforderliche Vorgang ist `-lt` , `-gt` sollte verwendet werden. Weitere Informationen finden Sie unter dem- `-gt` Operator in [about_Comparison_Operators](about_Comparison_Operators.md#-gt--ge--lt-and--le).

## <a name="see-also"></a>Weitere Informationen

- [Out-File](xref:Microsoft.PowerShell.Utility.Out-File)
- [Tee-Object](xref:Microsoft.PowerShell.Utility.Tee-Object)
- [Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [Write-Error](xref:Microsoft.PowerShell.Utility.Write-Error)
- [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host)
- [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)
- [Write-Output](xref:Microsoft.PowerShell.Utility.Write-Output)
- [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [about_Output_Streams](about_Output_Streams.md)
- [about_Operators](about_Operators.md)
- [about_Command_Syntax](about_Command_Syntax.md)
- [about_Path_Syntax](about_Path_Syntax.md)
