---
description: Variablen, die das Verhalten von PowerShell anpassen.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: 25677cf687349bf805b66a116d3b2f09d27037bd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222644"
---
# <a name="about-preference-variables"></a>Informationen zu Einstellungs Variablen

## <a name="short-description"></a>Kurze Beschreibung

Variablen, die das Verhalten von PowerShell anpassen.

## <a name="long-description"></a>Lange Beschreibung

PowerShell enthält eine Reihe von Variablen, mit deren Hilfe Sie das Verhalten anpassen können. Diese Einstellungs Variablen funktionieren wie die Optionen in GUI-basierten Systemen.

Die Einstellungs Variablen wirken sich auf die PowerShell-Betriebsumgebung und alle Befehle aus, die in der Umgebung ausgeführt werden. In vielen Fällen verfügen die Cmdlets über Parameter, die Sie verwenden können, um das Einstellungs Verhalten für einen bestimmten Befehl zu überschreiben.

In der folgenden Tabelle sind die Einstellungs Variablen und ihre Standardwerte aufgeführt.

|             Variable             |       Standardwert       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | High                      |
| `$DebugPreference`               | SilentlyContinue          |
| `$ErrorActionPreference`         | Continue                  |
| `$ErrorView`                     | Normalansicht                |
| `$FormatEnumerationLimit`        | 4                         |
| `$InformationPreference`         | SilentlyContinue          |
| `$LogCommandHealthEvent`         | False (nicht protokolliert)        |
| `$LogCommandLifecycleEvent`      | False (nicht protokolliert)        |
| `$LogEngineHealthEvent`          | True (protokolliert)             |
| `$LogEngineLifecycleEvent`       | True (protokolliert)             |
| `$LogProviderLifecycleEvent`     | True (protokolliert)             |
| `$LogProviderHealthEvent`        | True (protokolliert)             |
| `$MaximumAliasCount`             | 4096                      |
| `$MaximumDriveCount`             | 4096                      |
| `$MaximumErrorCount`             | 256                       |
| `$MaximumFunctionCount`          | 4096                      |
| `$MaximumHistoryCount`           | 4096                      |
| `$MaximumVariableCount`          | 4096                      |
| `$OFS`                           | (Leerzeichen ( `" "` )) |
| `$OutputEncoding`                | **ASCIIEncoding** -Objekt  |
| `$ProgressPreference`            | Weiter                  |
| `$PSDefaultParameterValues`      | (Keine-leere Hash Tabelle) |
| `$PSEmailServer`                 | (Keine)                    |
| `$PSModuleAutoLoadingPreference` | Alle                       |
| `$PSSessionApplicationName`      | wsman                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | Siehe [$PSSessionOption](#pssessionoption) |
| `$Transcript`                    | (none)                    |
| `$VerbosePreference`             | SilentlyContinue          |
| `$WarningPreference`             | Continue                  |
| `$WhatIfPreference`              | False                     |

PowerShell umfasst die folgenden Umgebungsvariablen, in denen Benutzereinstellungen gespeichert werden. Weitere Informationen zu diesen Umgebungsvariablen finden Sie unter [about_Environment_Variables](about_Environment_Variables.md).

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> Änderungen an der Einstellungs Variablen werden nur in Skripts und Funktionen wirksam, wenn diese Skripts oder Funktionen im gleichen Bereich wie der Bereich definiert werden, in dem die bevorzugte Verwendung verwendet wurde. Weitere Informationen finden Sie unter [about_Scopes](about_Scopes.md).

## <a name="working-with-preference-variables"></a>Arbeiten mit Einstellungs Variablen

In diesem Dokument werden die einzelnen Einstellungs Variablen beschrieben.

Um den aktuellen Wert einer bestimmten Einstellungs Variablen anzuzeigen, geben Sie den Namen der Variablen ein. Der folgende Befehl zeigt z `$ConfirmPreference` . b. den Wert der Variablen an.

```powershell
 $ConfirmPreference
```

```Output
High
```

Verwenden Sie eine Zuweisungsanweisung, um den Wert einer Variablen zu ändern. Mit der folgenden Anweisung wird beispielsweise der `$ConfirmPreference` Wert des Parameters in **Mittel** geändert.

```powershell
$ConfirmPreference = "Medium"
```

Die von Ihnen festgelegten Werte sind spezifisch für die aktuelle PowerShell-Sitzung. Fügen Sie Sie Ihrem PowerShell-Profil hinzu, damit Variablen in allen PowerShell-Sitzungen wirksam werden. Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).

## <a name="working-remotely"></a>Remote arbeiten

Wenn Sie Befehle auf einem Remote Computer ausführen, unterliegen die Remote Befehle nur den Einstellungen, die im PowerShell-Client des Remote Computers festgelegt sind. Wenn Sie z. b. einen Remote Befehl ausführen, bestimmt der Wert der Variablen des Remote Computers, `$DebugPreference` wie PowerShell auf das Debuggen von Nachrichten reagiert.

Weitere Informationen zu Remote Befehlen finden Sie unter [about_Remote](about_Remote.md).

### <a name="confirmpreference"></a>\$Confirmpreference

Bestimmt, ob PowerShell Sie vor dem Ausführen eines Cmdlets oder einer Funktion automatisch zur Bestätigung auffordert.

Die `$ConfirmPreference` gültigen Werte der Variablen sind **hoch** , **Mittel** oder **niedrig**. Cmdlets und Funktionen werden das Risiko " **hoch** ", " **Mittel** " oder " **niedrig** " zugewiesen. Wenn der Wert der `$ConfirmPreference` Variablen kleiner als oder gleich dem Risiko ist, das einem Cmdlet oder einer Funktion zugewiesen ist, werden Sie von PowerShell automatisch zur Bestätigung aufgefordert, bevor Sie das Cmdlet oder die Funktion ausführen.

Wenn der Wert der `$ConfirmPreference` Variablen **None** lautet, werden Sie von PowerShell nie automatisch vor dem Ausführen eines Cmdlets oder einer Funktion aufgefordert.

Um das Bestätigungs Verhalten für alle Cmdlets und Funktionen in der Sitzung zu ändern, ändern Sie den `$ConfirmPreference` Wert der Variablen.

Um den `$ConfirmPreference` für einen einzelnen Befehl zu überschreiben, verwenden Sie den **Confirm** -Parameter eines Cmdlets oder einer Funktion. Verwenden Sie, um eine Bestätigung anzufordern `-Confirm` . Verwenden Sie, um die Bestätigung zu unterdrücken `-Confirm:$false` .

Gültige Werte `$ConfirmPreference` :

- **Keine** : PowerShell wird nicht automatisch zur Eingabe aufgefordert. Um die Bestätigung eines bestimmten Befehls anzufordern, verwenden Sie den **Confirm** -Parameter des Cmdlets oder der Funktion.
- **Niedrig** : PowerShell fordert vor der Ausführung von Cmdlets oder Funktionen mit einem niedrigen, mittleren oder hohen Risiko eine Bestätigung an.
- **Mittel** : PowerShell fordert vor dem Ausführen von Cmdlets oder Funktionen mit einem mittelgroßen oder hohen Risiko zur Bestätigung auf.
- **Hoch** : PowerShell fordert zur Bestätigung auf, bevor Cmdlets oder Funktionen mit hohem Risiko ausgeführt werden.

#### <a name="detailed-explanation"></a>Ausführliche Erläuterung

