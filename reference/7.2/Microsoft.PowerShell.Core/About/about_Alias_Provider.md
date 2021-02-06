---
description: Alias
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_alias_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Aliasanbieter
ms.openlocfilehash: d6bfbaf878a6d971b1e01d963faec8c8ece5d1fc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599215"
---
# <a name="alias-provider"></a>Alias Anbieter

## <a name="provider-name"></a>Anbietername
Alias

## <a name="drives"></a>Laufwerke

`Alias:`

## <a name="capabilities"></a>Funktionen

**ShouldProcess**

## <a name="short-description"></a>Kurze Beschreibung

Bietet Zugriff auf die PowerShell-Aliase und die Werte, die Sie darstellen.

## <a name="detailed-description"></a>Detaillierte Beschreibung

Mit dem PowerShell- **Alias** Anbieter können Sie Aliase in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.

Ein Alias ist ein alternativer Name für ein Cmdlet, eine Funktion, eine ausführbare Datei, einschließlich Skripts. PowerShell enthält eine Reihe integrierter Aliase. Sie können Ihrer aktuellen Sitzung und Ihrem PowerShell-Profil eigene Aliase hinzufügen.

Das **Alias** Laufwerk ist ein flacher Namespace, der nur die Alias Objekte enthält.
Die Aliase haben keine untergeordneten Elemente.

Der **Alias** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

PowerShell umfasst einen Satz von Cmdlets, die zum Anzeigen und Ändern von Aliasen entwickelt wurden. Wenn Sie **Alias** -Cmdlets verwenden, müssen Sie nicht das `Alias:` Laufwerk im Namen angeben. In diesem Artikel wird das Arbeiten mit **Alias** -Cmdlets nicht behandelt.

