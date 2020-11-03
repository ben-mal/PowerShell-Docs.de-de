---
description: Beschreibt die neuen Features, die in Windows PowerShell 5,1 enthalten sind.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/17/2018
online version: https://docs.microsoft.com/powershell/module/?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_5.1
ms.openlocfilehash: 567af048dd137c0287c6eba4ccc42a77055c0c92
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224908"
---
# <a name="about_windows_powershell_51"></a>about_Windows_PowerShell_5.1

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt die neuen Features, die in Windows PowerShell 5,1 enthalten sind.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Windows PowerShell 5,1 umfasst wichtige neue Features, die die Verwendungsmöglichkeiten erweitern, die Benutzerfreundlichkeit verbessern und es Ihnen ermöglichen, die Steuerung und Verwaltung von Windows-basierten Umgebungen leichter und umfassender zu steuern.

Windows PowerShell 5,1 ist abwärts kompatibel. Cmdlets, Anbieter, Module, Snap-Ins, Skripts, Funktionen und Profile, die für Windows PowerShell 4,0, Windows PowerShell 3,0 und Windows PowerShell 2,0 entwickelt wurden, funktionieren im Allgemeinen ohne Änderungen in Windows PowerShell 5,1.

- Neue Cmdlets: lokale Benutzer und Gruppen; Get-ComputerInfo
- PowerShellGet-Verbesserungen wie z. B. die Durchsetzung von signierten Modulen und die Installation von JEA-Modulen
- Bei PackageManagement wurde Unterstützung für Container, CBS-Setup, EXE-basiertes Setup und CAB-Pakete hinzugefügt
- Debuggingverbesserungen für DSC und PowerShell-Klassen
- Sicherheitsverbesserungen wie u. a. die Durchsetzung von katalogsignierten Modulen vom Pullserver und bei Verwendung von PowerShellGet-Cmdlets
- Antworten auf verschiedene Benutzeranfragen und zu Problemen

Windows PowerShell 5,1 wird standardmäßig unter Windows Server 2016 und Windows 10 installiert. Informationen zum Installieren von Windows PowerShell 5,1 unter Windows Server 2012 R2, Windows 8.1 Enterprise oder Windows 8.1 pro finden Sie unter [Installieren und Konfigurieren von WMF 5,1](/powershell/scripting/wmf/setup/install-configure).
Achten Sie darauf, dass Sie die Download Details lesen und alle Systemanforderungen erfüllen, bevor Sie Windows Management Framework 5,1 installieren.

Weitere Informationen zu Änderungen an Windows PowerShell 5,1 finden Sie unter [Neuerungen in Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).

## <a name="new-scenarios-and-features-in-wmf-51"></a>Neue Szenarios und Features in WMF 5.1

> Hinweis: Diese Dokumentation ist vorläufig und kann geändert werden.

### <a name="powershell-editions"></a>PowerShell-Editionen
Ab Version 5.1 ist PowerShell in verschiedenen Editionen verfügbar, die unterschiedliche Funktionen mitbringen und zu unterschiedlichen Plattformen kompatibel sind.

- **Desktop-Edition:** Diese Edition basiert auf .NET Framework und bietet Kompatibilität mit PowerShell-Versionen, die auf Skripts und Module abzielen und unter vollwertigen Editionen von Windows ausgeführt werden, z. B. Server Core und Windows Desktop.
- **Core-Edition:** Diese Edition basiert auf .NET Core und bietet Kompatibilität mit Skripts und Modulen für Versionen von PowerShell, die unter funktionsreduzierten Versionen von Windows wie Nano Server und Windows IoT ausgeführt werden.

**Weitere Informationen zur Verwendung von PowerShell-Editionen**

