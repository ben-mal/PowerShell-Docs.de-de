---
description: Erläutert das Konzept des Bereichs in PowerShell und zeigt, wie der Bereich von Elementen festgelegt und geändert wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scopes?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_scopes
ms.openlocfilehash: 2149a1dec14e4de9c6ff1021e98689ca93307cb8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220615"
---
# <a name="about-scopes"></a>Informationen zu Bereichen

## <a name="short-description"></a>Kurze Beschreibung
Erläutert das Konzept des Bereichs in PowerShell und zeigt, wie der Bereich von Elementen festgelegt und geändert wird.

## <a name="long-description"></a>Lange Beschreibung

PowerShell schützt den Zugriff auf Variablen, Aliase, Funktionen und PowerShell-Laufwerke (PSDrives), indem er einschränkt, wo Sie gelesen und geändert werden können. PowerShell verwendet Bereichs Regeln, um sicherzustellen, dass Sie nicht versehentlich ein Element ändern, das nicht geändert werden sollte.

Im folgenden sind die grundlegenden Regeln des Bereichs aufgeführt:

- Bereiche können geschachtelt werden. Ein äußerer Bereich wird als übergeordneter Bereich bezeichnet. Alle untergeordneten Bereiche sind untergeordnete Bereiche dieses übergeordneten Bereichs.

- Ein Element ist in dem Bereich, in dem es erstellt wurde, und in allen untergeordneten Bereichen sichtbar, es sei denn, Sie machen es explizit als privat. Sie können Variablen, Aliase, Funktionen oder PowerShell-Laufwerke in einem oder mehreren Bereichen platzieren.

- Ein Element, das Sie in einem Bereich erstellt haben, kann nur in dem Bereich geändert werden, in dem es erstellt wurde, es sei denn, Sie geben explizit einen anderen Bereich an.

Wenn Sie ein Element in einem Bereich erstellen und der Name des Elements mit einem Element in einem anderen Bereich geteilt wird, ist das ursprüngliche Element möglicherweise unter dem neuen Element ausgeblendet, aber es wird nicht überschrieben oder geändert.

## <a name="powershell-scopes"></a>PowerShell-Bereiche

PowerShell unterstützt die folgenden Bereiche:

- Global: der Gültigkeitsbereich, der beim Starten von PowerShell wirksam ist. Variablen und Funktionen, die beim Start von PowerShell vorhanden sind, wurden im globalen Gültigkeitsbereich erstellt, z. b. automatische Variablen und Einstellungs Variablen. Die Variablen, Aliase und Funktionen in ihren PowerShell-Profilen werden ebenfalls im globalen Gültigkeitsbereich erstellt.

- Local: der aktuelle Bereich. Der lokale Bereich kann der globale Gültigkeitsbereich oder ein beliebiger anderer Bereich sein.

- Skript: der Bereich, der erstellt wird, während eine Skriptdatei ausgeführt wird. Nur die Befehle im Skript werden im Skript Bereich ausgeführt. Für die Befehle in einem Skript ist der Skript Bereich der lokale Gültigkeitsbereich.

