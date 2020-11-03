---
description: Funktion
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_function_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Funktionsanbieter
ms.openlocfilehash: 0323433d5ab9114dd1bb21afc47b7fa7db3d6f8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221615"
---
# <a name="function-provider"></a>Funktions Anbieter

## <a name="provider-name"></a>Anbietername
Funktion

## <a name="drives"></a>Laufwerke

`Function:`

## <a name="capabilities"></a>Funktionen

**ShouldProcess**

## <a name="short-description"></a>Kurze Beschreibung

Bietet Zugriff auf die Funktionen, die in PowerShell definiert sind.

## <a name="detailed-description"></a>Detaillierte Beschreibung

Mit dem PowerShell- **Funktions** Anbieter können Sie die Funktionen und Filter in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.

Eine Funktion ist ein benannter Codeblock, der eine Aktion ausführt. Wenn Sie den Namen der Funktion eingeben, wird der Code in der Funktion ausgeführt. Ein Filter ist ein benannter Codeblock, der Bedingungen für eine Aktion festlegt. Sie können den Namen des Filters anstelle der Bedingung eingeben, z. b. in einem `Where-Object` Befehl.

Das **Funktions** Laufwerk ist ein flacher Namespace, der nur die Funktions-und Filter Objekte enthält. Weder Funktionen noch Filter haben untergeordnete Elemente.

Der **Funktions** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a>Von diesem Anbieter verfügbar gemachte Typen

Jede Funktion ist eine Instanz der [System. Management. Automation. functioninfo](/dotnet/api/system.management.automation.functioninfo) -Klasse. Jeder Filter ist eine Instanz der [System. Management. Automation. FilterInfo](/dotnet/api/system.management.automation.filterinfo) -Klasse.

## <a name="navigating-the-function-drive"></a>Navigieren im Funktions Laufwerk

Der **Funktions** Anbieter stellt seinen Datenspeicher im `Function:` Laufwerk bereit. Um mit Funktionen arbeiten zu können, können Sie den Speicherort in das `Function:` Laufwerk ( `Set-Location Function:` ) ändern. Oder Sie können von einem anderen PowerShell-Laufwerk aus arbeiten. Um auf eine Funktion von einem anderen Speicherort zu verweisen, verwenden Sie den Laufwerk Namen ( `Function:` ) im Pfad.

```powershell
Set-Location Function:
```

Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein. Beispiel:

```powershell
Set-Location C:
```

Sie können auch mit dem **Funktions** Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten. Um auf eine Funktion von einem anderen Speicherort zu verweisen, verwenden Sie den Namen des Laufwerks `Function:` im Pfad.

> [!NOTE]
> PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten. Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="getting-functions"></a>Funktionen werden erhalten

Dieser Befehl ruft die Liste aller Funktionen in der aktuellen Sitzung ab. Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.

```powershell
Get-ChildItem -Path Function:
```

Der Funktions Anbieter hat keine Container, sodass der obige Befehl bei der Verwendung mit dieselbe Auswirkung hat `Get-ChildItem` .

```powershell
Get-ChildItem -Path Function:
```

Sie können die Definition einer Funktion abrufen, indem Sie wie unten gezeigt auf die **Definition** -Eigenschaft zugreifen.

```powershell
(Get-Item -Path function:more).Definition
```

Sie können auch die Definition einer Funktion mithilfe Ihres Anbieter Pfads abrufen, dem das Dollarzeichen () vorangestellt ist `$` .

```powershell
$function:more
```

### <a name="getting-selected-functions"></a>Ausgewählte Funktionen werden ausgewählt.

Mit diesem Befehl wird die `man` Funktion vom `Function:` Laufwerk abgerufen. Er verwendet das `Get-Item` Cmdlet, um die Funktion zu erhalten. Der Pipeline Operator ( `|` ) sendet das Ergebnis an `Format-Table` . Der- `-Wrap` Parameter leitet Text, der nicht in die Zeile passt, auf die nächste Zeile. Der- `-Autosize` Parameter ändert die Größe der Tabellen Spalten, um den Text aufnehmen zu können.

```powershell
Get-Item -Path man | Format-Table -Wrap -Autosize
```

### <a name="working-with-function-provider-paths"></a>Arbeiten mit Funktions Anbieter Pfaden