PowerShell kann Sie automatisch zur Bestätigung auffordern, bevor eine Aktion ausgeführt wird. Wenn z. b. ein Cmdlet oder eine Funktion das System erheblich beeinträchtigt, um Daten zu löschen oder eine beträchtliche Menge an Systemressourcen zu verwenden.

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

Die Schätzung des Risikos ist ein Attribut des Cmdlets oder der Funktion, das als **confirmimpact** bezeichnet wird. Benutzer können dies nicht ändern.

Cmdlets und Funktionen, die möglicherweise ein Risiko für das System darstellen, verfügen über einen **Confirm** -Parameter, den Sie verwenden können, um die Bestätigung für einen einzelnen Befehl anzufordern oder zu unterdrücken.

Da die meisten Cmdlets und Funktionen den Standard Risiko Wert " **confirmimpact** " von " **Medium** " verwenden und der Standardwert von " `$ConfirmPreference` **High** " ist, erfolgt die automatische Bestätigung selten. Sie können jedoch die automatische Bestätigung aktivieren, indem Sie den Wert von `$ConfirmPreference` auf **Mittel** oder **niedrig** ändern.

#### <a name="examples"></a>Beispiele

Dieses Beispiel zeigt die Auswirkung des `$ConfirmPreference` Standardwerts der Variablen, **hoch**. Der **hohe** Wert bestätigt nur risikoreiche Cmdlets und Funktionen. Da die meisten Cmdlets und Funktionen ein mittleres Risiko darstellen, werden Sie nicht automatisch bestätigt, und `Remove-Item` die Datei wird gelöscht. Durch das Hinzufügen `-Confirm` zum Befehl wird der Benutzer zur Bestätigung aufgefordert.

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

Verwenden `-Confirm` Sie, um eine Bestätigung anzufordern.

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

Das folgende Beispiel zeigt die Auswirkung der Änderung des Werts von `$ConfirmPreference` auf **Mittel**. Da die meisten Cmdlets und Funktionen ein mittleres Risiko darstellen, werden Sie automatisch bestätigt. Um die Bestätigungsaufforderung für einen einzelnen Befehl zu unterdrücken, verwenden Sie den **Confirm** -Parameter mit dem Wert `$false` .

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a>\$DebugPreference

Bestimmt, wie PowerShell auf das Debuggen von Nachrichten reagiert, die von einem Skript, Cmdlet oder Anbieter generiert wurden, oder über einen `Write-Debug` Befehl in der Befehlszeile.

In einigen Cmdlets werden Debugmeldungen angezeigt, bei denen es sich in der Regel um technische Meldungen handelt, die für Programmierer und technischen Support Standardmäßig werden keine Debugmeldungen angezeigt, Sie können jedoch Debugmeldungen anzeigen, indem Sie den Wert von ändern `$DebugPreference` .

Sie können den allgemeinen **Debug** -Parameter eines Cmdlets verwenden, um die Debugmeldungen für einen bestimmten Befehl anzuzeigen oder auszublenden. Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).

Die folgenden Werte sind gültig:

- **Beenden** : zeigt die Debugmeldung an und beendet die Ausführung. Schreibt einen Fehler in die Konsole.
- **Erkundigen** : zeigt die Debugmeldung an und fragt Sie, ob Sie den Vorgang fortsetzen möchten. Wenn Sie den allgemeinen **Debug** -Parameter einem Befehl hinzufügen, wenn der Befehl zum Generieren einer Debugmeldung konfiguriert ist, wird der Wert der `$DebugPreference` Variablen in " **fragt** " geändert.
- **Continue** : zeigt die Debugmeldung an und setzt die Ausführung fort.
- **SilentlyContinue** : (Standard) keine Auswirkung. Die Debugmeldung wird nicht angezeigt, und die Ausführung wird nicht unterbrochen

#### <a name="examples"></a>Beispiele

In den folgenden Beispielen wird gezeigt, wie sich die Werte von ändern, `$DebugPreference` Wenn ein `Write-Debug` Befehl in der Befehlszeile eingegeben wird.
Die Änderung wirkt sich auf alle Debugmeldungen aus, einschließlich der von Cmdlets und Skripts generierten Meldungen. Die Beispiele zeigen den **Debug** -Parameter, der die Debugmeldungen im Zusammenhang mit einem einzelnen Befehl anzeigt oder ausblendet.

Dieses Beispiel zeigt die Auswirkung des `$DebugPreference` Standardwerts der Variablen, **SilentlyContinue**. Standardmäßig wird die `Write-Debug` Debugmeldung des Cmdlets nicht angezeigt, und die Verarbeitung wird fortgesetzt. Wenn der **Debug** -Parameter verwendet wird, überschreibt er die bevorzugte Einstellung für einen einzelnen Befehl. Der Benutzer wird zur Bestätigung aufgefordert.

```powershell
$DebugPreference
```

```Output
SilentlyContinue
```

```powershell
Write-Debug -Message "Hello, World"
```

```powershell
Write-Debug -Message "Hello, World" -Debug
```

```Output
DEBUG: Hello, World
Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

Dieses Beispiel zeigt die Auswirkung von `$DebugPreference` mit dem Wert " **Continue** ". Die Debugmeldung wird angezeigt, und der Befehl wird weiterhin verarbeitet.

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken. Die Debugmeldung wird nicht angezeigt.

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

Dieses Beispiel zeigt die Auswirkung der `$DebugPreference` Festlegung auf den **Stop** Endzeit Wert. Die Debugmeldung wird angezeigt, und der Befehl wird beendet.

```powershell
$DebugPreference = "Stop"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
Write-Debug : The running command stopped because the preference variable
 "DebugPreference" or common parameter is set to Stop: Hello, World
At line:1 char:1
+ Write-Debug -Message "Hello, World"
```

Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken. Die Debugmeldung wird nicht angezeigt, und die Verarbeitung wird nicht beendet.

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

Dieses Beispiel zeigt die Auswirkung der `$DebugPreference` Festlegung auf den **Inquire** Wert "suchen". Die Debugmeldung wird angezeigt, und der Benutzer wird zur Bestätigung aufgefordert.

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

Dieses Beispiel verwendet den **Debug** -Parameter mit dem Wert `$false` , um die Meldung für einen einzelnen Befehl zu unterdrücken. Die Debugmeldung wird nicht angezeigt und die Verarbeitung wird fortgesetzt.

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a>\$ErrorActionPreference

Bestimmt, wie PowerShell auf einen Fehler ohne Abbruch antwortet, ein Fehler, der die Cmdlet-Verarbeitung nicht stoppt. Beispielsweise in der Befehlszeile oder in einem Skript, Cmdlet oder Anbieter, wie z. b. den vom `Write-Error` Cmdlet generierten Fehlern.

Sie können den allgemeinen **ErrorAction** -Parameter eines Cmdlets verwenden, um die Einstellung für einen bestimmten Befehl zu überschreiben.

Die folgenden Werte sind gültig:

- **Continue** (Standard): zeigt die Fehlermeldung an und setzt die Ausführung fort.
- **Ignore** : unterdrückt die Fehlermeldung und setzt die Ausführung des Befehls fort. Der Wert " **Ignore** " ist für die Verwendung per Befehls bestimmt, nicht für die Verwendung als gespeicherte Einstellung. **Ignore** ist kein gültiger Wert für die `$ErrorActionPreference` Variable.
- **Erkundigen** : zeigt die Fehlermeldung an und fragt Sie, ob Sie den Vorgang fortsetzen möchten.
- **SilentlyContinue** : keine Auswirkung. Die Fehlermeldung wird nicht angezeigt, und die Ausführung wird nicht unterbrochen.
- **Beenden** : zeigt die Fehlermeldung an und beendet die Ausführung. Zusätzlich zum Fehler, der generiert wurde, generiert der Wert " **Beenden** " ein "aktionpreferencestopexception"-Objekt in den Fehler Datenstrom.
  Datenstrom
- **Suspend** : hält einen Workflow Auftrag automatisch an, um weitere Untersuchungen zu ermöglichen. Nach der Untersuchung kann der Workflow fortgesetzt werden. Der **Suspend** -Wert ist für die Verwendung per Befehl bestimmt, nicht für die Verwendung als gespeicherte Einstellung. **Suspend** ist kein gültiger Wert für die `$ErrorActionPreference` Variable.

`$ErrorActionPreference` der **ErrorAction** -Parameter wirkt sich nicht darauf aus, wie PowerShell auf abschließende Fehler reagiert, die die Cmdlet-Verarbeitung beenden. Weitere Informationen zum allgemeinen **ErrorAction** -Parameter finden Sie unter [about_CommonParameters](about_CommonParameters.md).

#### <a name="examples"></a>Beispiele

Diese Beispiele zeigen die Auswirkung der verschiedenen Werte der `$ErrorActionPreference` Variablen. Der **ErrorAction** -Parameter wird verwendet, um den Wert zu überschreiben `$ErrorActionPreference` .

Dieses Beispiel zeigt den `$ErrorActionPreference` Standardwert " **Continue** ". Ein Fehler ohne Abbruch wird generiert. Die Meldung wird angezeigt, und die Verarbeitung wird fortgesetzt.

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error -Message  'Test Error' ; Write-Host 'Hello World' : Test Error
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

Hello World
```

