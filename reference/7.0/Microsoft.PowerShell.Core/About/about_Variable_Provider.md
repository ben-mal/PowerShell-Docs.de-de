---
description: Variable
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variable_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Variablenanbieter
ms.openlocfilehash: cae9a100b9e0a8fd044ec87d1541e1fe2bf440c8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222396"
---
# <a name="variable-provider"></a>Variablen Anbieter

## <a name="provider-name"></a>Anbietername
Variable

## <a name="drives"></a>Laufwerke

`Variable:`

## <a name="capabilities"></a>Funktionen

**ShouldProcess**

## <a name="short-description"></a>Kurze Beschreibung

Ermöglicht den Zugriff auf die PowerShell-Variablen und ihre Werte.

## <a name="detailed-description"></a>Detaillierte Beschreibung

Mit dem PowerShell- **Variablen** Anbieter können Sie PowerShell-Variablen in der aktuellen Konsole erhalten, hinzufügen, ändern, löschen und löschen.

Der PowerShell- **Variablen** Anbieter unterstützt die Variablen, die PowerShell erstellt, einschließlich der automatischen Variablen, der Einstellungs Variablen und der Variablen, die Sie erstellen.

Das **Variable** Laufwerk ist ein flacher Namespace, der nur die Variablen Objekte enthält. Die Variablen haben keine untergeordneten Elemente.

Der **Variablen** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

PowerShell enthält auch eine Reihe von Cmdlets, die speziell zum Anzeigen und Ändern von Variablen entworfen wurden. Wenn Sie **Variablen** -Cmdlets verwenden, müssen Sie nicht das `Variable:` Laufwerk im Namen angeben. In diesem Artikel wird das Arbeiten mit **Variablen** -Cmdlets nicht behandelt.

- [Get-Variable](xref:Microsoft.PowerShell.Utility.Get-Variable)
- [New-Variable](xref:Microsoft.PowerShell.Utility.New-Variable)
- [Set-Variable](xref:Microsoft.PowerShell.Utility.Set-Variable)
- [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable)
- [Clear-Variable](xref:Microsoft.PowerShell.Utility.Clear-Variable)

> [!NOTE]
> Sie können auch den PowerShell-Ausdrucks Parser verwenden, um die Werte von Variablen zu erstellen, anzuzeigen und zu ändern, ohne die-Cmdlets zu verwenden. Verwenden Sie beim direkten Arbeiten mit Variablen ein Dollarzeichen ( `$` ), um den Namen als Variable zu identifizieren, und den Zuweisungs Operator ( `=` ), um den Wert festzulegen und zu ändern. Beispielsweise `$p = Get-Process` erstellt die `p` Variable und speichert die Ergebnisse eines `Get-Process` Befehls darin.

## <a name="types-exposed-by-this-provider"></a>Von diesem Anbieter verfügbar gemachte Typen

Variablen können einen von mehreren unterschiedlichen Typen aufweisen. Die meisten Variablen sind Instanzen der- `PSVariable` Klasse. Weitere Variablen und deren Typen sind unten aufgeführt.

- Die- `?` Variable ist eine Instanz der- `QuestionMarkVariable` Klasse.
- Die- `null` Variable ist eine Instanz der- `NullVariable` Klasse.
- Die Variablen für die maximale Anzahl sind Instanzen der- `SessionStateCapacityVariable` Klasse.
- `LocalVariable` -Instanzen enthalten Informationen zur aktuellen Ausführung, wie z. b.:
  - `MyInvocation`
  - `PSCommandPath`
  - `PSScriptRoot`
  - `PSBoundParameters`
  - `args`
  - `input`

## <a name="navigating-the-variable-drives"></a>Navigieren in den Variablen Laufwerken

Der **Variablen** Anbieter macht seinen Datenspeicher im `Variable:` Laufwerk verfügbar. Wenn Sie mit Variablen arbeiten möchten, können Sie den Speicherort in das `Variable:` Laufwerk ( `Set-Location Variable:` ) ändern, oder Sie können von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten. Um auf eine Variable von einem anderen Speicherort zu verweisen, verwenden Sie den Laufwerk Namen ( `Variable:` ) im Pfad.

```powershell
Set-Location Variable:
```

Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein. Beispiel:

```powershell
Set-Location C:
```

Sie können auch mit dem **Variablen** Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten. Um auf eine Variable von einem anderen Speicherort zu verweisen, verwenden Sie den Namen des Laufwerks `Variable:` im Pfad.

> [!NOTE]
> PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten. Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="displaying-the-value-of-variables"></a>Anzeigen des Werts von Variablen

### <a name="get-all-variables-in-the-current-session"></a>Alle Variablen in der aktuellen Sitzung erhalten

Dieser Befehl ruft die Liste aller Variablen und ihre Werte in der aktuellen Sitzung ab. Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.

```powershell
Get-ChildItem -Path Variable:
```

### <a name="get-a-variable-using-its-provider-path"></a>Eine Variable mithilfe Ihres Anbieter Pfads erhalten

Dieser Befehl ruft einen variablen Wert mithilfe seines Anbieter Pfads ab, dem das Dollarzeichen () vorangestellt ist `$` . Dies hat dieselbe Auswirkung wie das präfixsignal des Variablen namens mit dem Dollarzeichen ( `$` ).

```powershell
$variable:home
```

### <a name="get-variables-using-wildcards"></a>Variablen mithilfe von Platzhaltern erhalten

Dieser Befehl ruft die Variablen ab, deren Namen mit "max" beginnen. Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.

```powershell
Get-ChildItem -Path Variable:max*
```

### <a name="get-the-value-of-the--variable"></a>Den Wert von erhalten? Variable

