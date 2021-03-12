---
description: Beschreibt, wie PowerShell bestimmt, welcher Befehl ausgeführt werden soll.
Locale: en-US
ms.date: 02/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_precedence?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Precedence
ms.openlocfilehash: 8b8a27a47c454b59b5dd4bb2d6e8a8cc3cec78c8
ms.sourcegitcommit: 71173a89c4f05b5283ccd1e885a780773c13fa47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "103196244"
---
# <a name="about-command-precedence"></a>Informationen zur Befehls Rangfolge

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt, wie PowerShell bestimmt, welcher Befehl ausgeführt werden soll.

## <a name="long-description"></a>Lange Beschreibung

Befehls Rangfolge: Beschreibt, wie PowerShell bestimmt, welcher Befehl ausgeführt werden soll, wenn eine Sitzung mehr als einen Befehl mit demselben Namen enthält. Befehle in einer Sitzung können ausgeblendet oder durch Befehle mit demselben Namen ersetzt werden. In diesem Artikel wird gezeigt, wie Sie ausgeblendete Befehle ausführen und Konflikte mit Befehlsnamen vermeiden.

## <a name="command-precedence"></a>Befehls Rangfolge

Wenn eine PowerShell-Sitzung mehr als einen Befehl mit demselben Namen enthält, bestimmt PowerShell anhand der folgenden Regeln, welcher Befehl ausgeführt werden soll.

Wenn Sie den Pfad zu einem Befehl angeben, führt PowerShell den Befehl an dem Speicherort aus, der durch den Pfad angegeben wird.

Der folgende Befehl führt beispielsweise das FindDocs.ps1 Skript im Verzeichnis "C: \\ techdocs" aus:

```
C:\TechDocs\FindDocs.ps1
```

Als Sicherheits Feature führt PowerShell keine ausführbaren (nativen) Befehle (einschließlich PowerShell-Skripts) aus, es sei denn, der Befehl befindet sich in einem Pfad, der in der PATH-Umgebungsvariablen aufgelistet ist, `$env:path` oder es sei denn, Sie geben den Pfad zur Skriptdatei an.