In diesem Beispiel `$ErrorActionPreference` wird der Standardwert " **fragt** " angezeigt. Ein Fehler wird generiert, und es wird eine Eingabeaufforderung angezeigt.

```powershell
# Change the ErrorActionPreference to 'Inquire'
$ErrorActionPreference = 'Inquire'
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
```

```Output
Confirm
Test Error
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

Dieses Beispiel zeigt `$ErrorActionPreference` , dass auf **SilentlyContinue** festgelegt ist.
Die Fehlermeldung wird unterdrückt.

```powershell
# Change the ErrorActionPreference to 'SilentlyContinue'
$ErrorActionPreference = 'SilentlyContinue'
# Generate an error message
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
# Error message is suppressed and script continues processing
```

```Output
Hello World
```

In diesem Beispiel wird der `$ErrorActionPreference` zu **stoppende** Satz angezeigt. Außerdem wird das zusätzliche Objekt angezeigt, das für die Variable generiert wurde `$Error` .

```powershell
# Change the ErrorActionPreference to 'Stop'
$ErrorActionPreference = 'Stop'
# Error message is is generated and script stops processing
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'

# Show the ActionPreferenceStopException and the error generated
$Error[0]
$Error[1]
```

```Output
Write-Error -Message 'Test Error' ; Write-Host 'Hello World' : Test Error
At line:1 char:1
+ Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

The running command stopped because the preference variable "ErrorActionPreference"
or common parameter is set to Stop: Test Error

Write-Error -Message 'Test Error' ; Write-Host 'Hello World' : Test Error
At line:1 char:1
+ Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

### <a name="errorview"></a>\$Errorview

Bestimmt das Anzeige Format von Fehlermeldungen in PowerShell.

Die folgenden Werte sind gültig:

- **Normalview** : (Standard) eine ausführliche Ansicht, die für die meisten Benutzer konzipiert ist. Besteht aus einer Beschreibung des Fehlers und dem Namen des Objekts, das am Fehler beteiligt ist.
- **Categoryview** : eine prägnante, strukturierte Sicht, die für Produktionsumgebungen konzipiert ist. Das Format sieht folgendermaßen aus:

  {Category}: ({TargetName}: {TargetType}): [{Activity}], {Reason}

Weitere Informationen zu den Feldern in **categoryview** finden Sie unter [errorcategoryinfo](/dotnet/api/system.management.automation.errorcategoryinfo) -Klasse.

#### <a name="examples"></a>Beispiele

Dieses Beispiel zeigt, wie ein Fehler angezeigt wird, wenn der Wert von `$ErrorView` der Standardwert, **Normalansicht** ist. `Get-ChildItem` wird verwendet, um eine nicht vorhandene Datei zu suchen.

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

Dieses Beispiel zeigt, wie der gleiche Fehler angezeigt wird, wenn der Wert von `$ErrorView` in **categoryview** geändert wird.

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

In diesem Beispiel wird veranschaulicht, dass sich der Wert von `$ErrorView` nur auf die Fehleranzeige auswirkt. Die Struktur des Fehler Objekts, das in der automatischen Variablen gespeichert ist, wird nicht geändert `$Error` . Weitere Informationen über die `$Error` Automatische Variable finden Sie unter [about_automatic_variables](about_Automatic_Variables.md).

Der folgende Befehl übernimmt das **ErrorRecord** -Objekt, das dem letzten Fehler im Fehler Array, **Element 0** , zugeordnet ist, und formatiert alle Eigenschaften des Fehler Objekts in einer Liste.

```powershell
$Error[0] | Format-List -Property * -Force
```

```Output
PSMessageDetails      :
Exception             : System.Management.Automation.ItemNotFoundException:
                          Cannot find path 'C:\nofile.txt' because it does
                          not exist.
                        at System.Management.Automation.SessionStateInternal.
                          GetChildItems(String path, Boolean recurse, UInt32
                          depth, CmdletProviderContext context)
                        at System.Management.Automation.ChildItemCmdlet
                          ProviderIntrinsics.Get(String path, Boolean
                          recurse, UInt32 depth, CmdletProviderContext context)
                        at Microsoft.PowerShell.Commands.GetChildItemCommand.
                          ProcessRecord()
TargetObject          : C:\nofile.txt
CategoryInfo          : ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem],
                          ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,
                          Microsoft.PowerShell.Commands.GetChildItemCommand
ErrorDetails          :
InvocationInfo        : System.Management.Automation.InvocationInfo
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo : {0, 1}
```

### <a name="formatenumerationlimit"></a>\$Formatenumerationlimit

Bestimmt, wie viele aufgelistete Elemente in einer Anzeige enthalten sind. Diese Variable wirkt sich nicht auf die zugrunde liegenden Objekte aus, sondern nur auf die Anzeige. Wenn der Wert von `$FormatEnumerationLimit` kleiner als die Anzahl der aufgelisteten Elemente ist, fügt PowerShell ein Ellipsen () hinzu, `...` um anzuzeigen, dass Elemente nicht angezeigt werden.

**Gültige Werte** : ganze Zahlen ( `Int32` )

**Standardwert** : 4

#### <a name="examples"></a>Beispiele

Dieses Beispiel zeigt, wie die- `$FormatEnumerationLimit` Variable verwendet wird, um die Anzeige von enumerierten Elementen zu verbessern.

Der Befehl in diesem Beispiel generiert eine Tabelle, in der alle Dienste aufgelistet sind, die auf dem Computer in zwei Gruppen ausgeführt werden: eine für die **Ausführung** von Diensten und eine für **beendete Dienste.** Er verwendet einen `Get-Service` Befehl, um alle Dienste zu erhalten, und sendet dann die Ergebnisse über die Pipeline an das `Group-Object` Cmdlet, das die Ergebnisse nach dem Dienststatus gruppiert.