- [Export-Alias](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [Import-Alias](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [New-Alias](xref:Microsoft.PowerShell.Utility.New-Alias)
- [Set-Alias](xref:Microsoft.PowerShell.Utility.Set-Alias)

## <a name="types-exposed-by-this-provider"></a>Von diesem Anbieter verfügbar gemachte Typen

Jeder Alias ist eine Instanz der [System. Management. Automation. AliasInfo](/dotnet/api/system.management.automation.aliasinfo) -Klasse.

## <a name="navigating-the-alias-drive"></a>Navigieren im Alias Laufwerk

Der **Alias** Anbieter stellt seinen Datenspeicher im `Alias:` Laufwerk bereit. Um mit Aliasen zu arbeiten, können Sie den Speicherort auf das Laufwerk ändern, `Alias:` indem Sie den folgenden Befehl verwenden:

```powershell
Set-Location Alias:
```

Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein. Beispiel:

```powershell
Set-Location C:
```

Sie können auch mit dem Alias Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten. Um auf einen Alias von einem anderen Speicherort zu verweisen, verwenden Sie den `Alias:` Namen des Laufwerks im Pfad.

> [!NOTE]
> PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten. Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

### <a name="displaying-the-contents-of-the-alias-drive"></a>Anzeigen des Inhalts des Alias:-Laufwerks

Mit diesem Befehl wird die Liste aller Aliase abgerufen, wenn der aktuelle Speicherort das `Alias:` Laufwerk ist. Es verwendet ein Platzhalter Zeichen `*` , um den gesamten Inhalt des aktuellen Speicher Orts anzugeben.

```powershell
PS Alias:\> Get-Item -Path *
```

Im `Alias:` Laufwerk haben Sie einen Punkt `.` , der den aktuellen Speicherort darstellt, und ein Platzhalter Zeichen `*` , das alle Elemente am aktuellen Speicherort darstellt. Beispielsweise, `Get-Item -Path .` oder `Get-Item \*` führen Sie das gleiche Ergebnis aus.

Der Alias Anbieter hat keine Container, sodass der obige Befehl bei der Verwendung mit dieselbe Auswirkung hat `Get-ChildItem` .

```powershell
Get-ChildItem -Path Alias:
```

### <a name="get-a-selected-alias"></a>Ausgewählten Alias erhalten

Mit diesem Befehl wird der `ls` Alias abgerufen.
Da Sie den Pfad enthält, können Sie ihn in jedem beliebigen PowerShell-Laufwerk verwenden.

```powershell
Get-Item -Path Alias:ls
```

Wenn Sie sich auf dem `Alias:` Laufwerk befinden, können Sie den Namen des Laufwerks aus dem Pfad weglassen.

Sie können die Definition für einen Alias auch abrufen, indem Sie dem Anbieter Pfad das Dollarzeichen () voranstellen `$` .

```powershell
$Alias:ls
```

### <a name="get-all-aliases-for-a-specific-cmdlet"></a>Alle Aliase für ein bestimmtes Cmdlet erhalten

Mit diesem Befehl wird eine Liste der Aliase abgerufen, die dem `Get-ChildItem` Cmdlet zugeordnet sind. Er verwendet die **Definition** -Eigenschaft, die den Cmdlet-Namen speichert.

```powershell
Get-Item -Path Alias:* | Where-Object {$_.Definition -eq "Get-ChildItem"}
```

## <a name="creating-aliases"></a>Erstellen von Aliasen

### <a name="create-an-alias-from-the-alias-drive"></a>Erstellen eines Alias über das Alias:-Laufwerk

Mit diesem Befehl wird der `serv` Alias für das `Get-Service` Cmdlet erstellt. Da sich der aktuelle Speicherort im `Alias:` Laufwerk befindet, `-Path` wird der-Parameter nicht benötigt.

Dieser Befehl verwendet außerdem den `-Options` Dynamic-Parameter, um die **allscope** -Option für den Alias festzulegen. Der- `-Options` Parameter ist nur im- `New-Item` Cmdlet verfügbar, wenn Sie sich auf dem- `Alias:` Laufwerk befinden. Der Punkt ( `.` ) gibt das aktuelle Verzeichnis an, das das Alias Laufwerk ist.

```
PS Alias:\> New-Item -Path . -Name serv -Value Get-Service -Options "AllScope"
```

### <a name="create-an-alias-with-an-absolute-path"></a>Einen Alias mit einem absoluten Pfad erstellen

Sie können einen Alias für jedes Element erstellen, das einen Befehl aufruft.
Mit diesem Befehl wird der `np` Alias für erstellt `Notepad.exe` .

```powershell
New-Item -Path Alias:np -Value c:\windows\notepad.exe
```

### <a name="create-an-alias-to-a-new-function"></a>Erstellen eines Alias für eine neue Funktion

Sie können einen Alias für jede Funktion erstellen. Mit diesem Feature können Sie einen Alias erstellen, der ein Cmdlet und die entsprechenden Parameter enthält.

Der erste Befehl erstellt die- `CD32` Funktion, die das aktuelle Verzeichnis in das `System32` Verzeichnis ändert. Mit dem zweiten Befehl wird der `go` Alias für die `CD32` Funktion erstellt.

Wenn der Befehl fertig ist, können Sie entweder oder verwenden, `CD32` `go` um die Funktion aufzurufen.

```powershell
function CD32 {Set-Location -Path c:\windows\system32}
Set-Item -Path Alias:go -Value CD32
```

## <a name="changing-aliases"></a>Ändern von Aliasen

### <a name="change-the-options-of-an-alias"></a>Ändern der Optionen eines Alias

Sie können das `Set-Item` Cmdlet mit dem `-Options` dynamischen Parameter verwenden, um den Wert der- `-Options` Eigenschaft eines Alias zu ändern.

Dieser Befehl legt die Optionen " **allscope** " und "read **only** " für den `dir` Alias fest. Der Befehl verwendet den `-Options` dynamischen Parameter des `Set-Item` Cmdlets. Der- `-Options` Parameter ist in verfügbar, `Set-Item` Wenn er mit dem **Alias** -oder **Funktions** Anbieter verwendet wird.

```powershell
Set-Item -Path Alias:dir -Options "AllScope,ReadOnly"
```

### <a name="change-an-aliases-referenced-command"></a>Ändern eines referenzierten Aliase-Befehls

Dieser Befehl verwendet das `Set-Item` Cmdlet, um den `gp` Alias so zu ändern, dass er das `Get-Process` Cmdlet anstelle des `Get-ItemProperty` Cmdlets darstellt.
Der- `-Force` Parameter ist erforderlich, da der Wert der **options** -Eigenschaft des `gp` Alias auf festgelegt ist `ReadOnly` . Da der Befehl innerhalb des Laufwerks übermittelt wird `Alias:` , ist das Laufwerk im Pfad nicht angegeben.

```powershell
Set-Item -Path gp -Value Get-Process -Force
```

Die Änderung wirkt sich auf die vier Eigenschaften aus, die die Zuordnung zwischen dem Alias und dem Befehl definieren. Um die Auswirkung der Änderung anzuzeigen, geben Sie den folgenden Befehl ein:

```powershell
Get-Item -Path gp | Format-List -Property *
```

### <a name="rename-an-alias"></a>Umbenennen eines Alias

Dieser Befehl verwendet das `Rename-Item` Cmdlet, um den `popd` Alias in zu ändern `pop` .

```powershell
Rename-Item -Path Alias:popd -NewName pop
```

## <a name="copying-an-alias"></a>Kopieren eines Alias

Mit diesem Befehl `pushd` wird der Alias kopiert, sodass ein neuer `push` Alias für das `Push-Location` Cmdlet erstellt wird.

Beim Erstellen des neuen Alias hat die **Description** -Eigenschaft einen NULL-Wert.
Und die **Option** -Eigenschaft hat den Wert `None` . Wenn der Befehl innerhalb des `Alias:` Laufwerks ausgegeben wird, können Sie den Namen des Laufwerks aus dem Wert des- `-Path` Parameters weglassen.

```powershell
Copy-Item -Path Alias:pushd -Destination Alias:push
```

## <a name="deleting-an-alias"></a>Löschen eines Alias

Dieser Befehl löscht den `serv` Alias aus der aktuellen Sitzung.
Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.

```powershell
Remove-Item -Path Alias:serv
```

Dieser Befehl löscht alle Aliase, die mit "s" beginnen.
Schreibgeschützte Aliase werden nicht gelöscht.

```powershell
Clear-Item -Path Alias:s*
```

### <a name="delete-read-only-aliases"></a>Schreibgeschützte Aliase löschen

Dieser Befehl löscht alle Aliase aus der aktuellen Sitzung, mit Ausnahme derjenigen mit dem Wert `Constant` für die **options** -Eigenschaft. Der- `-Force` Parameter ermöglicht dem Befehl das Löschen von Aliasen, deren **options** -Eigenschaft den Wert hat `ReadOnly` .

```powershell
Remove-Item Alias:* -Force
```

## <a name="dynamic-parameters"></a>Dynamische Parameter

Dynamische Parameter sind Cmdlet-Parameter, die von einem PowerShell-Anbieter hinzugefügt werden und nur verfügbar sind, wenn das Cmdlet im Anbieter fähigen Laufwerk verwendet wird.

### <a name="options-systemmanagementautomationscopeditemoptions"></a>Optionen [System. Management. Automation. scopeditemoptions]

Bestimmt den Wert der **options** -Eigenschaft eines Alias.

- **Keine: keine** Optionen. Dies ist der Standardwert.
- **Constant**: der Alias kann nicht gelöscht werden, und seine Eigenschaften können nicht geändert werden.
  **Constant** ist nur verfügbar, wenn Sie einen Alias erstellen. Die Option eines vorhandenen Alias kann nicht in " **Constant**" geändert werden.
- **Privat**: der Alias ist nur im aktuellen Gültigkeitsbereich, nicht in den untergeordneten Bereichen sichtbar.
- Schreib **geschützt: die** Eigenschaften des Alias können nicht geändert werden, es sei denn, Sie verwenden den- `-Force` Parameter. Sie können verwenden `Remove-Item` , um den Alias zu löschen.
- **Allscope**: der Alias wird in neue Bereiche kopiert, die erstellt werden.

#### <a name="cmdlets-supported"></a>Unterstützte Cmdlets

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
Get-Help Get-ChildItem -Path alias:
```

## <a name="see-also"></a>Weitere Informationen

[about_Aliases](../About/about_Aliases.md)

[about_Providers](../About/about_Providers.md)

