---
ms.date: 07/28/2020
keywords: powershell,cmdlet
title: Arbeiten mit Dateien, Ordnern und Registrierungsschlüsseln
description: In diesem Artikel wird erörtert, wie Sie in PowerShell mit Änderungsaufgaben an Registrierungsschlüsseln umgehen.
ms.openlocfilehash: 6f653c1fb409a238aa05658e89261a12e96f6fe1
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92499976"
---
# <a name="working-with-files-folders-and-registry-keys"></a>Arbeiten mit Dateien, Ordnern und Registrierungsschlüsseln

Windows PowerShell verwendet das Nomen **Item** zum Verweisen auf Elemente in einem Windows PowerShell-Laufwerk.
Im Zusammenhang mit dem Windows PowerShell FileSystem-Anbieter kann ein **Item** eine Datei, ein Ordner oder das Windows PowerShell-Laufwerk sein. Das Auflisten dieser Elemente und die Arbeiten damit ist in den meisten Verwaltungseinstellungen eine wichtige grundlegende Aufgabe. Daher sollen diese Aufgaben ausführlich erläutert werden.

## <a name="enumerating-files-folders-and-registry-keys-get-childitem"></a>Auflisten von Dateien, Ordnern und Registrierungsschlüsseln (Get-ChildItem)

Da das Abrufen einer Sammlung von Elementen von einem bestimmten Standort eine sehr häufige Aufgabe ist, wurde das Cmdlet `Get-ChildItem` speziell dafür entwickelt, alle in einem Container, z. B. einem Ordner, gefundenen Elemente zurückzugeben.

Wenn Sie alle Dateien und Ordner zurückgeben möchten, die direkt im Ordner „C:\\Windows“ enthalten sind, geben Sie Folgendes ein:

```
PS> Get-ChildItem -Path C:\Windows
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-16   8:10 AM          0 0.log
-a---        2005-11-29   3:16 PM         97 acc1.txt
-a---        2005-10-23  11:21 PM       3848 actsetup.log
...
```

Die Auflistung gleicht der Ausgabe nach Eingabe des Befehls `dir` in **Cmd.exe** oder des Befehls `ls` in einer UNIX-Befehlsshell.

Sie können unter Verwendung der Parameter des Cmdlets `Get-ChildItem` sehr komplexe Sammlungen erstellen. Wir werden als Nächstes einige Szenarien näher betrachten. Sie können die Syntax des Cmdlets `Get-ChildItem` anzeigen, indem Sie Folgendes eingeben:

```powershell
Get-Command -Name Get-ChildItem -Syntax
```

Diese Parameter können gemischt und angepasst werden, um eine stark angepasste Ausgabe zu erhalten.

### <a name="listing-all-contained-items--recurse"></a>Auflisten aller enthaltenen Elemente (-Recurse)

Verwenden Sie den Parameter **Recurse** von `Get-ChildItem`, um sowohl die Elemente in einem Windows-Ordner als auch alle in dessen Unterordnern enthaltenen Elemente anzuzeigen. Die Auflistung zeigt alles, was im Windows-Ordner enthalten ist, und alle Elemente in seinen Unterordnern an. Beispiel:

```
PS> Get-ChildItem -Path C:\WINDOWS -Recurse

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS\AppPatch
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM    1852416 AcGenral.dll
...
```

### <a name="filtering-items-by-name--name"></a>Filtern von Elementen anhand des Namens (-Name)

Verwenden Sie den Parameter **Name** von `Get-Childitem`, um nur die Elementnamen anzuzeigen:

```
PS> Get-ChildItem -Path C:\WINDOWS -Name
addins
AppPatch
assembly
...
```

### <a name="forcibly-listing-hidden-items--force"></a>Erzwungenes Auflisten von ausgeblendeten Elementen (-Force)

Elemente, die normalerweise im Datei-Explorer oder in „Cmd.exe“ nicht sichtbar sind, werden in der Ausgabe des Befehls `Get-ChildItem` nicht angezeigt. Verwenden Sie den Parameter **Force** von `Get-ChildItem`, um ausgeblendete Elemente anzuzeigen.
Beispiel:

```powershell
Get-ChildItem -Path C:\Windows -Force
```

Dieser Parameter heißt „Force“ (Erzwingen), weil Sie mit ihm erzwingen können, dass das normale Verhalten des Befehls `Get-ChildItem` außer Kraft gesetzt wird. „Force“ ist ein weit verbreiteter Parameter, der eine Aktion erzwingt, die ein Cmdlet normalerweise nicht ausführen würde. Allerdings wird keine Aktion ausgeführt, die die Sicherheit des Systems gefährden würde.

### <a name="matching-item-names-with-wildcards"></a>Abgleichen von Elementnamen mit Platzhaltern