Das Ergebnis ist eine Tabelle, die den Status in der Spalte " **Name** " und die Prozesse in der Spalte " **Group** " auflistet. Um die Spalten Bezeichnungen zu ändern, verwenden Sie eine Hash Tabelle. Weitere Informationen finden Sie unter [about_Hash_Tables](about_Hash_Tables.md). Weitere Informationen finden Sie in den Beispielen in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).

Suchen Sie den aktuellen Wert von `$FormatEnumerationLimit` .

```powershell
$FormatEnumerationLimit
```

```Output
4
```

Auflisten aller Dienste nach **Status** gruppiert. In der **Gruppen** Spalte sind maximal vier Dienste für jeden Status aufgeführt, da den `$FormatEnumerationLimit` Wert **4** aufweist.

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

Erhöhen Sie den Wert von auf 1000, um die Anzahl der aufgelisteten Elemente zu erhöhen `$FormatEnumerationLimit` . **1000** Verwenden `Get-Service` `Group-Object` Sie und, um die Dienste anzuzeigen.

```powershell
$FormatEnumerationLimit = 1000
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec...
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc...
```

Verwenden `Format-Table` Sie mit dem **Wrap** -Parameter, um die Liste der Dienste anzuzeigen.

```powershell
Get-Service | Group-Object -Property Status | Format-Table -Wrap
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec,
                  Client for NFS, CryptSvc, DcomLaunch, Dhcp, dmserver,
                  Dnscache, ERSvc, Eventlog, EventSystem, FwcAgent, helpsvc,
                  HidServ, IISADMIN, InoRPC, InoRT, InoTask, lanmanserver,
                  lanmanworkstation, LmHosts, MDM, Netlogon, Netman, Nla,
                  NtLmSsp, PlugPlay, PolicyAgent, ProtectedStorage, RasMan,
                  RemoteRegistry, RpcSs, SamSs, Schedule, seclogon, SENS,
                  SharedAccess, ShellHWDetection, SMT PSVC, Spooler,
                  srservice, SSDPSRV, stisvc, TapiSrv, TermService, Themes,
                  TrkWks, UMWdf, W32Time, W3SVC, WebClient, winmgmt, wscsvc,
                  wuauserv, WZCSVC, zzInterix}

41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc,
                  ClipSrv, clr_optimization_v2.0.50727_32, COMSysApp,
                  CronService, dmadmin, FastUserSwitchingCompatibility,
                  HTTPFilter, ImapiService, Mapsvc, Messenger, mnmsrvc,
                  MSDTC, MSIServer, msvsmon80, NetDDE, NetDDEdsdm, NtmsSvc,
                  NVSvc, ose, RasAuto, RDSessMgr, RemoteAccess, RpcLocator,
                  SCardSvr, SwPrv, SysmonLog, TlntSvr, upnphost, UPS, VSS,
                  WmdmPmSN, Wmi, WmiApSrv, xmlprov}
```

### <a name="informationpreference"></a>\$"Informationpreference"

Mit der- `$InformationPreference` Variable können Sie Einstellungen für den Informationsstrom festlegen, die Benutzern angezeigt werden sollen. Insbesondere Informationsmeldungen, die Sie Befehlen oder Skripts hinzugefügt haben, indem Sie das Cmdlet " [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) " hinzufügen. Wenn der **informationaction** -Parameter verwendet wird, überschreibt der Wert den Wert der `$InformationPreference` Variablen. `Write-Information` wurde in PowerShell 5,0 eingeführt.

Die folgenden Werte sind gültig:

- **Beenden** : beendet einen Befehl oder ein Skript bei einem Vorkommen des `Write-Information` Befehls.
- **Erkundigen** : zeigt die Informations Meldung an, die Sie in einem `Write-Information` Befehl angeben, und fragt dann, ob Sie den Vorgang fortsetzen möchten.
- **Continue** : zeigt die Informations Meldung an und wird weiterhin ausgeführt.
- **Suspend** : hält einen Workflow Auftrag automatisch an, nachdem ein `Write-Information` Befehl ausgeführt wurde, damit Benutzer die Nachrichten anzeigen können, bevor Sie fortfahren. Der Workflow kann nach Ermessen des Benutzers fortgesetzt werden.
- **SilentlyContinue** : (Standard) keine Auswirkung. Die Informationsmeldungen werden nicht angezeigt, und das Skript wird ohne Unterbrechung fortgesetzt.

### <a name="logevent"></a>\$Log *-Ereignis

Die **Log *-Ereignis** Einstellungs Variablen bestimmen, welche Arten von Ereignissen in Ereignisanzeige in das PowerShell-Ereignisprotokoll geschrieben werden. Standardmäßig werden nur Engine-und Provider Ereignisse protokolliert. Sie können jedoch die **Log *-Ereignis** Einstellungs Variablen verwenden, um Ihr Protokoll anzupassen, z. b. Protokollieren von Ereignissen zu Befehlen.

Die **Ereignis Einstellungs Variablen Log *** lauten wie folgt:

- `$LogCommandHealthEvent`: Protokolliert Fehler und Ausnahmen bei der Initialisierung und Verarbeitung von Befehlen. Der Standardwert ist `$false` (nicht protokolliert).
- `$LogCommandLifecycleEvent`: Protokolliert das Starten und Beenden von Befehlen und Befehls Pipelines sowie Sicherheits Ausnahmen in der Befehls Ermittlung. Der Standardwert ist `$false` (nicht protokolliert).
- `$LogEngineHealthEvent`: Protokolliert Fehler und Fehler von Sitzungen. Der Standardwert ist `$true` (protokolliert).
- `$LogEngineLifecycleEvent`: Protokolliert das Öffnen und Schließen von Sitzungen. Der Standardwert ist `$true` (protokolliert).
- `$LogProviderHealthEvent`: Protokolliert Anbieter Fehler, wie z. b. Lese-und Schreibfehler, Such Fehler und Aufruf Fehler. Der Standardwert ist `$true` (protokolliert).
- `$LogProviderLifecycleEvent`: Protokolliert das Hinzufügen und Entfernen von PowerShell-Anbietern. Der Standardwert ist `$true` (protokolliert). Weitere Informationen zu PowerShell-Anbietern finden Sie unter [about_Providers](about_Providers.md).

Um ein **Log *-Ereignis** zu aktivieren, geben Sie die Variable mit dem Wert ein, z. b. `$true` :

```powershell
$LogCommandLifeCycleEvent = $true
```

Wenn Sie einen Ereignistyp deaktivieren möchten, geben Sie die Variable mit dem Wert ein, z. b. `$false` :

```powershell
$LogCommandLifeCycleEvent = $false
```

Die Ereignisse, die Sie aktivieren, gelten nur für die aktuelle PowerShell-Konsole. Wenn Sie die Konfiguration auf alle Konsolen anwenden möchten, speichern Sie die Variablen Einstellungen in Ihrem PowerShell-Profil. Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).

### <a name="maximumaliascount"></a>\$Maximubösascount

Bestimmt, wie viele Aliase in einer PowerShell-Sitzung zulässig sind. Der Standardwert ist **4096** und sollte für die meisten Verwendungen ausreichen. Sie können `$MaximumAliasCount` Ihren Anforderungen entsprechend anpassen.

**Gültige Werte** : 1024-32768 ( `Int32` )

**Standard** Wert: 4096

Geben Sie Folgendes ein, um die Aliase Ihres Systems zu zählen:

```powershell
(Get-Alias).count
```

### <a name="maximumdrivecount"></a>\$Maximumdrivecount

