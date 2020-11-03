---
description: Umgebung
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Umgebungsanbieter
ms.openlocfilehash: 354d6b0d07ac93a0b1a40543ca1e301a785ca934
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221692"
---
# <a name="environment-provider"></a>Umgebungs Anbieter

## <a name="provider-name"></a>Anbietername
Environment

## <a name="drives"></a>Laufwerke

`Env:`

## <a name="capabilities"></a>Funktionen

**ShouldProcess**

## <a name="short-description"></a>Kurze Beschreibung

Bietet Zugriff auf die Windows-Umgebungsvariablen.

## <a name="detailed-description"></a>Detaillierte Beschreibung

Mit dem PowerShell- **Umgebungs** Anbieter können Sie Umgebungsvariablen und-Werte in PowerShell erhalten, hinzufügen, ändern, löschen und löschen.

**Umgebungs** Variablen sind dynamisch benannte Variablen, die die Umgebung beschreiben, in der die Programme ausgeführt werden. Windows und PowerShell verwenden Umgebungsvariablen zum Speichern von persistenten Informationen, die sich auf die System-und Prozess Ausführung auswirken. Im Gegensatz zu PowerShell-Variablen unterliegen Umgebungsvariablen keinen Bereichs Einschränkungen.

Das **Umgebungs** Laufwerk ist ein flacher Namespace, der die Umgebungsvariablen enthält, die spezifisch für die Sitzung des aktuellen Benutzers sind. Die Umgebungsvariablen haben keine untergeordneten Elemente.

Der **Umgebungs** Anbieter unterstützt die folgenden Cmdlets, die in diesem Artikel behandelt werden.