Zum Ausführen eines Skripts, das sich im aktuellen Verzeichnis befindet, geben Sie den vollständigen Pfad an, oder geben Sie einen Punkt ein, `.\` um das aktuelle Verzeichnis darzustellen.

Wenn Sie z. b. die FindDocs.ps1 Datei im aktuellen Verzeichnis ausführen möchten, geben Sie Folgendes ein:

```
.\FindDocs.ps1
```

### <a name="using-wildcards-in-execution"></a>Verwenden von Platzhaltern bei der Ausführung

In der Befehlsausführung können Sie Platzhalter verwenden. Die Verwendung von Platzhalter Zeichen wird auch als " *glob"* bezeichnet.

PowerShell führt eine Datei mit einer Platzhalter Übereinstimmung vor einer Literalübereinstimmung aus.

Nehmen Sie beispielsweise ein Verzeichnis mit den folgenden Dateien:

```
Get-ChildItem C:\temp\test


    Directory: C:\temp\test


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        5/20/2019   2:29 PM             28 a.ps1
-a----        5/20/2019   2:29 PM             28 [a1].ps1
```

Beide Skriptdateien weisen den gleichen Inhalt auf: `$MyInvocation.MyCommand.Path` .
Dieser Befehl zeigt den Namen des Skripts an, das aufgerufen wird.

Wenn Sie Ausführen `[a1].ps1` , wird die Datei `a.ps1` ausgeführt, auch wenn die Datei `[a1].ps1` eine Literalübereinstimmung ist.

```powershell
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\a.ps1
```

Löschen Sie nun die `a.ps1` Datei, und versuchen Sie erneut, Sie auszuführen.

```powershell
Remove-Item C:\temp\test\a.ps1
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\[a1].ps1
```

Sie können in der Ausgabe sehen, die `[a1].ps1` dieses Mal ausgeführt wird, da die Literalübereinstimmung für dieses Platzhalter Muster die einzige Datei Übereinstimmung ist.

Weitere Informationen zur Verwendung von Platzhaltern in PowerShell finden Sie unter [about_Wildcards](about_Wildcards.md).

> [!NOTE]
> Um die Suche auf einen relativen Pfad einzuschränken, müssen Sie dem Skriptnamen den Pfad voranstellen `.\` . Dies schränkt die Suche nach Befehlen auf Dateien in diesem relativen Pfad ein. Ohne dieses Präfix können andere PowerShell-Syntax Konflikte verursachen, und es gibt nur wenige Garantien, dass die Datei gefunden wird.

Wenn Sie keinen Pfad angeben, verwendet PowerShell die folgende Rangfolge, wenn Befehle für alle in der aktuellen Sitzung geladenen Elemente ausgeführt werden:

  1. Alias
  2. Funktion
  3. Cmdlet
  4. Externe ausführbare Dateien (Programme und nicht-PowerShell-Skripts)

Wenn Sie "Help" eingeben, sucht PowerShell zunächst nach einem Alias mit dem Namen `help` , dann nach einer Funktion mit dem Namen `Help` und schließlich nach einem Cmdlet mit dem Namen `Help` . Er führt das erste gefundene `help` Element aus.

Wenn Ihre Sitzung z. b. ein Cmdlet und eine Funktion enthält, `Get-Map` bei der Sie eingeben, `Get-Map` führt PowerShell die Funktion aus.

> [!NOTE]
> Dies gilt nur für geladene Befehle. Wenn eine `build` ausführbare Datei und ein Alias `build` für eine Funktion mit dem Namen `Invoke-Build` innerhalb eines Moduls vorhanden sind, das nicht in die aktuelle Sitzung geladen wird, führt PowerShell `build` stattdessen die ausführbare Datei aus. Module werden nicht automatisch geladen, wenn in diesem Fall die externe ausführbare Datei gefunden wird. Nur wenn keine externe ausführbare Datei gefunden wird, wird ein Alias, eine Funktion oder ein Cmdlet mit dem angegebenen Namen aufgerufen, wodurch das automatische Laden des Moduls ausgelöst wird.

Wenn die Sitzung Elemente desselben Typs enthält, die denselben Namen aufweisen, führt PowerShell das neuere Element aus.

Wenn Sie z. b. ein anderes `Get-Date` Cmdlet aus einem Modul importieren, `Get-Date` führt PowerShell die importierte Version über die systemeigene Version aus, wenn Sie eingeben.

## <a name="hidden-and-replaced-items"></a>Ausgeblendete und ersetzte Elemente

Aufgrund dieser Regeln können Elemente durch Elemente mit dem gleichen Namen ersetzt oder ausgeblendet werden.

Elemente sind "ausgeblendet" oder "Shadowing", wenn Sie weiterhin auf das ursprüngliche Element zugreifen können, z. b. indem Sie den Elementnamen mit einem Modul-oder Snap-in-Namen qualifizieren.

Wenn Sie z. b. eine Funktion importieren, die den gleichen Namen wie ein Cmdlet in der Sitzung hat, ist das Cmdlet ausgeblendet (aber nicht ersetzt), da es aus einem Snap-in oder Modul importiert wurde.

Elemente werden ersetzt oder überschrieben, wenn Sie nicht mehr auf das ursprüngliche Element zugreifen können.

Wenn Sie z. b. eine Variable importieren, die denselben Namen wie eine Variable in der Sitzung hat, wird die ursprüngliche Variable ersetzt und ist nicht mehr verfügbar.
Eine Variable kann nicht mit einem Modulnamen qualifiziert werden.

Wenn Sie eine Funktion in der Befehlszeile eingeben und dann eine Funktion mit demselben Namen importieren, wird die ursprüngliche Funktion ersetzt und ist nicht mehr verfügbar.

### <a name="finding-hidden-commands"></a>Suchen von verdeckten Befehlen

Der **all** -Parameter des [Get-Command-](xref:Microsoft.PowerShell.Core.Get-Command) Cmdlets Ruft alle Befehle mit dem angegebenen Namen ab, auch wenn Sie ausgeblendet oder ersetzt werden. Ab PowerShell 3,0 ruft standardmäßig nur die Befehle ab, die ausgeführt werden, `Get-Command` Wenn Sie den Befehlsnamen eingeben.

In den folgenden Beispielen schließt die Sitzung eine `Get-Date` Funktion und ein [Get-Date-](xref:Microsoft.PowerShell.Utility.Get-Date) Cmdlet ein.

Der folgende Befehl ruft den Befehl ab, der ausgeführt wird `Get-Date` , wenn Sie eingeben `Get-Date` .

```powershell
Get-Command Get-Date
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
```

Der folgende Befehl verwendet den **all** -Parameter, um alle Befehle zu erhalten `Get-Date` .

```powershell
Get-Command Get-Date -All
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
Cmdlet          Get-Date                  Microsoft.PowerShell.Utility
```

### <a name="running-hidden-commands"></a>Ausführen von verdeckten Befehlen

Sie können bestimmte Befehle ausführen, indem Sie Element Eigenschaften angeben, die den Befehl von anderen Befehlen unterscheiden, die denselben Namen aufweisen können. Mit dieser Methode können Sie einen beliebigen Befehl ausführen, dies ist jedoch besonders nützlich für das Ausführen von ausgeblendeten Befehlen.

#### <a name="qualified-names"></a>Qualifizierte Namen

Wenn Sie den mit dem Modul gekennzeichneten Namen eines Cmdlets verwenden, können Sie Befehle ausführen, die von einem Element mit dem gleichen Namen ausgeblendet werden. Beispielsweise können Sie das `Get-Date` Cmdlet ausführen, indem Sie es mit dem Modulnamen " **Microsoft. PowerShell. Utility**" qualifizieren.

Verwenden Sie diese bevorzugte Methode, wenn Sie Skripts schreiben, die Sie verteilen möchten. Sie können nicht vorhersagen, welche Befehle in der Sitzung vorhanden sein können, in der das Skript ausgeführt wird.

```powershell
New-Alias -Name "Get-Date" -Value "Get-ChildItem"
Microsoft.PowerShell.Utility\Get-Date
```

```output
Tuesday, September 4, 2018 8:17:25 AM
```

Um einen Befehl auszuführen, `New-Map` der durch das Modul hinzugefügt wurde `MapFunctions` , verwenden Sie den mit dem Modul qualifizierten Namen:

```powershell
MapFunctions\New-Map
```

Um das Modul zu finden, aus dem ein Befehl importiert wurde, verwenden Sie die **ModuleName** -Eigenschaft der Befehle.

```
(Get-Command <command-name>).ModuleName
```

Wenn Sie z. b. die Quelle des `Get-Date` Cmdlets ermitteln möchten, geben Sie Folgendes ein:

```powershell
(Get-Command Get-Date).ModuleName
```

```output
Microsoft.PowerShell.Utility
```

> [!NOTE]
> Variablen oder Aliase können nicht qualifiziert werden.

#### <a name="call-operator"></a>Calloperator

Sie können auch den-Operator verwenden, um ausgeblendete `Call` `&` Befehle auszuführen, indem Sie Sie mit einem [Get-ChildItem-](xref:Microsoft.PowerShell.Management.Get-ChildItem) Rückruf (Alias ist "dir") `Get-Command` oder [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)kombinieren.

Der calloperator führt Zeichen folgen und Skriptblöcke in einem untergeordneten Bereich aus. Weitere Informationen finden Sie unter [about_Operators](about_Operators.md).

Wenn Sie z. b. eine Funktion mit dem Namen haben, die `Map` von einem Alias mit dem Namen ausgeblendet wird `Map` , verwenden Sie den folgenden Befehl, um die Funktion auszuführen.

```powershell
&(Get-Command -Name Map -CommandType Function)
```

oder

```powershell
&(dir Function:\map)
```

Sie können auch den Hidden-Befehl in einer Variablen speichern, um die Benutzerfreundlichkeit zu vereinfachen.

Der folgende Befehl speichert z `Map` . b. die Funktion in der `$myMap` Variablen und verwendet dann den- `Call` Operator, um Sie auszuführen.

```powershell
$myMap = (Get-Command -Name map -CommandType function)
&($myMap)
```

### <a name="replaced-items"></a>Ersetzte Elemente

Ein ersetzter Eintrag ist ein Element, auf das Sie nicht mehr zugreifen können. Sie können Elemente ersetzen, indem Sie Elemente desselben Namens aus einem Modul oder Snap-in importieren.

Wenn Sie z. b. `Get-Map` in der Sitzung eine Funktion eingeben und eine Funktion mit dem Namen importieren `Get-Map` , ersetzt Sie die ursprüngliche Funktion. Sie können Sie nicht in der aktuellen Sitzung abrufen.

Variablen und Aliase können nicht ausgeblendet werden, da Sie keinen aufrufsoperator oder einen qualifizierten Namen verwenden können, um Sie auszuführen. Wenn Sie Variablen und Aliase aus einem Modul oder Snap-in importieren, werden die Variablen in der Sitzung durch denselben Namen ersetzt.

### <a name="avoiding-name-conflicts"></a>Vermeiden von Namenskonflikten

Die beste Möglichkeit zum Verwalten von Befehlsnamen Konflikten besteht darin, Sie zu verhindern. Wenn Sie die Befehle benennen, verwenden Sie einen eindeutigen Namen. Fügen Sie z. b. die Initialen oder das Akronym Ihres Firmennamens den Substantiven in ihren Befehlen hinzu.

Wenn Sie Befehle aus einem PowerShell-Modul oder einer anderen Sitzung in die Sitzung importieren, verwenden Sie außerdem den- `Prefix` Parameter von [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) oder

[Import-PSSession-](xref:Microsoft.PowerShell.Utility.Import-PSSession) Cmdlet, um den Substantiven in den Namen der Befehle ein Präfix hinzuzufügen.

Beispielsweise werden mit dem folgenden Befehl Konflikte mit dem `Get-Date` - `Set-Date` Cmdlet und dem-Cmdlet vermieden, die in PowerShell enthalten sind, wenn Sie das `DateFunctions` Modul importieren.

```powershell
Import-Module -Name DateFunctions -Prefix ZZ
```

Weitere Informationen finden Sie `Import-Module` unter und weiter `Import-PSSession` unten.

## <a name="see-also"></a>Weitere Informationen:

- [about_Path_Syntax](about_Path_Syntax.md)
- [about_Aliases](about_Aliases.md)
- [about_Functions](about_Functions.md)
- [Alias-Provider](../../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)
- [Function-Provider](../../Microsoft.PowerShell.Core/About/about_Function_Provider.md)
- [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)
- [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)
- [Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession)