Bestimmt, wie viele PowerShell-Laufwerke in einer bestimmten Sitzung zulässig sind. Beispielsweise Dateisystem Laufwerke und Datenspeicher, die von PowerShell-Anbietern verfügbar gemacht werden und als Laufwerke angezeigt werden, `Alias:` z `HKLM:` . b. die Laufwerke und.

**Gültige Werte** : 1024-32768 ( `Int32` )

**Standard** Wert: 4096

Geben Sie Folgendes ein, um die Aliase Ihres Systems zu zählen:

```powershell
(Get-PSDrive).count
```

### <a name="maximumerrorcount"></a>\$MaximumErrorCount

Bestimmt, wie viele Fehler im Fehler Verlauf der Sitzung gespeichert werden.

**Gültige Werte** : 256-32768 ( `Int32` )

**Standard** Wert: 256

Objekte, die die einzelnen beibehaltenen Fehler darstellen, werden in der `$Error` automatischen Variablen gespeichert. `$Error` enthält ein Array von Fehler Daten Satz-Objekten. Der letzte Fehler ist das erste Objekt im Array `$Error[0]` .

Verwenden Sie die `$Error` **count** -Eigenschaft des Arrays, um die Fehler in Ihrem System zu zählen.

```powershell
$Error.count
```

Um einen bestimmten Fehler anzuzeigen, verwenden `[0]` Sie die Array Notation, um den letzten Fehler anzuzeigen.

```powershell
$Error[0]
```

Geben Sie Folgendes ein, um den ältesten beibehaltenen Fehler anzuzeigen:

```powershell
$Error[($Error.Count -1]
```

Der **Force** -Parameter überschreibt die spezielle Formatierung von **ErrorRecord** -Objekten und kehrt auf das herkömmliche Format zurück. Geben Sie den folgenden Befehl ein, um die Eigenschaften des **ErrorRecord** -Objekts anzuzeigen:

```powershell
$Error[0] | Format-List -Property * -Force
```

In diesem Beispiel `$Error.Count` zeigt die Anzahl der Fehler an. Um alle Fehler aus dem Fehler Verlauf zu löschen, verwenden Sie die- `Clear` Methode des Fehler Arrays.

```powershell
$Error.Count
```

```Output
17
```

```powershell
$Error.Clear()
$Error.Count
```

```Output
0
```

Wenn Sie alle Eigenschaften und Methoden eines Fehler Arrays suchen möchten, verwenden Sie das `Get-Member` Cmdlet mit dem **Inputobject** -Parameter. Wenn Sie den **Inputobject** -Parameter verwenden, werden `Get-Member` die Eigenschaften und Methoden der Auflistung angezeigt.

```powershell
Get-Member -InputObject $Error
```

Wenn Sie eine Auflistung von-Objekten an übergeben `Get-Member` , `Get-Member` zeigt die Eigenschaften und Methoden der Objekte in der Auflistung an.

```powershell
$Error | Get-Member
```

### <a name="maximumfunctioncount"></a>\$Maximumfunctioncount

Bestimmt, wie viele Funktionen in einer bestimmten Sitzung zulässig sind.

**Gültige Werte** : 1024-32768 ( `Int32` )

**Standard** Wert: 4096

Verwenden Sie das PowerShell- `Function:` Laufwerk, das vom PowerShell-Anbieter verfügbar gemacht wird, um die Funktionen in Ihrer Sitzung anzuzeigen `Function` . Weitere Informationen zum `Function` Anbieter [about_Function_Provider](about_Function_Provider.md).

Um die Funktionen in der aktuellen Sitzung aufzulisten, geben Sie Folgendes ein:

```powershell
Get-ChildItem Function:
```

Geben Sie Folgendes ein, um die Funktionen in der aktuellen Sitzung zu zählen:

```powershell
(Get-ChildItem Function:).Count
```

### <a name="maximumhistorycount"></a>\$MaximumHistoryCount

Bestimmt, wie viele Befehle im Befehlsverlauf für die aktuelle Sitzung gespeichert werden.

**Gültige Werte** : 1-32768 ( `Int32` )

**Standard** Wert: 4096

Geben Sie Folgendes ein, um die Anzahl der Befehle zu ermitteln, die aktuell im Befehlsverlauf gespeichert sind:

```powershell
(Get-History).Count
```

Verwenden Sie das-Cmdlet, um die im Sitzungsverlauf gespeicherten Befehle anzuzeigen `Get-History` . Weitere Informationen finden Sie unter [about_History](about_History.md).

### <a name="maximumvariablecount"></a>\$MaximumVariableCount

Bestimmt, wie viele Variablen in einer bestimmten Sitzung zulässig sind, einschließlich automatischer Variablen, Einstellungs Variablen und der Variablen, die Sie in Befehlen und Skripts erstellen.

**Gültige Werte** : 1024-32768 ( `Int32` )

**Standard** Wert: 4096

Verwenden Sie das `Get-Variable` Cmdlet und die Features des PowerShell `Variable:` -Laufwerks und des PowerShell-Anbieters, um die Variablen in der Sitzung anzuzeigen `Variable` . Weitere Informationen finden Sie unter [about_Variable_Provider](about_Variable_Provider.md).

Um die aktuelle Anzahl der Variablen im System zu ermitteln, geben Sie Folgendes ein:

```powershell
(Get-Variable).Count
```

### <a name="ofs"></a>\$OFS

Das Ausgabefeld Trennzeichen (OFS) gibt das Zeichen an, das die Elemente eines Arrays trennt, das in eine Zeichenfolge konvertiert wird.

**Gültige Werte** : eine beliebige Zeichenfolge.

**Standard** Wert: Leerzeichen

Standardmäßig ist die `$OFS` Variable nicht vorhanden, und das Ausgabedatei Trennzeichen ist ein Leerzeichen, Sie können diese Variable jedoch hinzufügen und auf eine beliebige Zeichenfolge festlegen. Sie können den Wert von `$OFS` in Ihrer Sitzung ändern, indem Sie eingeben `$OFS="<value>"` .

> [!NOTE]
> Wenn Sie den Standardwert eines leer Zeichens ( `" "` ) in ihrer Skript-, Modul-oder Konfigurations Ausgabe erwarten, achten Sie darauf, dass der `$OFS` Standardwert an anderer Stelle im Code nicht geändert wurde.

#### <a name="examples"></a>Beispiele

Dieses Beispiel zeigt, dass ein Leerzeichen verwendet wird, um die Werte zu trennen, wenn ein Array in eine Zeichenfolge konvertiert wird. In diesem Fall wird ein Array aus ganzen Zahlen in einer Variablen gespeichert, und dann wird die Variable in eine Zeichenfolge umgewandelt.

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

Um das Trennzeichen zu ändern, fügen Sie die Variable hinzu, `$OFS` indem Sie Ihr einen Wert zuweisen.
Die Variable muss den Namen haben `$OFS` .

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

Um das Standardverhalten wiederherzustellen, können Sie dem Wert von ein Leerzeichen ( `" "` ) zuweisen `$OFS` oder die Variable löschen. Mit den folgenden Befehlen wird die-Variable gelöscht und dann überprüft, ob das Trennzeichen ein Leerzeichen ist.

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a>\$OutputEncoding

Bestimmt die Zeichen Codierungsmethode, die PowerShell beim Senden von Text an andere Anwendungen verwendet.

Wenn eine Anwendung z. b. Unicode-Zeichen folgen an PowerShell zurückgibt, müssen Sie den Wert möglicherweise in **UnicodeEncoding** ändern, um die Zeichen ordnungsgemäß zu senden.