- [Determine running edition of PowerShell using $PSVersionTable (Bestimmen der ausgeführten Edition von PowerShell mit $PSVersionTable)](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [Filter Get-Module results by CompatiblePSEditions using PSEdition parameter (Filtern von Get-Module-Ergebnissen nach CompatiblePSEditions mithilfe des PSEdition-Parameters)](/powershell/module/microsoft.powershell.core/get-module)
- [Verhindern der Ausführung von Skripts außer bei Ausführung in einer kompatiblen Edition von PowerShell](/powershell/scripting/gallery/concepts/script-psedition-support)
- [Deklarieren der Kompatibilität eines Moduls mit bestimmten Versionen von PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a>Katalog-Cmdlets

Dem [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640))-Modul wurden zwei neue Cmdlets hinzugefügt, die Windows-Katalogdateien generieren und überprüfen.

#### <a name="new-filecatalog"></a>New-FileCatalog

„New-FileCatalog“ erstellt eine Windows-Katalogdatei für eine Gruppe von Ordnern und Dateien.
Diese Katalogdatei enthält die Hashes aller Dateien in bestimmten Pfaden. Benutzer können den Satz von Ordnern zusammen mit den entsprechenden Katalogdateien verteilen, die diese Ordner darstellen. Diese Informationen helfen bei der Überprüfung, ob seit der Erstellung des Katalogs Änderungen an den Ordnern vorgenommen wurden.

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

Die Katalogversionen 1 und 2 werden unterstützt. Version 1 verwendet den SHA1-Hashalgorithmus, um Dateihashes zu erstellen, Version 2 verwendet SHA256. Katalogversion 2 wird weder auf *Windows Server 2008 R2* noch auf *Windows 7* unterstützt. Daher sollten Sie die Katalogversion 2 mit *Windows 8* , *Windows Server 2012* und späteren Betriebssystemen verwenden.

Melden Sie sich mit dem Cmdlet [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) an, um die Integrität der Katalogdatei zu überprüfen (im obigen Beispiel: „pester.cat“).

#### <a name="test-filecatalog"></a>Test-FileCatalog

„Test-FileCatalog“ überprüft den Katalog, der einen Satz von Ordnern darstellt.

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

Dieses Cmdlet vergleicht alle Dateihashes und deren im *Katalog* enthaltenen relativen Pfade mit denen auf dem *Datenträger*. Wenn das Cmdlet eine Unstimmigkeit zwischen den Dateihashes und den Pfaden entdeckt, gibt es den Status *ValidationFailed* zurück. Benutzer können alle diese Informationen mithilfe des Parameters *-Detailed* abrufen. Dieser Parameter zeigt in der Eigenschaft *Signature* auch den Signierstatus des Katalogs an, was dem Aufruf des Cmdlets [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) in der Katalogdatei entspricht. Benutzer können außerdem jede Datei während der Überprüfung mithilfe des Parameters *-FilesToSkip* überspringen.

### <a name="module-analysis-cache"></a>Die Datei „ModuleAnalysisCache“

Ab Version 5.1 bietet PowerShell Kontrolle über die Datei, die zum Zwischenspeichern von Daten zu einem Modul verwendet wird, z. B. der Befehle, die es exportiert.

Standardmäßig wird dieser Cache in der Datei `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` gespeichert. Der Cache wird in der Regel beim Start der Suche nach einem Befehl gelesen und einige Zeit nach dem Import des Moduls in einem Hintergrundthread geschrieben.

Um den Standardspeicherort des Caches zu ändern, legen Sie die Umgebungsvariable `$env:PSModuleAnalysisCachePath` vor dem Starten von PowerShell fest. Änderungen an dieser Umgebungsvariablen betreffen nur untergeordnete Prozesse. Der Wert muss einen vollständigen Pfad (samt Dateiname) definieren, in dem PowerShell die Berechtigung zum Erstellen und Schreiben von Dateien hat. Zum Deaktivieren des Dateicaches kann dieser Wert auf einen ungültigen Speicherort festgelegt werden. Beispiel:

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

Hiermit wird der Pfad auf ein ungültiges Gerät festgelegt. Wenn PowerShell nicht in den Pfad schreiben kann, wird keine Fehlermeldung zurückgegeben. Mithilfe eines Ablaufverfolgungstools können Sie jedoch einen Fehlerbericht anzeigen:

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

Bei der Ausgabe aus dem Cache sucht PowerShell nach Modulen, die nicht mehr vorhanden sind, um einen unnötig großen Cache zu vermeiden. Mitunter sind diese Überprüfungen nicht wünschenswert, weshalb Sie sie deaktivieren können, indem Sie Folgendes festlegen:

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

Das Festlegen dieser Umgebungsvariablen wird im aktuellen Prozess sofort wirksam.

### <a name="specifying-module-version"></a>Angeben der Modulversion

In WMF 5.1 verhält sich `using module` genauso wie andere modulbezogene Konstruktionen in PowerShell. Zuvor gab es keine Möglichkeit, eine bestimmte Modulversion anzugeben. Wenn mehrere Versionen vorhanden waren, führte dies zu einem Fehler.

In WMF 5.1:

* Sie können den [Konstruktor „ModuleSpecification“ (Hashtabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor) verwenden.
  Diese Hashtabelle hat das gleiche Format wie `Get-Module -FullyQualifiedName`.

  **Beispiel:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

* Wenn mehrere Versionen des Moduls vorhanden sind, verwendet PowerShell **dieselbe Auflösungslogik** wie `Import-Module` und gibt keinen Fehler zurück, was dem Verhalten von `Import-Module` und `Import-DscResource` entspricht.

### <a name="improvements-to-pester"></a>Verbesserungen an Pester

In WMF 5,1 wurde die im Lieferumfang von PowerShell enthaltene Version von Pester von 3.3.5 auf 3.4.0 aktualisiert, mit dem Hinzufügen von GitHub [PR # 484](https://github.com/pester/Pester/pull/484), was ein besseres Verhalten für Pester auf Nano Server ermöglicht.

Überprüfen Sie die Veränderungen in Version 3.4.0 im Vergleich zu Version 3.3.5 durch Untersuchen der ChangeLog.md-Datei unter: https://github.com/pester/Pester/blob/master/CHANGELOG.md

## <a name="keywords"></a>Keywords

Neues in Windows PowerShell 5,1