Diese Befehle erhalten beide die Funktion mit dem Namen `c:` . Der erste Befehl kann in einem beliebigen Laufwerk verwendet werden. Der zweite Befehl wird im Laufwerk verwendet `Function:` . Da der Name mit einem Doppelpunkt endet, was die Syntax für ein Laufwerk ist, müssen Sie den Pfad mit dem Namen des Laufwerks verwenden. Innerhalb des `Function:` Laufwerks können Sie beide Formate verwenden. Im zweiten Befehl stellt der Punkt ( `.` ) den aktuellen Speicherort dar.

```
PS C:\> Get-Item -Path Function:c:
PS Function:\> Get-Item -Path .\c:
```

## <a name="creating-a-function"></a>Erstellen einer Funktion

Dieser Befehl verwendet das `New-Item` Cmdlet, um eine Funktion mit dem Namen zu erstellen `Win32:` .
Der Ausdruck in Klammern ist der Skriptblock, der durch den Namen der Funktion dargestellt wird.

```powershell
New-Item -Path Function:Win32: -Value {Set-Location C:\Windows\System32}
```

Sie können auch eine Funktion erstellen, indem Sie Sie in der PowerShell-Befehlszeile eingeben. Beispiel: TPE `Function:Win32: {Set-Location C:\Windows\System32}` . Wenn Sie sich auf dem `Function:` Laufwerk befinden, können Sie den Namen des Laufwerks weglassen.

## <a name="deleting-a-function"></a>Löschen einer Funktion

Dieser Befehl löscht die `more:` Funktion aus der aktuellen Sitzung.

```powershell
Remove-Item Function:more:
```

## <a name="changing-a-function"></a>Ändern einer Funktion

Dieser Befehl verwendet das `Set-Item` Cmdlet, um die `prompt` Funktion so zu ändern, dass Sie die Zeit vor dem Pfad anzeigt.

```powershell
Set-Item -Path Function:prompt -Value {
  'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '
  }
```

### <a name="rename-a-function"></a>Umbenennen einer Funktion

Dieser Befehl verwendet das `Rename-Item` Cmdlet, um den Namen der `help` Funktion in zu ändern `gh` .

```powershell
Rename-Item -Path Function:help -NewName gh
```

## <a name="copying-a-function"></a>Kopieren einer Funktion

Mit diesem Befehl `prompt` wird die Funktion in kopiert `oldPrompt` , wodurch ein neuer Name für den Skriptblock erstellt wird, der der prompt-Funktion zugeordnet ist.
Dadurch können Sie die ursprüngliche "prompt"-Funktion speichern, wenn Sie planen, sie zu ändern.
Die **options** -Eigenschaft der neuen Funktion hat den Wert `None` . Verwenden Sie, um den Wert der **options** -Eigenschaft zu ändern `Set-Item` .

```powershell
Copy-Item -Path Function:prompt -Destination Function:oldPrompt
```

## <a name="dynamic-parameters"></a>Dynamische Parameter

Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.

### <a name="options-systemmanagementautomationscopeditemoptions"></a>Optionen < [System. Management. Automation. scopeditemoptions] >

Bestimmt den Wert der **options** -Eigenschaft einer Funktion.

- `None`: Keine Optionen. `None` ist die Standardoption.
- `Constant`: Die Funktion kann nicht gelöscht werden, und ihre Eigenschaften können nicht geändert werden. `Constant` ist nur verfügbar, wenn Sie eine Funktion erstellen.
  Die Option einer vorhandenen Funktion kann nicht in geändert werden `Constant` .
- `Private`: Die Funktion ist nur im aktuellen Gültigkeitsbereich sichtbar.
- (nicht in untergeordneten Bereichen).
- `ReadOnly`: Die Eigenschaften der Funktion können nicht geändert werden, es sei denn, Sie verwenden den- `-Force` Parameter. Sie können verwenden `Remove-Item` , um die Funktion zu löschen.
- `AllScope`: Die Funktion wird in neue Bereiche kopiert, die erstellt werden.

### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)

- [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item)

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
Get-Help Get-ChildItem -Path function:
```

## <a name="see-also"></a>Weitere Informationen:

[about_Functions](../About/about_Functions.md)

[about_Providers](../About/about_Providers.md)