Die gültigen Werte lauten wie folgt: Objekte, die von einer Codierungs Klasse abgeleitet werden, z. b. **ASCIIEncoding** , **sbcscodepageencoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** und **UnicodeEncoding**.

**Standard** : ASCIIEncoding-Objekt (System. Text. ASCIIEncoding)

#### <a name="examples"></a>Beispiele

In diesem Beispiel wird gezeigt, wie der Windows **findstr.exe** -Befehl in PowerShell auf einem Computer ausgeführt wird, der für eine Sprache lokalisiert wird, die Unicode-Zeichen verwendet, z. b. Chinesisch.

Der erste Befehl sucht den Wert von `$OutputEncoding` . Da der Wert ein Codierungs Objekt ist, zeigen Sie nur seine **EncodingName** -Eigenschaft an.

```powershell
$OutputEncoding.EncodingName
```

In diesem Beispiel wird ein **findstr.exe** Befehl verwendet, um nach zwei chinesischen Zeichen zu suchen, die in der `Test.txt` Datei vorhanden sind. Wenn dieser **findstr.exe** Befehl in der Windows-Eingabeaufforderung ( **cmd.exe** ) ausgeführt wird, sucht **findstr.exe** die Zeichen in der Textdatei. Wenn Sie jedoch denselben **findstr.exe** Befehl in PowerShell ausführen, werden die Zeichen nicht gefunden, da Sie von PowerShell an **findstr.exe** im ASCII-Text gesendet werden und nicht in Unicode-Text.

```powershell
findstr <Unicode-characters>
```

Damit der Befehl in PowerShell funktioniert, legen Sie den Wert von `$OutputEncoding` auf den Wert der **OutputEncoding** -Eigenschaft der Konsole fest, die auf dem für Windows ausgewählten Gebiets Schema basiert. Da **OutputEncoding** eine statische Eigenschaft der-Konsole ist, verwenden Sie doppelte Doppelpunkte ( `::` ) im-Befehl.

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

Nach der Änderung der Codierung findet der **findstr.exe** -Befehl die Unicode-Zeichen.

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a>\$ProgressPreference

Bestimmt, wie PowerShell auf Statusaktualisierungen antwortet, die von einem Skript, Cmdlet oder Anbieter generiert werden, z. b. die vom Cmdlet " [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) " generierten Status leisten.
Mit dem `Write-Progress` -Cmdlet werden Status leisten erstellt, in denen der Status eines Befehls angezeigt wird.

Die folgenden Werte sind gültig:

- **Abbrechen** : zeigt die Statusanzeige nicht an. Stattdessen wird eine Fehlermeldung angezeigt, und die Ausführung wird beendet.
- **Erkundigen** : die Statusanzeige wird nicht angezeigt. Fordert die Berechtigung zum Fortfahren an. Wenn Sie mit `Y` oder Antworten `A` , wird die Statusanzeige angezeigt.
- **Continue** (Standard): zeigt die Statusanzeige an und setzt die Ausführung fort.
- **SilentlyContinue** : führt den Befehl aus, zeigt jedoch nicht die Statusanzeige an.

### <a name="psemailserver"></a>\$Psemailserver "

Gibt den Standard-e-Mail-Server an, der zum Senden von e-Mails verwendet wird. Diese Einstellungs Variable wird von Cmdlets verwendet, die eine e-Mail senden, z. b. das Cmdlet " [Send-Mail Message](xref:Microsoft.PowerShell.Utility.Send-MailMessage) ".

### <a name="psdefaultparametervalues"></a>\$PSDefaultParameterValues

Gibt die Standardwerte für die Parameter von Cmdlets und erweiterten Funktionen an.
Der Wert von `$PSDefaultParameterValues` ist eine Hash Tabelle, in der der Schlüssel aus dem Cmdlet-Namen und dem Parameternamen besteht, die durch einen Doppelpunkt () getrennt sind `:` . Der Wert ist ein benutzerdefinierter Standardwert, den Sie angeben.

`$PSDefaultParameterValues` wurde in PowerShell 3,0 eingeführt.

Weitere Informationen zu dieser Einstellungs Variablen finden Sie unter [about_Parameters_Default_Values](about_Parameters_Default_Values.md).

### <a name="psmoduleautoloadingpreference"></a>\$PSModuleAutoloadingPreference

Aktiviert und deaktiviert das automatische Importieren von Modulen in der Sitzung. Der Standardwert ist " **all** ". Unabhängig vom Wert der Variablen können Sie [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) verwenden, um ein Modul zu importieren.

Gültige Werte sind:

- **All** : Module werden bei der ersten Verwendung automatisch importiert. Um ein Modul zu importieren, können Sie einen beliebigen Befehl im Modul erhalten oder verwenden. Verwenden Sie z. B. `Get-Command`.
- **Modulequalified** : Module werden nur dann automatisch importiert, wenn ein Benutzer das Modul qualifizierte Name eines Befehls im Modul verwendet. Wenn der Benutzer z. b. eingibt `MyModule\MyCommand` , importiert PowerShell das **MyModule** -Modul.
- **Keine** : der automatische Import von Modulen ist in der Sitzung deaktiviert. Verwenden Sie das-Cmdlet, um ein Modul zu importieren `Import-Module` .

Weitere Informationen zum automatischen Importieren von Modulen finden Sie unter [about_Modules](about_Modules.md).

### <a name="pssessionapplicationname"></a>\$PSSessionApplicationName

Gibt den Standard Anwendungsnamen für einen Remote Befehl an, der die Web Services for Management (WS-Management)-Technologie verwendet. Weitere Informationen finden Sie unter Informationen [zu Windows-Remoteverwaltung](/windows/win32/winrm/about-windows-remote-management).

Der Standard Anwendungsname des Systems ist `WSMAN` , aber Sie können diese Einstellungs Variable verwenden, um den Standardwert zu ändern.

Der Anwendungsname ist der letzte Knoten in einem Verbindungs-URI. Der Anwendungsname im folgenden Beispiel-URI lautet z. b `WSMAN` ..

`http://Server01:8080/WSMAN`

Der Standard Anwendungsname wird verwendet, wenn der Remote Befehl keinen Verbindungs-URI oder Anwendungsnamen angibt.

Der **WinRM** -Dienst wählt mit dem Anwendungsnamen einen Listener für die Verbindungsanforderung aus. Der Wert des Parameters sollte mit dem Wert der **URLPrefix** -Eigenschaft eines Listener auf dem Remote Computer identisch sein.

Verwenden Sie die Parameter **ConnectionUri** oder **ApplicationName** der Cmdlets [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)oder [aufrufen-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) , um die System Standardwerte und den Wert dieser Variablen zu überschreiben und einen anderen Anwendungsnamen für eine bestimmte Sitzung auszuwählen.

Die Einstellungs `$PSSessionApplicationName` Variable wird auf dem lokalen Computer festgelegt, aber Sie gibt einen Listener auf dem Remote Computer an. Wenn der angegebene Anwendungsname auf dem Remote Computer nicht vorhanden ist, schlägt der Befehl zum Einrichten der Sitzung fehl.

### <a name="pssessionconfigurationname"></a>\$PSSessionConfigurationName

Gibt die Standard Sitzungs Konfiguration an, die für die in der aktuellen Sitzung erstellten **pssessions** verwendet wird.

Diese Einstellungs Variable wird auf dem lokalen Computer festgelegt, aber Sie gibt eine Sitzungs Konfiguration an, die sich auf dem Remote Computer befindet.

