---
description: Die Umgebungsvariable psmodulepath enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_PSModulePath?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Grundlegendes zu PSModulePath
ms.openlocfilehash: 5d87f550b3aa8774ae81f68848d5aa252b2e5851
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524653"
---
# <a name="about-psmodulepath"></a>Informationen über psmodulepath

Die `$env:PSModulePath` Umgebungsvariable enthält eine Liste der Ordner Speicherorte, die durchsucht werden, um Module und Ressourcen zu finden. PowerShell durchsucht jeden Ordner rekursiv nach `.psd1` Modul `.psm1` Dateien (oder Dateien).

Standardmäßig sind die folgenden effektiven Speicherorte zugewiesen `$env:PSModulePath` :

- System weite Speicherorte: diese Ordner enthalten Module, die mit PowerShell ausgeliefert werden. Diese Module sind im Ordner gespeichert `$PSHOME\Modules` . Dies ist auch der Speicherort, an dem die Windows-Verwaltungs Module installiert sind.

- Vom Benutzer installierte Module: Dies sind Module, die vom Benutzer installiert werden.
  `Install-Module` verfügt über einen **Scope** -Parameter, mit dem Sie angeben können, ob das Modul für den aktuellen Benutzer oder für alle Benutzer installiert ist. Weitere Informationen finden Sie unter [Install-Module](xref:PowerShellGet.Install-Module).

  - Unter Windows ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME\Documents\PowerShell\Modules` Ordner. Der Speicherort des **ALLUSERS** -Bereichs ist `$env:ProgramFiles\PowerShell\Modules` .
  - Bei nicht-Windows-Systemen ist der Speicherort des benutzerspezifischen **CurrentUser** -Bereichs der `$HOME/.local/share/powershell/Modules` Ordner. Der Speicherort des **ALLUSERS** -Bereichs ist `/usr/local/share/powershell/Modules` .

Außerdem können Setup Programme, die Module in anderen Verzeichnissen installieren, z. b. das Verzeichnis "Programme", ihre Speicherorte an den Wert von anfügen `$env:PSModulePath` .

> [!NOTE]
> Unter Windows ist der benutzerspezifische Speicherort der `PowerShell\Modules` Ordner im Ordner " **Dokumente** " in Ihrem Benutzerprofil. Der spezifische Pfad dieses Standorts variiert je nach Version von Windows und ob Sie die Ordner Umleitung verwenden. Microsoft onedrive kann auch den Speicherort des Ordners " **Dokumente** " ändern. Sie können den Speicherort des Ordners " **Dokumente** " mithilfe des folgenden Befehls überprüfen: `[Environment]::GetFolderPath('MyDocuments')` .

## <a name="modifying-psmodulepath"></a>Ändern von psmodulepath

Um die Standardmodul Verzeichnisse für die aktuelle Sitzung zu ändern, verwenden Sie das folgende Befehls Format, um den Wert der `PSModulePath` Umgebungsvariablen zu ändern.

Wenn Sie z. b. das `C:\Program Files\Fabrikam\Modules` Verzeichnis dem Wert der psmodulepath-Umgebungsvariablen hinzufügen möchten, geben Sie Folgendes ein:

```powershell
$Env:PSModulePath = $Env:PSModulePath+";C:\Program Files\Fabrikam\Modules"
```

Das Semikolon ( `;` ) im Befehl trennt den neuen Pfad von dem Pfad, der in der Liste vorangestellt ist. Auf nicht-Windows-Plattformen trennt der Doppelpunkt ( `:` ) die Pfad Positionen in der Umgebungsvariablen.

Wenn Sie den Wert von `PSModulePath` in jeder Sitzung ändern möchten, fügen Sie den vorherigen Befehl zu Ihrem PowerShell-Profil hinzu, oder verwenden Sie die Methode "* **tenvironmentvariable** " der **Umgebungs** Klasse.

Der folgende Befehl verwendet die **GetEnvironmentVariable** -Methode, um die Computer Einstellung von `PSModulePath` und die Methode " **enumervironmentvariable** " zum Hinzufügen des `C:\Program Files\Fabrikam\Modules` Pfads zum Wert zu erhalten.

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'Machine')
```