> [!NOTE]
> " **Private** " ist kein Bereich. Es handelt sich um eine [Option](#private-option) , mit der die Sichtbarkeit eines Elements außerhalb des Bereichs geändert wird, in dem das Element definiert ist.

## <a name="parent-and-child-scopes"></a>Über-und untergeordnete Bereiche

Sie können einen neuen Bereich erstellen, indem Sie ein Skript oder eine Funktion ausführen, indem Sie eine Sitzung erstellen oder eine neue Instanz von PowerShell starten. Wenn Sie einen neuen Bereich erstellen, ist das Ergebnis ein übergeordneter Bereich (ursprünglicher Bereich) und ein untergeordneter Bereich (der Bereich, den Sie erstellt haben).

In PowerShell sind alle Bereiche untergeordnete Bereiche des globalen Bereichs, Sie können jedoch viele Bereiche und viele rekursive Bereiche erstellen.

Wenn Sie die Elemente nicht explizit als privat festlegen, sind die Elemente im übergeordneten Bereich für den untergeordneten Bereich verfügbar. Elemente, die Sie im untergeordneten Bereich erstellen und ändern, wirken sich jedoch nicht auf den übergeordneten Bereich aus, es sei denn, Sie geben den Bereich explizit an, wenn Sie die Elemente erstellen.

## <a name="inheritance"></a>Vererbung

Ein untergeordneter Bereich erbt nicht die Variablen, Aliase und Funktionen aus dem übergeordneten Bereich. Wenn ein Element nicht privat ist, kann der untergeordnete Bereich die Elemente im übergeordneten Bereich anzeigen. Und Sie können die Elemente ändern, indem Sie den übergeordneten Bereich explizit angeben, aber die Elemente sind nicht Teil des untergeordneten Bereichs.

Ein untergeordneter Bereich wird jedoch mit einer Reihe von Elementen erstellt. In der Regel enthält Sie alle Aliase mit der Option **allscope** . Diese Option wird weiter unten in diesem Artikel erläutert. Sie enthält alle Variablen mit der Option **allscope** sowie einige automatische Variablen.

Verwenden Sie den Scope-Parameter von oder, um die Elemente in einem bestimmten Bereich zu suchen `Get-Variable` `Get-Alias` .

Um beispielsweise alle Variablen im lokalen Gültigkeitsbereich zu erhalten, geben Sie Folgendes ein:

```powershell
Get-Variable -Scope local
```

Um alle Variablen im globalen Gültigkeitsbereich zu erhalten, geben Sie Folgendes ein:

```powershell
Get-Variable -Scope global
```

## <a name="scope-modifiers"></a>Bereichs Modifizierer

Ein Variablen-, Alias-oder Funktionsname kann einen der folgenden optionalen bereichsmodifizierer einschließen:

- `global:` : Gibt an, dass der Name im **globalen** Gültigkeitsbereich vorhanden ist.
- `local:` : Gibt an, dass der Name im **lokalen** Gültigkeitsbereich vorhanden ist. Der aktuelle Bereich ist immer der **lokale** Gültigkeitsbereich.
- `private:` : Gibt an, dass der Name **Privat** und nur für den aktuellen Gültigkeitsbereich sichtbar ist.
- `script:` : Gibt an, dass der Name im **Skript** Bereich vorhanden ist.
  Der **Skript** Bereich ist der nächste Bereich der Vorgänger Skriptdatei oder **Global** , wenn keine nächste Vorgänger Skriptdatei vorhanden ist.
- `using:`: Wird verwendet, um auf Variablen zuzugreifen, die in einem anderen Gültigkeitsbereich definiert sind, während Skripts über Cmdlets `Start-Job` wie `Invoke-Command`
- `workflow:` : Gibt an, dass der Name in einem Workflow vorhanden ist. Hinweis: Workflows werden in PowerShell Core nicht unterstützt.
- `<variable-namespace>` : Ein Modifizierer, der von einem PowerShell-PSDrive-Anbieter erstellt wurde.
  Beispiel:

  |  Namespace  |                    BESCHREIBUNG                     |
  | ----------- | -------------------------------------------------- |
  | `Alias:`    | Im aktuellen Bereich definierte Aliase               |
  | `Env:`      | Im aktuellen Bereich definierte Umgebungsvariablen |
  | `Function:` | Im aktuellen Bereich definierte Funktionen             |
  | `Variable:` | Im aktuellen Bereich definierte Variablen             |

Der Standardbereich für Skripts ist der Skript Bereich. Der Standardbereich für Funktionen und Aliase ist der lokale Gültigkeitsbereich, auch wenn Sie in einem Skript definiert sind.

### <a name="using-scope-modifiers"></a>Verwenden von Bereichs modifiziererbereichen

Um den Gültigkeitsbereich einer neuen Variablen, eines Alias oder einer neuen Funktion anzugeben, verwenden Sie einen bereichsmodifizierer.

Die Syntax für einen bereichsmodifizierer in einer Variablen lautet wie folgt:

```
$[<scope-modifier>:]<name> = <value>
```

Die Syntax für einen bereichsmodifizierer in einer Funktion ist wie folgt:

```
function [<scope-modifier>:]<name> {<function-body>}
```

Der folgende Befehl, der keinen bereichsmodifizierer verwendet, erstellt eine Variable im aktuellen oder **lokalen** Gültigkeitsbereich:

```powershell
$a = "one"
```

Um die gleiche Variable im **globalen** Gültigkeitsbereich zu erstellen, verwenden Sie den bereichsmodifizierer `global:` :

```powershell
$global:a = "one"
```

Um die gleiche Variable im **Skript** Bereich zu erstellen, verwenden Sie den bereichsmodifizierer `script:` :

```powershell
$script:a = "one"
```

Sie können auch einen bereichsmodifizierer mit Funktionen verwenden. Die folgende Funktionsdefinition erstellt eine Funktion im **globalen** Gültigkeitsbereich:

```powershell
function global:Hello {
  Write-Host "Hello, World"
}
```

Sie können auch Bereichs Modifizierer verwenden, um auf eine Variable in einem anderen Bereich zu verweisen.
Der folgende Befehl verweist auf die `$test` -Variable, zuerst im lokalen Gültigkeitsbereich und dann im globalen Gültigkeitsbereich:

```powershell
$test
$global:test
```

### <a name="the-using-scope-modifier"></a>Der bereichsmodifizierer `Using:`

Die Verwendung von ist ein spezieller bereichsmodifizierer, der eine lokale Variable in einem Remote Befehl identifiziert. Ohne einen-Modifizierer erwartet PowerShell, dass Variablen in Remote Befehlen in der Remote Sitzung definiert werden.

Der bereichsmodifizierer `Using` wird in PowerShell 3,0 eingeführt.

Für Skripts oder Befehle, die außerhalb der Sitzung ausgeführt werden, müssen Sie den bereichsmodifizierer `Using` zum Einbetten von Variablen Werten aus dem aufrufenden Sitzungs Bereich benötigen, damit der Sitzungscode darauf zugreifen kann. Der bereichsmodifizierer `Using` wird in den folgenden Kontexten unterstützt:

- Remote ausgeführte Befehle, gestartet mit mit `Invoke-Command` den Parametern **Computername** , **Hostname** , **SshConnection** oder **Session** (Remote Sitzung)
- Hintergrund Aufträge, gestartet mit `Start-Job` (Out-of-Process-Sitzung)
- Thread Aufträge, gestartet über `Start-ThreadJob` oder `ForEach-Object -Parallel` (separate Thread Sitzung)

Abhängig vom Kontext sind eingebettete Variablen Werte entweder unabhängige Kopien der Daten im Gültigkeitsbereich des Aufrufers oder Verweise darauf. In Remote-und Out-of-Process-Sitzungen sind Sie immer unabhängige Kopien.

Weitere Informationen finden Sie unter [about_Remote_Variables](about_Remote_Variables.md).

In Thread Sitzungen werden Sie als Verweis übermittelt. Dies bedeutet, dass es möglich ist, die Variablen für den aufrufbereich in einem anderen Thread zu ändern. Zum sicheren ändern von Variablen ist die Thread Synchronisierung erforderlich.

Weitere Informationen finden Sie unter:

- [Start-ThreadJob](xref:ThreadJob.Start-ThreadJob)
- [ForEach-Object](xref:Microsoft.PowerShell.Core.ForEach-Object)

#### <a name="serialization-of-variable-values"></a>Serialisierung von Variablen Werten

Remote ausgeführte Befehle und Hintergrund Aufträge werden außerhalb des Prozesses ausgeführt.
Out-of-Process-Sitzungen verwenden die XML-basierte Serialisierung und Deserialisierung, um die Werte der Variablen über die Prozess Grenzen hinweg verfügbar zu machen. Der Serialisierungsprozess konvertiert Objekte in ein **psobject** -Objekt, das die ursprünglichen Objekteigenschaften, aber nicht die zugehörigen Methoden enthält.

Bei einer begrenzten Menge von Typen werden Objekte von der Deserialisierung zurück auf den ursprünglichen Typ zurückgesetzt. Das rehydrierte Objekt ist eine Kopie der ursprünglichen Objektinstanz.
Es verfügt über die Typeigenschaften und-Methoden. Bei einfachen Typen, wie z. b **. System. Version** , ist die Kopie exakt. Bei komplexen Typen ist die Kopie nicht perfekt. Beispielsweise enthalten die von einem Zertifikat bereit erten Zertifikat Objekte nicht den privaten Schlüssel.

Instanzen aller anderen Typen sind **psobject** -Instanzen. Die **pstypames** -Eigenschaft enthält den ursprünglichen Typnamen, dem die **Deserialisierung** vorangestellt ist, z **. b.Deserialized.System. Data. datdatababel**

### <a name="the-allscope-option"></a>Die allscope-Option

Variablen und Aliase haben eine **options** -Eigenschaft, die den Wert **allscope** annehmen kann. Elemente, die die **allscope** -Eigenschaft aufweisen, werden Teil der von Ihnen erstellten untergeordneten Bereiche, obwohl Sie nicht rückwirkend von übergeordneten Bereichen geerbt werden.

Ein Element, das die **allscope** -Eigenschaft aufweist, wird im untergeordneten Bereich angezeigt und ist Teil dieses Bereichs. Änderungen am Element in einem beliebigen Gültigkeitsbereich betreffen alle Bereiche, in denen die Variable definiert ist.

### <a name="managing-scope"></a>Verwalten des Bereichs

Mehrere Cmdlets verfügen über einen **Scope** -Parameter, mit dem Sie Elemente in einem bestimmten Bereich erhalten oder festlegen können (erstellen und ändern). Verwenden Sie den folgenden Befehl, um alle Cmdlets in Ihrer Sitzung zu suchen, die einen **Scope** -Parameter aufweisen:

```powershell
Get-Help * -Parameter scope
```

Zum Ermitteln der Variablen, die in einem bestimmten Bereich sichtbar sind, verwenden Sie den- `Scope` Parameter von `Get-Variable` . Zu den sichtbaren Variablen zählen globale Variablen, Variablen im übergeordneten Bereich und Variablen im aktuellen Gültigkeitsbereich.

Beispielsweise ruft der folgende Befehl die Variablen ab, die im lokalen Gültigkeitsbereich sichtbar sind:

```powershell
Get-Variable -Scope local
```

Um eine Variable in einem bestimmten Bereich zu erstellen, verwenden Sie einen bereichsmodifizierer oder den **Scope** -Parameter von `Set-Variable` . Der folgende Befehl erstellt eine Variable im globalen Gültigkeitsbereich:

```powershell
New-Variable -Scope global -Name a -Value "One"
```

Sie können auch den Scope-Parameter der `New-Alias` `Set-Alias` Cmdlets, oder verwenden, `Get-Alias` um den Bereich anzugeben. Der folgende Befehl erstellt einen Alias im globalen Gültigkeitsbereich:

```powershell
New-Alias -Scope global -Name np -Value Notepad.exe
```

Um die Funktionen in einem bestimmten Bereich zu erhalten, verwenden `Get-Item` Sie das Cmdlet, wenn Sie sich im Bereich befinden. Das `Get-Item` Cmdlet weist keinen **Bereichs** Parameter auf.

> [!NOTE]
> Für die Cmdlets, die den **Scope** -Parameter verwenden, können Sie auch auf Bereiche nach Zahl verweisen. Die Zahl beschreibt die relative Position von einem Bereich zu einem anderen. Bereich 0 stellt den aktuellen Bereich (oder den lokalen Bereich) dar. Bereich 1 gibt den unmittelbar übergeordneten Bereich an. Bereich 2 gibt das übergeordnete Element des übergeordneten Bereichs an usw. Nummerierte Bereiche sind nützlich, wenn Sie viele rekursive Bereiche erstellt haben.

### <a name="using-dot-source-notation-with-scope"></a>Verwenden der Punkt Quell Notation mit dem Bereich

Skripts und Funktionen folgen allen Regeln des Gültigkeits Bereichs. Sie erstellen Sie in einem bestimmten Bereich und wirken sich nur auf diesen Bereich aus, es sei denn, Sie verwenden einen Cmdlet-Parameter oder einen bereichsmodifizierer, um diesen Bereich zu ändern.

Sie können jedoch dem aktuellen Bereich ein Skript oder eine Funktion hinzufügen, indem Sie die Punkt Quell Notation verwenden. Wenn ein Skript im aktuellen Bereich ausgeführt wird, sind alle Funktionen, Aliase und Variablen, die das Skript erstellt, im aktuellen Bereich verfügbar.

Um dem aktuellen Gültigkeitsbereich eine Funktion hinzuzufügen, geben Sie einen Punkt (.) und ein Leerzeichen vor dem Pfad und dem Namen der Funktion in den Funktions aufzurufen ein.

Um beispielsweise das Sample.ps1 Skript aus dem Verzeichnis "c:\Scripts" im Skript Bereich (Standard für Skripts) auszuführen, verwenden Sie den folgenden Befehl:

```powershell
c:\scripts\sample.ps1
```

Um das Sample.ps1 Skript im lokalen Gültigkeitsbereich auszuführen, verwenden Sie den folgenden Befehl:

```powershell
. c:\scripts.sample.ps1
```

Wenn Sie den calloperator (&) zum Ausführen einer Funktion oder eines Skripts verwenden, wird er dem aktuellen Bereich nicht hinzugefügt. Im folgenden Beispiel wird der-Operator aufgerufen:

```powershell
& c:\scripts.sample.ps1
```

Weitere Informationen zum calloperator finden Sie in [about_operators](about_operators.md).

Alle Aliase, Funktionen oder Variablen, die vom Sample.ps1 Skript erstellt werden, sind im aktuellen Bereich nicht verfügbar.

## <a name="restricting-without-scope"></a>Einschränken ohne Bereich

Einige PowerShell-Konzepte ähneln dem Bereich oder der Interaktion mit dem Bereich. Diese Konzepte können mit dem Bereich oder dem Verhalten des Bereichs verwechselt werden.

Sitzungen, Module und eingefügte Eingabe Aufforderungen sind eigenständige Umgebungen, aber Sie sind keine untergeordneten Bereiche des globalen Bereichs in der Sitzung.

### <a name="sessions"></a>Sitzungen

Eine Sitzung ist eine Umgebung, in der PowerShell ausgeführt wird. Wenn Sie eine Sitzung auf einem Remote Computer erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her. Mit der permanenten Verbindung können Sie die Sitzung für mehrere verwandte Befehle verwenden.

Da eine Sitzung eine eigenständige Umgebung ist, verfügt sie über einen eigenen Bereich, aber eine Sitzung ist kein untergeordneter Bereich der Sitzung, in der Sie erstellt wurde. Die Sitzung beginnt mit einem eigenen globalen Gültigkeitsbereich. Dieser Bereich ist unabhängig vom globalen Gültigkeitsbereich der Sitzung. Sie können untergeordnete Bereiche in der Sitzung erstellen. Beispielsweise können Sie ein-Skript ausführen, um einen untergeordneten Bereich in einer-Sitzung zu erstellen.

### <a name="modules"></a>Module

Sie können ein PowerShell-Modul verwenden, um PowerShell-Tools freizugeben und bereitzustellen. Ein Modul ist eine Einheit, die Cmdlets, Skripts, Funktionen, Variablen, Aliase und andere nützliche Elemente enthalten kann. Sofern nicht explizit definiert, kann nicht auf die Elemente in einem Modul außerhalb des Moduls zugegriffen werden. Aus diesem Grund können Sie das Modul der Sitzung hinzufügen und die öffentlichen Elemente verwenden, ohne zu befürchten, dass die anderen Elemente die Cmdlets, Skripts, Funktionen und andere Elemente in der Sitzung überschreiben können.

Module werden standardmäßig in die oberste Ebene des aktuellen _Sitzungs Zustands_ geladen, nicht im aktuellen _Bereich_. Der aktuelle Sitzungszustand kann ein Modul Sitzungs Status oder der globale Sitzungszustand sein. Durch das Hinzufügen eines Moduls zu einer Sitzung wird der Bereich nicht geändert. Wenn Sie sich im globalen Gültigkeitsbereich befinden, werden Module in den globalen Sitzungszustand geladen. Alle Exporte werden in die globalen Tabellen eingefügt.
Wenn Sie Module2 _innerhalb_ von Module1 laden, wird Module2 in den Sitzungszustand Module1 und nicht in den globalen Sitzungszustand geladen. Alle Exporte aus Module2 werden am Anfang des Module1-Sitzungs Zustands platziert. Wenn Sie verwenden `Import-Module -Scope local` , werden die Exporte in das aktuelle Bereichs Objekt und nicht auf der obersten Ebene platziert. Wenn Sie _ein Modul_ verwenden und `Import-Module -Scope global` (oder) verwenden, `Import-Module -Global` um ein anderes Modul zu laden, werden das Modul und die Exporte in den globalen Sitzungszustand geladen, anstatt in den lokalen Sitzungszustand des Moduls. Diese Funktion wurde für das Schreiben von Modulen entworfen, die Module manipulieren. Das **windowscompatibility** -Modul bewirkt, dass Proxy Module in den globalen Sitzungszustand importiert werden.

Innerhalb des Sitzungs Zustands haben Module einen eigenen Bereich. Beachten Sie das folgende Modul `C:\temp\mod1.psm1` :

```powershell
$a = "Hello"

function foo {
    "`$a = $a"
    "`$global:a = $global:a"
}
```

Nun erstellen wir eine globale Variable `$a` , legen ihr einen Wert zu und rufen die Funktion **foo** auf.

```powershell
$a = "Goodbye"
foo
```

Das Modul deklariert die Variable `$a` im Modul Bereich, dann gibt die Funktion **foo** den Wert der Variablen in beiden Bereichen aus.

```Output
$a = Hello
$global:a = Goodbye
```

### <a name="nested-prompts"></a>Aufforderungs Eingabe Aufforderungen

In der Liste von aufgefügten Eingabe Aufforderungen ist kein eigener Bereich vorhanden Wenn Sie eine Eingabeaufforderung eingeben, ist die eingefügte Eingabeaufforderung eine Teilmenge der Umgebung. Allerdings bleiben Sie im lokalen Gültigkeitsbereich.

Skripts haben einen eigenen Bereich. Wenn Sie ein Skript Debuggen und einen Haltepunkt im Skript erreichen, geben Sie den Skript Bereich ein.

### <a name="private-option"></a>Private Option

Aliase und Variablen verfügen über eine **Option** -Eigenschaft, die den Wert **private** annehmen kann. Elemente mit der Option **private** können in dem Bereich, in dem Sie erstellt werden, angezeigt und geändert werden. Sie können jedoch außerhalb dieses Bereichs nicht angezeigt oder geändert werden.

Wenn Sie z. b. eine Variable erstellen, die eine private-Option im globalen Gültigkeitsbereich hat, und dann ein Skript ausführen, `Get-Variable` zeigen die Befehle im Skript nicht die private Variable an. Durch die Verwendung des globalen bereichsmodifizierers in dieser Instanz wird die private Variable nicht angezeigt.

Sie können den Option-Parameter der `New-Variable` -, `Set-Variable` `New-Alias` -,-und- `Set-Alias` Cmdlets verwenden, um den Wert der Option-Eigenschaft auf "Privat" festzulegen.

### <a name="visibility"></a>Sichtbarkeit

Die **Visibility** -Eigenschaft einer Variablen oder eines Alias bestimmt, ob das Element außerhalb des Containers, in dem er erstellt wurde, angezeigt wird. Ein Container kann ein Modul, ein Skript oder ein Snap-in sein. Die Sichtbarkeit wurde für Container auf die gleiche Weise entworfen, wie der **private** Wert der **Option** -Eigenschaft für Bereiche vorgesehen ist.

Die **Visibility** -Eigenschaft übernimmt die Werte **Public** und **private** . Elemente mit privater Sichtbarkeit können nur in dem Container angezeigt und geändert werden, in dem Sie erstellt wurden. Wenn der Container hinzugefügt oder importiert wird, können die Elemente mit privater Sichtbarkeit nicht angezeigt oder geändert werden.

Da die Sichtbarkeit für Container konzipiert ist, funktioniert Sie in einem Bereich anders.

- Wenn Sie ein Element mit privater Sichtbarkeit im globalen Gültigkeitsbereich erstellen, können Sie das Element in keinem Bereich anzeigen oder ändern.
- Wenn Sie versuchen, den Wert einer Variablen anzuzeigen oder zu ändern, die über eine private Sichtbarkeit verfügt, gibt PowerShell eine Fehlermeldung zurück.

Sie können die `New-Variable` -und- `Set-Variable` Cmdlets verwenden, um eine Variable zu erstellen, die über private Sichtbarkeit verfügt.

## <a name="examples"></a>Beispiele

### <a name="example-1-change-a-variable-value-only-in-a-script"></a>Beispiel 1: Ändern eines Variablen Werts nur in einem Skript

Der folgende Befehl ändert den Wert der `$ConfirmPreference` Variablen in einem Skript. Die Änderung wirkt sich nicht auf den globalen Gültigkeitsbereich aus.

Verwenden Sie zuerst den folgenden Befehl, um den Wert der `$ConfirmPreference` Variablen im lokalen Gültigkeitsbereich anzuzeigen:

```
PS>  $ConfirmPreference
High
```

Erstellen Sie ein Scope.ps1 Skript, das die folgenden Befehle enthält:

```powershell
$ConfirmPreference = "Low"
"The value of `$ConfirmPreference is $ConfirmPreference."
```

Führen Sie das Skript aus. Das Skript ändert den Wert der `$ConfirmPreference` Variablen und meldet dann den Wert im Skript Bereich. Die Ausgabe sollte der folgenden Ausgabe ähneln:

```output
The value of $ConfirmPreference is Low.
```

Testen Sie als nächstes den aktuellen Wert der `$ConfirmPreference` Variablen im aktuellen Bereich.

```
PS>  $ConfirmPreference
High
```

Dieses Beispiel zeigt, dass sich Änderungen am Wert einer Variablen im Skript Bereich nicht auf den Wert der Variablen im übergeordneten Bereich auswirken.

### <a name="example-2-view-a-variable-value-in-different-scopes"></a>Beispiel 2: Anzeigen eines Variablen Werts in verschiedenen Bereichen

Sie können Bereichs Modifizierer verwenden, um den Wert einer Variablen im lokalen Gültigkeitsbereich und in einem übergeordneten Bereich anzuzeigen.

Definieren Sie zunächst eine `$test` Variable im globalen Gültigkeitsbereich.

```powershell
$test = "Global"
```

Erstellen Sie als nächstes ein Sample.ps1 Skript, das die `$test` Variable definiert. Verwenden Sie im Skript einen bereichsmodifizierer, um entweder auf die globale oder lokale Version der Variablen zu verweisen `$test` .

In Sample.ps1:

```powershell
$test = "Local"
"The local value of `$test is $test."
"The global value of `$test is $global:test."
```

Wenn Sie Sample.ps1 ausführen, sollte die Ausgabe der folgenden Ausgabe ähneln:

```output
The local value of $test is Local.
The global value of $test is Global.
```

Wenn das Skript beendet ist, wird nur der globale Wert von `$test` in der Sitzung definiert.

```
PS>  $test
Global
```

### <a name="example-3-change-the-value-of-a-variable-in-a-parent-scope"></a>Beispiel 3: Ändern des Werts einer Variablen in einem übergeordneten Bereich

Wenn Sie ein Element nicht mithilfe der Option "private" oder einer anderen Methode schützen, können Sie den Wert einer Variablen in einem übergeordneten Bereich anzeigen und ändern.

Definieren Sie zunächst eine `$test` Variable im globalen Gültigkeitsbereich.

```powershell
$test = "Global"
```

Erstellen Sie als nächstes ein Sample.ps1 Skript, das die `$test` Variable definiert. Verwenden Sie im Skript einen bereichsmodifizierer, um entweder auf die globale oder lokale Version der Variablen zu verweisen `$test` .

In Sample.ps1:

```powershell
$global:test = "Local"
"The global value of `$test is $global:test."
```

Wenn das Skript beendet ist, wird der globale Wert von `$test` geändert.

```
PS>  $test
Local
```

### <a name="example-4-creating-a-private-variable"></a>Beispiel 4: Erstellen einer privaten Variablen

Eine private Variable ist eine Variable, die eine **options** -Eigenschaft mit dem Wert *private* aufweist. *Private* Variablen werden vom untergeordneten Bereich geerbt, Sie können jedoch nur in dem Bereich angezeigt oder geändert werden, in dem Sie erstellt wurden.

Der folgende Befehl erstellt eine private Variable namens `$ptest` im lokalen Gültigkeitsbereich.

```powershell
New-Variable -Name ptest -Value 1 -Option private
```

Sie können den Wert von im lokalen Gültigkeitsbereich anzeigen und ändern `$ptest` .

```
PS>  $ptest
1