Der Wert der `$PSSessionConfigurationName` Variablen ist ein voll qualifizierter Ressourcen-URI.

Der Standardwert `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` gibt die **Microsoft. PowerShell** -Sitzungs Konfiguration auf dem Remote Computer an.

Wenn Sie nur einen Konfigurations Namen angeben, wird der folgende Schema-URI vorangestellt:

`http://schemas.microsoft.com/PowerShell/`

Sie können den Standardwert überschreiben und eine andere Sitzungs Konfiguration für eine bestimmte Sitzung auswählen, indem Sie den **ConfigurationName** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder verwenden.

Sie können den Wert dieser Variablen jederzeit ändern. Beachten Sie dabei, dass die ausgewählte Sitzungs Konfiguration auf dem Remote Computer vorhanden sein muss. Wenn dies nicht der Fall ist, schlägt der Befehl zum Erstellen einer Sitzung fehl, die die Sitzungs Konfiguration verwendet.

Diese Einstellungs Variable bestimmt nicht, welche lokalen Sitzungs Konfigurationen verwendet werden, wenn Remote Benutzer eine Sitzung erstellen, die eine Verbindung mit diesem Computer herstellt.
Sie können jedoch die Berechtigungen für die lokalen Sitzungs Konfigurationen verwenden, um zu bestimmen, welche Benutzer Sie verwenden dürfen.

### <a name="pssessionoption"></a>\$PSSessionOption

Legt die Standardwerte für erweiterte Benutzeroptionen in einer Remote Sitzung fest.
Diese Options Einstellungen überschreiben die System Standardwerte für Sitzungs Optionen.

Die `$PSSessionOption` Variable enthält ein **pssessionoption** -Objekt. Weitere Informationen finden Sie unter " [System. Management. Automation. Remoting. pssessionoption](/dotnet/api/system.management.automation.remoting.pssessionoption)".
Jede Eigenschaft des-Objekts stellt eine Sitzungs Option dar. Beispielsweise wandelt die **NoCompression** -Eigenschaft die Datenkomprimierung während der Sitzung um.

Standardmäßig enthält die `$PSSessionOption` Variable ein **pssessionoption** -Objekt mit den Standardwerten für alle Optionen, wie unten gezeigt.

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
IncludePortInSPN                  : False
OutputBufferingMode               : None
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : -00:00:00.0010000
```

Beschreibungen dieser Optionen und weitere Informationen finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption). Weitere Informationen zu Remote Befehlen und-Sitzungen finden Sie unter [about_Remote](about_Remote.md) und [about_PSSessions](about_PSSessions.md).

Um den Wert der Preference- `$PSSessionOption` Variablen zu ändern, verwenden `New-PSSessionOption` Sie das Cmdlet zum Erstellen eines **pssessionoption** -Objekts mit den von Ihnen bevorzugten Options Werten. Speichern Sie die Ausgabe in einer Variablen mit dem Namen `$PSSessionOption` .

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

Wenn Sie die Einstellungs `$PSSessionOption` Variable in jeder PowerShell-Sitzung verwenden möchten, fügen Sie einen `New-PSSessionOption` Befehl hinzu, mit dem die Variable in `$PSSessionOption` Ihrem PowerShell-Profil erstellt wird. Weitere Informationen finden Sie unter [about_Profiles](about_Profiles.md).

Sie können benutzerdefinierte Optionen für eine bestimmte Remote Sitzung festlegen. Die von Ihnen festgelegten Optionen haben Vorrang vor den System Standardwerten und dem Wert der `$PSSessionOption` Preference-Variablen.

Verwenden Sie das `New-PSSessionOption` Cmdlet zum Erstellen eines **pssessionoption** -Objekts, um benutzerdefinierte Sitzungs Optionen festzulegen. Verwenden Sie dann das **pssessionoption** -Objekt als Wert des **sessionoption** -Parameters in Cmdlets, die eine Sitzung erstellen, `New-PSSession` z `Enter-PSSession` . b `Invoke-Command` ., und.

### <a name="transcript"></a>$Transcript

Wird von verwendet `Start-Transcript` , um den Namen und den Speicherort der Transkriptions Datei anzugeben. Wenn Sie keinen Wert für den **path** -Parameter angeben, wird `Start-Transcript` von der Pfad im Wert der `$Transcript` globalen Variablen verwendet. Wenn Sie diese Variable nicht erstellt haben, `Start-Transcript` speichert die Transkriptionen `$Home\My Documents` als Dateien im Verzeichnis `\PowerShell_transcript.<time-stamp>.txt` .

### <a name="verbosepreference"></a>\$VerbosePreference

Bestimmt, wie PowerShell auf ausführliche Meldungen antwortet, die von einem Skript, einem Cmdlet oder einem Anbieter generiert werden, z. b. die vom [Write-ausführliche-](xref:Microsoft.PowerShell.Utility.Write-Verbose) Cmdlet generierten Meldungen.
Ausführliche Meldungen beschreiben die Aktionen, die zum Ausführen eines Befehls ausgeführt werden.

Standardmäßig werden ausführliche Meldungen nicht angezeigt. Sie können dieses Verhalten jedoch ändern, indem Sie den Wert von ändern `$VerbosePreference` .

Sie können den allgemeinen **ausführliche** -Parameter eines Cmdlets verwenden, um die ausführlichen Meldungen für einen bestimmten Befehl anzuzeigen oder auszublenden. Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).

Die folgenden Werte sind gültig:

- **Beenden** : zeigt die ausführliche Meldung und eine Fehlermeldung an und beendet dann die Ausführung.
- **Anfragen** : zeigt die ausführliche Meldung an und zeigt dann eine Eingabeaufforderung an, in der Sie gefragt werden, ob Sie den Vorgang fortsetzen möchten.
- **Continue** : zeigt die ausführliche Meldung an und wird dann mit der Ausführung fortgesetzt.
- **SilentlyContinue** : (Standard) zeigt die ausführliche Meldung nicht an. Setzt die Ausführung fort.

#### <a name="examples"></a>Beispiele

Diese Beispiele zeigen die Auswirkung der unterschiedlichen Werte von `$VerbosePreference` und des **verbose** -Parameters, um den Preference-Wert zu überschreiben.

Dieses Beispiel zeigt die Auswirkung des **SilentlyContinue** -Werts, der Standardwert ist. Der Befehl verwendet den **Message** -Parameter, schreibt jedoch keine Nachricht in die PowerShell-Konsole.

```powershell
Write-Verbose -Message "Verbose message test."
```

Wenn der **verbose** -Parameter verwendet wird, wird die Nachricht geschrieben.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

Dieses Beispiel zeigt die Auswirkung des **Continue** -Werts. Die `$VerbosePreference` Variable wird auf **Continue** festgelegt, und die Meldung wird angezeigt.

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet `$false` , der den **Continue** -Wert überschreibt. Die Meldung wird nicht angezeigt.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

Dieses Beispiel zeigt die Auswirkung des **Stoppwerts** . Die `$VerbosePreference` Variable wird auf "wird **beendet** " festgelegt, und die Meldung wird angezeigt. Der Befehl wurde beendet.

```powershell
$VerbosePreference = "Stop"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
Write-Verbose : The running command stopped because the preference variable
  "VerbosePreference" or common parameter is set to Stop: Verbose message test.