Zum Hinzufügen eines Pfads zur Benutzereinstellung ändern Sie den Zielwert in **Benutzer**.

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'User')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'User')
```

Weitere Informationen zu den Methoden der **System. Environment** -Klasse finden Sie unter [Umgebungs Methoden](/dotnet/api/system.environment).

## <a name="powershell-psmodulepath-construction"></a>PowerShell psmodulepath-Konstruktion

Der Wert von `$env:PSModulePath` wird bei jedem Start von PowerShell erstellt.
Der Wert variiert je nach Version von PowerShell und dessen Start.

### <a name="windows-powershell-startup"></a>Windows PowerShell-Start

Windows PowerShell verwendet die folgende Logik, um `PSModulePath` beim Start zu erstellen:

- Wenn `PSModulePath` nicht vorhanden ist, kombinieren Sie **CurrentUser** , **ALLUSERS** und die `$PSHOME` Module-Pfade.
- Wenn `PSModulePath` vorhanden ist:
  - Wenn `PSModulePath` den `$PSHOME` Modulpfad enthält:
    - Der **ALLUSERS** -Modulpfad wird vor dem `$PSHOME` Modulpfad eingefügt.
  - woanders
    - Verwenden Sie einfach `PSModulePath` wie definiert, da der Benutzer den Speicherort absichtlich entfernt hat. `$PSHOME`

Der **CurrentUser** -Modulpfad wird nur vorangestellt, wenn der Benutzerbereich `$env:PSModulePath` nicht vorhanden ist. Andernfalls wird der Benutzerbereich `$env:PSModulePath` wie definiert verwendet.

### <a name="powershell-core-6-startup"></a>Starten von PowerShell Core 6

PowerShell Core 6 verwendet keinen Inhalt von, `$env:PSModulePath` Wenn er erkennt, dass er von PowerShell gestartet wurde. Sie überschreibt Sie mit:

- **CurrentUser** -Modulpfad + **ALLUSERS** Modulpfad + `$PSHOME` Modulpfad + Windows PowerShell- `$PSHOME` Modulpfad.

### <a name="powershell-7-startup"></a>PowerShell 7-Start

In Windows verwendet ein neuer Prozess bei den meisten Umgebungsvariablen nur dann diesen Wert, wenn die Variable im Benutzerbereich vorhanden ist, auch wenn eine Variable mit dem gleichen Namen vorhanden ist.

In PowerShell 7 `PSModulePath` wird ähnlich wie die `Path` Umgebungsvariable unter Windows behandelt. Unter Windows `Path` wird von anderen Umgebungsvariablen anders behandelt. Wenn ein Prozess gestartet wird, kombiniert Windows den Benutzer bezogenen Bereich `Path` mit dem Computerbereich `Path` .

- Abrufen des Benutzer bezogenen Bereichs `PSModulePath`
- Mit der vom Prozess geerbten `PSModulePath` Umgebungsvariablen vergleichen
  - Wenn derselbe:
    - Fügen Sie die **ALLUSERS** am `PSModulePath` Ende der Semantik der `Path` Umgebungsvariablen an.
    - Der Windows- `System32` Pfad stammt von dem definierten Computer `PSModulePath` und muss daher nicht explizit hinzugefügt werden.
  - Wenn dies anders ist, sollten Sie so behandeln, als ob der Benutzer es explizit geändert hat und **ALLUSERS**`PSModulePath`
- Präfix mit PS7 User, System und `$PSHOME` path in dieser Reihenfolge
  - Wenn `powershell.config.json` einen Benutzerbereich enthält `PSModulePath` , verwenden Sie diesen anstelle der Standardeinstellung für den Benutzer.
  - Wenn `powershell.config.json` ein Systembereich enthält `PSModulePath` , verwenden Sie diesen anstelle des standardmäßigen für das System.

UNIX-Systeme haben keine Trennung von Benutzer-und System Umgebungsvariablen.
`PSModulePath` wird geerbt, und die PS7-spezifischen Pfade haben das Präfix, wenn Sie nicht bereits definiert sind.

### <a name="starting-windows-powershell-from-powershell-7"></a>Starten von Windows PowerShell über PowerShell 7

In dieser Erläuterung bedeutet _Windows PowerShell_ sowohl `powershell.exe` als auch `powershell_ise.exe` .

Der Wert von `$env:PSModulePath` wird `WinPSModulePath` mit den folgenden Änderungen in kopiert:

- Remove PS7 the User Module Path
- Remove PS7 the System Module Path
- Remove PS7 der `$PSHOME` Modulpfad

Die PS7-Pfade werden entfernt, sodass PS7-Module nicht in Windows PowerShell geladen werden. Der `WinPSModulePath` Wert wird beim Starten von Windows PowerShell verwendet.

### <a name="starting-powershell-7-from-windows-powershell"></a>Starten von PowerShell 7 über Windows PowerShell

Der Start von PowerShell 7 wird unverändert fortgesetzt, und es werden die von Windows PowerShell hinzugefügten Pfade geerbt. Da die PS7-spezifischen Pfade mit einem Präfix versehen sind, gibt es kein funktionales Problem.

### <a name="starting-powershell-6-from-powershell-7"></a>Starten von PowerShell 6 von PowerShell 7

PowerShell Core 6 überschreibt `$env:PSModulePath` . Es werden keine Änderungen vorgenommen.

### <a name="starting-powershell-7-from-powershell-6"></a>Starten von PowerShell 7 von PowerShell 6

Der Start von PowerShell 7 wird unverändert fortgesetzt, und es werden die von PowerShell Core 6 hinzugefügten Pfade geerbt. Da die PS7-spezifischen Pfade mit einem Präfix versehen sind, gibt es kein funktionales Problem.

## <a name="module-search-behavior"></a>Modul Suchverhalten

PowerShell durchsucht rekursiv jeden Ordner in " **psmodulepath** " nach Modul `.psd1` Dateien (oder `.psm1` Dateien). Dieses Suchmuster ermöglicht das Installieren mehrerer Versionen desselben Moduls in verschiedenen Ordnern. Zum Beispiel:

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules\PowerShellGet

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----           8/14/2020  5:56 PM                1.0.0.1
d----           9/13/2019  3:53 PM                2.1.2
```

Standardmäßig lädt PowerShell die höchste Versionsnummer eines Moduls, wenn mehrere Versionen gefunden werden. Verwenden Sie zum Laden einer bestimmten Version `Import-Module` mit dem **FullyQualifiedName** -Parameter. Weitere Informationen finden Sie unter [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).

## <a name="see-also"></a>Siehe auch

- [about_Modules](about_Modules.md)
- [Umgebungs Methoden](/dotnet/api/system.environment)