Dieser Befehl verwendet den `-LiteralPath` -Parameter von [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) , um den Wert der `?` Variablen innerhalb des `Variable:` Laufwerks abzurufen. Der `?` ist ein Platzhalter in Pfaden, `Get-ChildItem` versucht jedoch nicht, Platzhalter in den Werten des- `-LiteralPath` Parameters aufzulösen.

```powershell
Get-ChildItem -Literalpath ?
```

### <a name="get-readonly-and-constant-variables"></a>"Schreibgeschützte" und "Konstante" Variablen

Dieser Befehl ruft die Variablen ab, die die Werte von `ReadOnly` oder `Constant` für die **options** -Eigenschaft aufweisen.

```powershell
Get-ChildItem -Path Variable: | Where-Object {
   $_.options -Match "Constant" `
   -or $_.options -Match "ReadOnly"
 } | Format-List -Property name, value, options
```

## <a name="creating-variables"></a>Erstellen von Variablen

### <a name="create-a-new-variable"></a>Neue Variable erstellen

Dieser Befehl erstellt die `services` Variable und speichert die Ergebnisse eines `Get-Service` Befehls darin. Da sich die aktuelle Position im `Variable:` Laufwerk befindet, ist der Wert des- `-Path` Parameters ein Punkt ( `.` ), der die aktuelle Position darstellt.

Durch die Klammern um den `Get-Service` Befehl wird sichergestellt, dass der Befehl ausgeführt wird, bevor die Variable erstellt wird. Ohne die Klammern wäre der Wert der neuen Variablen die Zeichenfolge "Get-Service".

```powershell
New-Item -Path . -Name services -Value (Get-Service)
```

### <a name="create-a-variable-using-an-absolute-path"></a>Erstellen einer Variablen mit einem absoluten Pfad

Dieser Befehl erstellt eine `services` Variable und speichert das Ergebnis eines `Get-Service` Befehls darin.

```powershell
New-Item -Path Variable:services -Value Get-Service
```

 Um eine Variable ohne einen Wert zu erstellen, lassen Sie den Zuweisungsoperator aus.

## <a name="changing-variables"></a>Ändern von Variablen

### <a name="rename-a-variable"></a>Umbenennen einer Variablen

Dieser Befehl verwendet das `Rename-Item` Cmdlet, um den Namen der `a` Variablen in zu ändern `processes` .

```powershell
Rename-Item -Path Variable:a -NewName processes
```

### <a name="change-the-value-of-a-variable"></a>Ändern des Werts einer Variablen

Dieser Befehl verwendet das `Set-Item` Cmdlet, um den Wert der `ErrorActionPreference` Variablen in "wird beendet" zu ändern.

```powershell
Set-Item -Path Variable:ErrorActionPreference -Value Stop
```

## <a name="copy-a-variable"></a>Kopieren einer Variablen

Dieser Befehl verwendet das `Copy-Item` Cmdlet, um die `processes` Variable in zu kopieren `old_processes` . Dadurch wird eine neue Variable mit `old_processes` dem Namen erstellt, die über denselben Wert wie die `processes` Variable verfügt.

```powershell
Copy-Item -Path Variable:processes -Destination Variable:old_processes
```

## <a name="delete-a-variable"></a>Löschen einer Variable

Dieser Befehl löscht die `serv` Variable aus der aktuellen Sitzung. Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.

```powershell
Remove-Variable -Path Variable:serv
```

### <a name="delete-variables-using-the--force-parameter"></a>Löschen von Variablen mithilfe des Parameters "-Force"

Dieser Befehl löscht alle Variablen aus der aktuellen Sitzung mit Ausnahme der Variablen, deren **options** -Eigenschaft den Wert hat `Constant` . Ohne den- `-Force` Parameter löscht der Befehl keine Variablen, deren **options** -Eigenschaft den Wert hat `ReadOnly` .

```powershell
Remove-Item Variable:* -Force
```

## <a name="setting-the-value-of-a-variable-to-null"></a>Festlegen des Werts einer Variablen auf NULL

Dieser Befehl verwendet das `Clear-Item` Cmdlet, um den Wert der `processes` Variablen in NULL zu ändern.

```powershell
Clear-Item -Path Variable:processes
```

## <a name="using-the-pipeline"></a>Verwenden der Pipeline

Anbieter-Cmdlets akzeptieren Pipeline Eingaben. Sie können die Pipeline verwenden, um die Aufgabe zu vereinfachen, indem Sie Anbieter Daten von einem Cmdlet an ein anderes Anbieter-Cmdlet senden.
Weitere Informationen zur Verwendung der Pipeline mit Anbieter-Cmdlets finden Sie in den Cmdlet-Referenzen in diesem Artikel.

## <a name="getting-help"></a>Hilfe

Ab Windows PowerShell 3.0 können Sie benutzerdefinierte Hilfethemen für Anbieter-Cmdlets abrufen, die erläutern, wie sich diese Cmdlets in einem Dateisystemlaufwerk verhalten.

Zum Aufrufen der Hilfe Themen, die für das Dateisystem Laufwerk angepasst sind, führen Sie einen [Get-Help-](xref:Microsoft.PowerShell.Core.Get-Help) Befehl in einem Dateisystem Laufwerk aus, oder verwenden Sie den `-Path` -Parameter von [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) zum Angeben eines Dateisystem Laufwerks.

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path variable:
```

## <a name="see-also"></a>Weitere Informationen:

[about_Variables](../About/about_Variables.md)

[about_Automatic_Variables](../About/about_Automatic_Variables.md)

[about_Providers](../About/about_Providers.md)