At line:1 char:1
+ Write-Verbose -Message "Verbose message test."
```

In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet `$false` , der den **Endwert** überschreibt. Die Meldung wird nicht angezeigt.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

Dieses Beispiel **zeigt die Auswirkung des Werts "** suchen". Die `$VerbosePreference` Variable wird auf " **Anfragen** " festgelegt. Die Meldung wird angezeigt, und der Benutzer wird zur Bestätigung aufgefordert.

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

In diesem Beispiel wird der **verbose** -Parameter mit dem Wert verwendet, der den Wert "suchen" `$false` überschreibt. **Inquire** Der Benutzer wird nicht zur Eingabe aufgefordert, und die Meldung wird nicht angezeigt.

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a>\$WarningPreference

Bestimmt, wie PowerShell auf Warnmeldungen antwortet, die von einem Skript, einem Cmdlet oder einem Anbieter generiert werden, z. b. die vom Cmdlet " [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) " generierten Meldungen.

Standardmäßig werden Warnmeldungen angezeigt, und die Ausführung wird fortgesetzt. Sie können dieses Verhalten jedoch ändern, indem Sie den Wert von ändern `$WarningPreference` .

Sie können den allgemeinen **WarningAction** -Parameter eines Cmdlets verwenden, um zu bestimmen, wie PowerShell auf Warnungen von einem bestimmten Befehl antwortet. Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).

Die folgenden Werte sind gültig:

- **Beenden** : zeigt die Warnmeldung und eine Fehlermeldung an und beendet dann die Ausführung.
- **Erkundigen** : zeigt die Warnmeldung an und fordert dann die Berechtigung zum Fortfahren auf.
- **Continue** (Standard): zeigt die Warnmeldung an und setzt dann die Ausführung fort.
- **SilentlyContinue** : zeigt die Warnmeldung nicht an. Setzt die Ausführung fort.

#### <a name="examples"></a>Beispiele

Diese Beispiele zeigen die Auswirkung der verschiedenen Werte von `$WarningPreference` .
Der **WarningAction** -Parameter überschreibt den Preference-Wert.

Dieses Beispiel zeigt die Auswirkung des Standardwerts " **Continue** ".

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

In diesem Beispiel wird der **WarningAction** -Parameter mit dem Wert **SilentlyContinue** verwendet, um die Warnung zu unterdrücken. Die Meldung wird nicht angezeigt.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

In diesem Beispiel wird die- `$WarningPreference` Variable in den **SilentlyContinue** -Wert geändert. Die Meldung wird nicht angezeigt.

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

In diesem Beispiel wird der **WarningAction** -Parameter verwendet, um zu beenden, wenn eine Warnung generiert wird.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Stop
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m -WarningAction Stop
```

In diesem Beispiel wird die- `$WarningPreference` Variable **Inquire** in den Wert "suchen" geändert. Der Benutzer wird zur Bestätigung aufgefordert.

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

In diesem Beispiel wird der **WarningAction** -Parameter mit dem Wert **SilentlyContinue** verwendet. Der Befehl wird weiter ausgeführt, und es wird keine Meldung angezeigt.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

In diesem Beispiel wird der `$WarningPreference` Wert in " **beendet** " geändert.

```powershell
$WarningPreference = "Stop"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m
```

In diesem Beispiel wird die **WarningAction** mit **dem Wert "** suchen" verwendet. Der Benutzer wird aufgefordert, wenn eine Warnung auftritt.

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend
[?] Help (default is "Y"):
```

### <a name="whatifpreference"></a>\$Variablen whatifpreference

Bestimmt, ob **WhatIf** für jeden Befehl, der ihn unterstützt, automatisch aktiviert wird. Wenn **WhatIf** aktiviert ist, meldet das Cmdlet die erwartete Auswirkung des Befehls, aber führt den Befehl nicht aus.

Die folgenden Werte sind gültig:

- **False** ( **0** , nicht aktiviert): (Standard) **WhatIf** ist nicht automatisch aktiviert. Um es manuell zu aktivieren, verwenden Sie den **WhatIf** -Parameter des Cmdlets.
- **True** ( **1** , aktiviert): **WhatIf** wird automatisch für jeden Befehl aktiviert, der den Befehl unterstützt. Benutzer können den **WhatIf** -Parameter mit dem Wert " **false** " verwenden, um ihn manuell zu deaktivieren, z `-WhatIf:$false` . b..

#### <a name="examples"></a>Beispiele

Diese Beispiele zeigen die Auswirkung der verschiedenen Werte von `$WhatIfPreference` .
Sie zeigen, wie der **WhatIf** -Parameter verwendet wird, um den Einstellungs Wert für einen bestimmten Befehl zu überschreiben.

Dieses Beispiel zeigt die Auswirkung der `$WhatIfPreference` Variablen auf den Standardwert **false**. `Get-ChildItem`Überprüfen Sie mithilfe von, ob die Datei vorhanden ist.
`Remove-Item` Löscht die Datei. Nachdem die Datei gelöscht wurde, können Sie den Löschvorgang mit überprüfen `Get-ChildItem` .

```powershell
Get-ChildItem -Path .\test.txt
Remove-Item -Path ./test.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           9/13/2019    10:53             10 test.txt
```

```powershell
Get-ChildItem -Path .\test.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -File test.txt
```

Dieses Beispiel zeigt die Auswirkung der Verwendung des **WhatIf** -Parameters, wenn der Wert von `$WhatIfPreference` **false** ist.

Überprüfen Sie, ob die Datei vorhanden ist.

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

Verwenden Sie den **WhatIf** -Parameter, um das Ergebnis des Löschens der Datei zu bestimmen.

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

Vergewissern Sie sich, dass die Datei nicht gelöscht wurde.

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

In diesem Beispiel wird gezeigt, wie die `$WhatIfPreference` Variable auf den Wert **true** festgelegt ist. Wenn Sie `Remove-Item` zum Löschen einer Datei verwenden, wird der Pfad der Datei angezeigt, aber die Datei wird nicht gelöscht.

Es wurde versucht, eine Datei zu löschen. Es wird eine Meldung darüber angezeigt, was passieren würde `Remove-Item` , wenn ausgeführt würde, aber die Datei nicht gelöscht wird.

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

Verwenden `Get-ChildItem` Sie, um zu überprüfen, ob die Datei gelöscht wurde.

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

Dieses Beispiel zeigt, wie eine Datei gelöscht wird, wenn der Wert von `$WhatIfPreference` **true** ist. Er verwendet den **WhatIf** -Parameter mit dem Wert `$false` . Verwenden `Get-ChildItem` Sie zum Überprüfen, ob die Datei gelöscht wurde.

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

Im folgenden finden Sie Beispiele für das `Get-Process` Cmdlet, das **WhatIf** nicht unterstützt, und `Stop-Process` das **WhatIf** unterstützt. Der `$WhatIfPreference` Wert der Variablen ist " **true** ".

`Get-Process` unterstützt **WhatIf** nicht. Wenn der Befehl ausgeführt wird, wird der **Winword** -Prozess angezeigt.

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

`Stop-Process` unterstützt **WhatIf**. Der **Winword** -Prozess wurde nicht beendet.

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

Sie können das `Stop-Process` **WhatIf** -Verhalten überschreiben, indem Sie den **WhatIf** -Parameter mit einem Wert von verwenden `$false` . Der **Winword** -Prozess wird beendet.

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

Verwenden Sie, um zu überprüfen, ob der **Winword** -Prozess beendet wurde `Get-Process` .

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a>Weitere Informationen:

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_CommonParameters](about_CommonParameters.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Profiles](about_Profiles.md)

[about_Remote](about_Remote.md)

[about_Scopes](about_Scopes.md)

[about_Variables](about_Variables.md)