Der Befehl `Get-ChildItem` akzeptiert Platzhalter im Pfad der aufzulistenden Elemente.

Da das Abgleichen von Platzhaltern von der Windows PowerShell-Engine durchgeführt wird, verwenden alle Cmdlets, die Platzhalter akzeptieren, die gleiche Notation und das gleiche Abgleichverhalten. Die Windows PowerShell-Notation für Platzhalter enthält Folgendes:

- Das Sternchen (`*`) steht für null oder mehr beliebige Zeichen.

- Das Fragezeichen (`?`) steht für genau ein Zeichen.

- Die linke eckige Klammer (`[`) und die rechte eckige Klammer (`]`) umgeben eine Gruppe von Zeichen, die für den Abgleich verwendet werden soll.

Hier sind einige Beispiele für die Funktionsweise der Platzhalterspezifikation.

Geben Sie den folgenden Befehl ein, um im Windows-Verzeichnis alle Dateien mit dem Suffix `.log` und genau fünf Zeichen im Basisnamen zu suchen:

```
PS> Get-ChildItem -Path C:\Windows\?????.log

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
...
-a---        2006-05-11   6:31 PM     204276 ocgen.log
-a---        2006-05-11   6:31 PM      22365 ocmsn.log
...
-a---        2005-11-11   4:55 AM         64 setup.log
-a---        2005-12-15   2:24 PM      17719 VxSDM.log
...
```

Geben Sie Folgendes ein, um im Windows-Verzeichnis alle Dateien zu suchen, die mit dem Buchstaben `x` beginnen:

```powershell
Get-ChildItem -Path C:\Windows\x*
```

Geben Sie Folgendes ein, um alle Dateien zu suchen, deren Name mit „x“ oder „z“ beginnt:

```powershell
Get-ChildItem -Path C:\Windows\[xz]*
```

Weitere Informationen zu Platzhaltern finden Sie unter [about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards).

### <a name="excluding-items--exclude"></a>Ausschließen von Elementen (-Exclude)

Mithilfe des Parameters **Exclude** von `Get-ChildItem` können Sie bestimmte Elemente ausschließen. Auf diese Weise können Sie eine komplexe Filterung in einer einzigen Anweisung durchführen.

Angenommen, Sie möchten etwa die Windows Time Service-DLL im Ordner **System32** suchen. Sie können sich jedoch nur daran erinnern, dass der Name der DLL mit „W“ beginnt und „32“ enthält.

Mit einem Ausdruck wie `w*32*.dll` finden Sie alle DLLs, die die Bedingungen erfüllen. Sie sollten jedoch weitere Dateien herausfiltern, nämlich alle Win32-Dateien. Mithilfe des Parameters **Exclude** mit dem Muster `win*` können Sie diese Dateien herausfiltern:

```
PS> Get-ChildItem -Path C:\WINDOWS\System32\w*32*.dll -Exclude win*

    Directory: C:\WINDOWS\System32

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           3/18/2019  9:43 PM         495616 w32time.dll
-a---           3/18/2019  9:44 PM          35328 w32topl.dll
-a---           1/24/2020  5:44 PM         401920 Wldap32.dll
-a---          10/10/2019  5:40 PM         442704 ws2_32.dll
-a---           3/18/2019  9:44 PM          66048 wsnmp32.dll
-a---           3/18/2019  9:44 PM          18944 wsock32.dll
-a---           3/18/2019  9:44 PM          64792 wtsapi32.dll
```

### <a name="mixing-get-childitem-parameters"></a>Kombinieren von Get-ChildItem-Parametern

Sie können verschiedene Parameter des Cmdlets `Get-ChildItem` im gleichen Befehl verwenden. Bevor Sie Parameter kombinieren, sollten Sie sicher sein, dass Sie das Abgleichen mit Platzhalterzeichen verstanden haben. Beispielsweise gibt der folgende Befehl keine Ergebnisse zurück:

```powershell
Get-ChildItem -Path C:\Windows\*.dll -Recurse -Exclude [a-y]*.dll
```

Es werden keine Ergebnisse zurückgegeben, obwohl es im Windows-Ordner zwei DLLs gibt, die mit dem Buchstaben „z“ beginnen.

Es wurden keine Ergebnisse zurückgegeben, weil das Platzhalterzeichen als Teil des Pfads angegeben wurde. Obwohl der Befehl rekursiv war, hat das Cmdlet `Get-ChildItem` die Elemente im Windows-Ordner auf diejenigen beschränkt, deren Name mit `.dll` endet.

Mithilfe des Parameters **Include** können Sie eine rekursive Suche nach Dateien angeben, deren Name einem bestimmten Muster entspricht.

```
PS> Get-ChildItem -Path C:\Windows -Include *.dll -Recurse -Exclude [a-y]*.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32\Setup

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM       8261 zoneoc.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM     337920 zipfldr.dll
```