PS>  $ptest = 2
PS>  $ptest
2
```

Erstellen Sie als nächstes ein Sample.ps1 Skript, das die folgenden Befehle enthält. Der Befehl versucht, den Wert von anzuzeigen und zu ändern `$ptest` .

In Sample.ps1:

```powershell
"The value of `$Ptest is $Ptest."
"The value of `$Ptest is $global:Ptest."
```

Die `$ptest` Variable ist im Skript Bereich nicht sichtbar. die Ausgabe ist leer.

```powershell
"The value of $Ptest is ."
"The value of $Ptest is ."
```

### <a name="example-5-using-a-local-variable-in-a-remote-command"></a>Beispiel 5: Verwenden einer lokalen Variablen in einem Remote Befehl

Verwenden Sie den bereichsmodifizierer für Variablen in einem Remote Befehl, der in der lokalen Sitzung erstellt wurde `Using` . PowerShell geht davon aus, dass die Variablen in Remote Befehlen in der Remote Sitzung erstellt wurden.

Die Syntax ist:

```
$Using:<VariableName>
```

Die folgenden Befehle erstellen z. b. eine `$Cred` Variable in der lokalen Sitzung und verwenden anschließend die `$Cred` Variable in einem Remote Befehl:

```powershell
$Cred = Get-Credential
Invoke-Command $s {Remove-Item .\Test*.ps1 -Credential $Using:Cred}
```

Der Bereich Verwendung wurde in PowerShell 3,0 eingeführt. Verwenden Sie in PowerShell 2,0 das folgende Befehls Format, um anzugeben, dass eine Variable in der lokalen Sitzung erstellt wurde.

```powershell
$Cred = Get-Credential
Invoke-Command $s {
  param($c)
  Remove-Item .\Test*.ps1 -Credential $c
} -ArgumentList $Cred
```

## <a name="see-also"></a>Weitere Informationen:

[about_Variables](about_Variables.md)

[about_Environment_Variables](about_Environment_Variables.md)

[about_Functions](about_Functions.md)

[about_Script_Blocks](about_Script_Blocks.md)

[Start-ThreadJob](/powershell/module/ThreadJob/Start-ThreadJob)