- [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location)
- [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location)
- [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
- [New-Item](xref:Microsoft.PowerShell.Management.New-Item)
- [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item)
- [Clear-Item](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a>Von diesem Anbieter verfügbar gemachte Typen

Jede Umgebungsvariable ist eine Instanz der Klasse [System. Collections. ditionaryentry](/dotnet/api/system.collections.dictionaryentry) . Der Name der Variablen ist der Wörterbuchschlüssel. Der Wert der Umgebungsvariablen ist der Wörterbuchwert.

## <a name="navigating-the-environment-drive"></a>Navigieren im Umgebungs Laufwerk

Der **Umgebungs** Anbieter stellt seinen Datenspeicher im `Env:` Laufwerk bereit. Um mit Umgebungsvariablen zu arbeiten, ändern Sie den Speicherort in das `Env:` Laufwerk ( `Set-Location Env:` ), oder arbeiten Sie von einem anderen PowerShell-Laufwerk aus. Um auf eine Umgebungsvariable von einem anderen Speicherort zu verweisen, verwenden Sie den `Env:` Laufwerks Namen im Pfad.

```powershell
Set-Location Env:
```

Um zu einem Dateisystemlaufwerk zurückzukehren, geben Sie den Namen des Laufwerks ein. Beispiel:

```powershell
Set-Location C:
```

Sie können auch mit dem **Umgebungs** Anbieter von einem beliebigen anderen PowerShell-Laufwerk aus arbeiten. Um auf eine Umgebungsvariable von einem anderen Speicherort zu verweisen, verwenden Sie den Laufwerks Namen `Env:` im Pfad.

Der **Umgebungs** Anbieter macht auch Umgebungsvariablen mithilfe eines Variablen Präfixes von verfügbar `$env:` .  Mit dem folgenden Befehl wird der Inhalt der Programmier Umgebungsvariablen " **Program Files** " angezeigt. Das `$env:` Variablen Präfix kann von jedem beliebigen PowerShell-Laufwerk verwendet werden.

```
PS C:\> $env:ProgramFiles
C:\Program Files
```

Sie können auch den Wert einer Umgebungsvariablen ändern, indem Sie das `$env:` Variablen Präfix verwenden.  Alle vorgenommenen Änderungen beziehen sich nur auf die aktuelle PowerShell-Sitzung, solange Sie aktiv ist.

> [!NOTE]
> PowerShell verwendet Aliase, um Ihnen eine vertraute Möglichkeit zum Arbeiten mit Anbieter Pfaden zu bieten. Befehle wie `dir` und `ls` sind jetzt Aliase für [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` ist ein Alias für [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location). und `pwd` ist ein Alias für [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).

## <a name="getting-environment-variables"></a>Umgebungsvariablen werden erhalten.

Mit diesem Befehl werden alle Umgebungsvariablen in der aktuellen Sitzung aufgelistet.

```powershell
Get-Item -Path Env:
```

Sie können diesen Befehl in jedem beliebigen PowerShell-Laufwerk verwenden.

Der Umgebungs Anbieter hat keine Container, sodass der obige Befehl bei der Verwendung mit denselben Effekt hat `Get-ChildItem` .

```powershell
Get-ChildItem -Path Env:
```

### <a name="get-a-selected-environment-variable"></a>Ausgewählte Umgebungsvariable erhalten

Mit diesem Befehl wird die `WINDIR` Umgebungs Variable abgerufen.

```powershell
Get-ChildItem -Path Env:windir
```

Sie können auch das Variablen Präfix Format verwenden.

```powershell
$env:windir
```

## <a name="create-an-environment-variable"></a>Erstellen einer Umgebungsvariablen

Mit diesem Befehl wird die `USERMODE` Umgebungsvariable mit dem Wert "Non-Admin" erstellt. Der `-Path` Parameterwert erstellt das neue Element im `Env:` Laufwerk. Die neue Umgebungsvariable kann nur in der aktuellen PowerShell-Sitzung verwendet werden, solange Sie aktiv ist.

```powershell
PS C:\> New-Item -Path Env: -Name USERMODE -Value Non-Admin
```

## <a name="changing-an-environment-variable"></a>Ändern einer Umgebungsvariablen

### <a name="rename-an-environment-variable"></a>Umbenennen einer Umgebungsvariablen

Dieser Befehl verwendet das `Rename-Item` Cmdlet, um den Namen der `USERMODE` Umgebungsvariablen zu ändern, die Sie in erstellt haben `USERROLE` . Ändern Sie nicht den Namen einer Umgebungsvariablen, die das System verwendet. Obwohl diese Änderungen nur die aktuelle Sitzung betreffen, bewirken sie möglicherweise, dass das System oder ein Programm nicht korrekt arbeitet.

```powershell
Rename-Item -Path Env:USERMODE -NewName USERROLE
```

### <a name="change-an-environment-variable"></a>Ändern einer Umgebungsvariablen

Dieser Befehl verwendet das `Set-Item` Cmdlet, um den Wert der `USERROLE` Umgebungsvariablen in "Administrator" zu ändern.

```powershell
Set-Item -Path Env:USERROLE -Value Administrator
```

## <a name="copy-an-environment-variable"></a>Kopieren einer Umgebungsvariablen

Mit diesem Befehl wird der Wert der `USERROLE` Umgebungsvariablen in die `USERROLE2` Umgebungsvariable kopiert.

```powershell
Copy-Item -Path Env:USERROLE -Destination Env:USERROLE2
```

## <a name="remove-an-environment-variable"></a>Entfernen einer Umgebungsvariablen

Dieser Befehl löscht die `USERROLE2` Umgebungsvariable aus der aktuellen Sitzung.

```powershell
Remove-Item -Path Env:USERROLE2
```

## <a name="remove-an-environment-variable-with-clear-item"></a>Entfernen Sie eine Umgebungsvariable mit Clear-Item

Mit diesem Befehl `USERROLE` wird die Umgebungsvariable gelöscht, indem ihr Wert gelöscht wird.

```powershell
Clear-Item -Path Env:USERROLE
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
Get-Help Get-ChildItem -Path env:
```

## <a name="see-also"></a>Weitere Informationen:

[about_Providers](../About/about_Providers.md)
