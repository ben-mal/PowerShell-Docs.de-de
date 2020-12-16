---
title: Neuerungen in PowerShell 7.1
description: In PowerShell 7.1 veröffentlichte neue Features und Änderungen
ms.date: 11/11/2020
ms.openlocfilehash: 5596d3ca69f5d8ea47f01ff0915e6fa33c1c463f
ms.sourcegitcommit: fb1a4bc4b249afd3513663de2e1ba3025d63467e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "94625719"
---
# <a name="whats-new-in-powershell-71"></a>Neuerungen in PowerShell 7.1

PowerShell 7.1 ist eine plattformübergreifende (Windows, macOS und Linux) Open-Source-Edition von PowerShell, die zur Verwaltung heterogener Umgebungen und Hybrid Clouds entwickelt wurde.

Aufbauend auf den in PowerShell 7.0 geschaffenen Grundlagen konzentrierten sich unsere Bemühungen auf in der Community gemeldete Issues und umfassen eine Reihe von Verbesserungen und Korrekturen. Wir engagieren uns dafür, dass PowerShell auch weiterhin eine stabile und leistungsstarke Plattform bleibt.

Zu PowerShell 7.1 gehört auch PSReadLine 2.1.0. Diese Version enthält Predictive IntelliSense. Weitere Informationen zum Feature Predictive IntelliSense finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/).

## <a name="where-can-i-install-powershell"></a>Wo kann ich PowerShell installieren?

<!-- TODO: Update list of OS below - make sure this is consistent across all docs -->

PowerShell 7.1 unterstützt derzeit die folgenden x64-Betriebssysteme:

- Windows 8.1/10 (einschließlich ARM64)
- Windows Server 2012 R2, 2016, 2019 und halbjährlicher Kanal
- Ubuntu 16.04/18.04/20.04 (einschließlich ARM64)
- Ubuntu 19.10 (über Snap-Pakete)
- Debian 9/10
- CentOS und RHEL 7/8
- Fedora 32
- Alpine ab 3.11 (einschließlich ARM64)
- macOS ab 10.13

Wir bieten auch Support über die Community für:

- Arch Linux
- Raspbian Linux
- Kali Linux

Weitere aktuelle Informationen zu unterstützten Betriebssystemen und zum Supportlebenszyklus finden Sie unter [PowerShell-Supportlebenszyklus](/powershell/scripting/powershell-support-lifecycle).

PowerShell 7.1 wurde im Microsoft Store veröffentlicht. Die PowerShell-Version finden Sie auf der Website von [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) oder in der Store-Anwendung unter Windows.

Vorteile des Microsoft Store-Pakets:

- Direkt in Windows 10 integrierte automatische Updates
- Integration in andere Softwareverteilungsmechanismen wie Intune und SCCM

> [!NOTE]
> Alle in `$PSHOME` gespeicherten Konfigurationseinstellungen auf Systemebene lassen sich nicht ändern. Dies schließt die WSMAN-Konfiguration ein. Dadurch wird verhindert, dass Remotesitzungen eine Verbindung mit auf Store basierenden Installationen von PowerShell herstellen. Konfigurationen auf Benutzerebene und SSH-Remoting werden unterstützt.

Prüfen Sie die Installationsanweisungen für Ihr bevorzugtes Betriebssystem:

- [Windows](/powershell/scripting/install/installing-powershell-core-on-windows)
- [macOS](/powershell/scripting/install/installing-powershell-core-on-macos)
- [Linux](/powershell/scripting/install/installing-powershell-core-on-linux)

Darüber hinaus unterstützt PowerShell 7.1 die ARM32- und ARM64-Varianten von Debian, Ubuntu und ARM64 Alpine Linux.

Wenngleich nicht offiziell unterstützt, hat die Community auch Pakete für [Arch](https://aur.archlinux.org/packages/powershell/) und Kali Linux bereitgestellt.

> [!NOTE]
> Debian ab Version 10, CentOS ab Version 8, Ubuntu 20.04, Alpine und ARM unterstützen WinRM-Remoting zurzeit nicht. Einzelheiten zum Einrichten von SSH-basiertem Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## <a name="running-powershell-71"></a>Ausführen von PowerShell 7.1

PowerShell 7.1 wird in ein neues Verzeichnis installiert und parallel mit Windows PowerShell 5.1 ausgeführt.
PowerShell 7.1 ist ein direktes Upgrade, das PowerShell 6.x. oder PowerShell 7.0 ersetzt.

- PowerShell 7.1 wird in `%programfiles%\PowerShell\7` installiert.
- Der Ordner `%programfiles%\PowerShell\7` wird `$env:PATH` hinzugefügt.

Das Installationsprogramm von PowerShell 7.1 aktualisiert frühere Versionen von PowerShell Core 6.x:

- PowerShell Core 6. x unter Windows: `%programfiles%\PowerShell\6` wird durch `%programfiles%\PowerShell\7` ersetzt.
- Linux: `/opt/microsoft/powershell/6` wird durch `/opt/microsoft/powershell/7` ersetzt.
- macOS: `/usr/local/microsoft/powershell/6` wird durch `/usr/local/microsoft/powershell/7` ersetzt.

> [!NOTE]
> In Windows PowerShell heißt die ausführbare Datei zum Starten von PowerShell `powershell.exe`. Ab Version 6 wurde die ausführbare Datei so geändert, dass die parallele Ausführung unterstützt wird. Die neue ausführbare Datei zum Starten von PowerShell 7.1 ist `pwsh.exe`. Vorschaubuilds bleiben als `pwsh-preview` anstelle von `pwsh` im Verzeichnis „7-preview“ erhalten.

## <a name="breaking-changes-and-improvements"></a>Breaking Changes und Verbesserungen

Die neuesten Informationen zu Änderungen und Verbesserungen finden Sie im GitHub-Repository unter [CHANGELOG](https://github.com/PowerShell/PowerShell/tree/master/CHANGELOG).

### <a name="breaking-changes"></a>Breaking Changes

<!-- TODO: Add descriptions for each breaking change - this might need to be a separate article that we link to -->

- Korrektur `$?` darf nicht `$false` sein, wenn der native Befehl in `stderr` schreibt (#13395)
- `-FromUnixTime` für `Get-Date` in `-UnixTimeSeconds` umbenannt, um die UNIX-Zeiteingabe zuzulassen (#13084) (vielen Dank an @aetos382!)
- Veranlassen, dass `$ErrorActionPreference` sich nicht auf die `stderr`-Ausgabe nativer Befehle auswirkt (#13361)
- Explizit angegebenem benannten Parameter erlauben, denselben über das Splatting von Hashtabellen zu ersetzen (#13162)
- Den Switch-Parameter `-Qualifier` für `Split-Path` nicht positionell gestalten (#12960) (vielen Dank an @yecril71pl!)
- Das Arbeitsverzeichnis als Literalpfad für `Start-Process` auflösen, wenn es nicht angegeben wird (#11946) (vielen Dank an @NoMoreFood!)
- Den Parameter `-OutFile` in Web-Cmdlets so wie `-LiteralPath` funktionieren lassen (#11701) (vielen Dank an @iSazonov!)
- Korrektur der Bindung von Zeichenfolgenparametern für numerische Literale des Typs `BigInteger`(#11634) (vielen Dank an @vexx32!)
- Unter Windows wird mit `Start-Process` eine Prozessumgebung mit allen Umgebungsvariablen der aktuellen Sitzung erstellt, wobei mit `-UseNewEnvironment` eine neue Standardprozessumgebung geschaffen wird (#10830) (vielen Dank an @iSazonov!)
- Zurückgegebenes Ergebnis nicht in `PSObject` umgebrochen, wenn ScriptBlock in „delegate“ konvertiert wird (#10619)
- Für den Operator `-replace` die Zeichenfolgenkonvertierung für invariante Kultur verwenden (#10954) (vielen Dank an @iSazonov!)

### <a name="experimental-features"></a>Experimentelle Features

Weitere Informationen zu den experimentellen Features finden Sie unter [Verwenden experimenteller Features](../learn/experimental-features.md).

- Feature `PSNullConditionalOperators` aus experimenteller Phase verschoben (#13529)
- Feature `PSUnixFileStat` aus experimenteller Phase verschoben
- Parameter `-Runspace` allen `*-PSBreakpoint`-Cmdlets hinzugefügt (#10492) (vielen Dank an @KirkMunro!)
- `PSNativePSPathResolution` hinzugefügt, um die Übergabe von `PSPath` an native Befehle zu unterstützen (#12386)
- Für den Operator `-replace` die Zeichenfolgenkonvertierung für invariante Kultur verwenden (#10954) (vielen Dank an @iSazonov!)
- `PSSubsystemPluginModel` hinzugefügt, um künftige Predictive IntelliSense-Plug-Ins zu unterstützen

### <a name="general-cmdlet-updates-and-fixes"></a>Allgemeine Cmdlet-Updates und -Korrekturen

- Warnung ausgeben, wenn `ConvertTo-Json` den Wert `-Depth` überschreitet (#13692)
- Den Fall korrigieren, wenn die Ausnahmemeldung unter Windows nur ``"`n"`` enthält (#13684)
- `CONOUT$` und `CONIN$` als reservierte Gerätenamen erkennen (#13508) (vielen Dank an @davidreis97!)
- `ConciseView` für interaktive erweiterte Funktion beim Schreiben des Fehlers korrigiert (#13623)
- Unterstützung für `TLS` 1.3 in Web-Cmdlets hinzugefügt (#13409) (vielen Dank an @iSazonov!)
- Prüfung auf NULL für `args` in `CommandLineParser` hinzugefügt (#13451) (vielen Dank an @iSazonov!)
- Neuanalysepunkte für Microsoft Store-Anwendungen verarbeitet (#13481) (vielen Dank an @iSazonov!)
- Feld verwenden, sofern die Eigenschaft für `ObRoot` nicht vorhanden ist, wenn PowerShell Direct für Container verwendet wird (#13375) (vielen Dank an @hemisphera!)
- Veraltete Warnungen zu `UTF-7` unterdrückt (#13484)
- Mehrerer Enumerationen einer Instanz von `IEnumerable<Expression>` in `Compiler.cs` vermieden (#13491)
- `Add-Type -OutputType` so ändern, dass `ConsoleApplication` und `WindowsApplication` nicht unterstützt werden (#13440)
- Warnungen erstellen, wenn `UTF-7` als Codierung angegeben wird (#13430)
- Fehlermeldung bei fehlendem Ziel für neue symbolische Verknüpfung korrigiert (#13085) (vielen Dank an @yecril71pl!)
- In den öffentlichen `ConsoleHost`-APIs den Parameter `args` als Non-Nullable festlegen (#13429)
- Fehlendes Dispose für `CancellationTokenSource` hinzugefügt (#13420) (vielen Dank an @Youssef1313!)
- Korrektur `Get-Help` wird nicht ordnungsgemäß angezeigt, wenn der Parameter Platzhalter unterstützt (#13353) (vielen Dank an @ThomasNieto!)
- Hilfe für `pwsh` für den Parameter `-InputFormat` aktualisiert (#13355) (vielen Dank an @sethvs!)
- Für als Roslyn kopierte Dateien MIT-Lizenz deklariert (#13305) (vielen Dank an @xtqqczze!)
- Umwandlungsverhalten von `BigInteger` verbessert (#12629) (vielen Dank an @vexx32!)
- Verhalten von `Get-Acl -LiteralPath "HKLM:Software\Classes\*"` korrigiert (#13107) (vielen Dank an @Shriram0908!)
- Methode `DefaultVisit` zu Besucheroberfläche und Klasse hinzugefügt (#13258)
- In Konflikt stehende Kurzform für Switch `-s` (STA) für `pwsh` korrigiert (#13262) (vielen Dank an @iSazonov!)
- `Read-Host -MaskInput` so geändert, dass der vorhandene `SecureString`-Pfad verwendet, aber Nur-Text zurückgegeben wird (#13256)
- Das Entfernen von `ComEnumerator` als COM-Objekte mithilfe von `IEnumerator` wird nun in .NET 5.0 unterstützt (#13259)
- Temporären persönlichen Pfad beim Start von Runspace verwenden, wenn die Umgebungsvariable HOME nicht definiert ist (#13239)
- `Invoke-Command` so korrigiert, das ein rekursiver Aufruf desselben Verlaufseintrags erkannt wird (#13197)
- Das Präfix des Switches `-in` für `pwsh` der ausführbaren Datei `-inputformat` in `-inp` geändert, um den Konflikt mit `-interactive` zu beheben (#13205) (vielen Dank an @iSazonov!)
- Dateisystempfad von WSL verarbeitet, wenn die Sicherheitszone einer Datei analysiert wird (#13120)
- Switches in `Split-Path` als obligatorisch festgelegt (#13150) (vielen Dank an @kvprasoon!)
- Neues Fluent-Entwurfssymbol für PowerShell 7 (#13100) (vielen Dank an @sarthakmalik!)
- `Move-Item` so korrigiert, dass mountübergreifende Verschiebungen unter UNIX unterstützt werden (#13044)
- `NullReferenceException` in `CommandSearcher.GetNextCmdlet` korrigiert (#12659) (vielen Dank an @powercode!)
- `NullReferenceException` in Cmdlets für UNIX-Computer mit aktiven Testhooks verhindert (#12651) (vielen Dank an @vexx32!)
- Problem in `Select-Object` korrigiert, bei dem Member von `Hashtable` (z. B. `Keys`) nicht mit `-Property` oder `-ExpandProperty` verwendet werden können (#11097) (vielen Dank an @vexx32!)
- In Konflikt stehende Kurzform für Switch `-w` für pwsh korrigiert (#12945)
- Ressourcendatei `CimCmdlet` umbenannt (#12955) (vielen Dank an @iSazonov!)
- Verwendung von `Test-Path` in `ConciseView` entfernt (#12778)
- Bedingungsklausel von Switch-Anweisung `default` als Schlüsselwort kennzeichnen (#10487) (vielen Dank an @msftrncs!)
- Parameter `SchemaFile` zum Cmdlet `Test-Json` hinzugefügt (#11934) (vielen Dank an @beatcracker!)
- Parameter für Zertifikatanbieter reaktiviert (#10622) (vielen Dank an @iSazonov!)
- `New-Item` so korrigiert, dass eine symbolische Verknüpfung zum Ziel des relativen Pfads erstellt wird (#12797) (vielen Dank an @iSazonov!)
- Eigenschaft `CommandLine` zu Prozess hinzugefügt (#12288) (vielen Dank an @iSazonov!)
- Parameter `-MaskInput` zu `Read-Host` hinzugefügt (#10908) (vielen Dank an @davinci26!)
- `CimCmdlets` so geändert, dass `AliasAttribute` verwendet wird (#12617) (vielen Dank an @thlac!)
- Falschen Index in Formatzeichenfolge in ParameterBinderBase korrigiert (#12630) (vielen Dank an @powercode!)
- Eigenschaft `CommandInfo` in `Command.Clone()` kopiert (#12301) (vielen Dank an @TylerLeonhardt!)
- `-IncludeEqual` wird in `Compare-Object` angewendet, wenn `-ExcludeDifferent` angegeben ist (#12317) (vielen Dank an @davidseibel!)
- `Get-FileHash` so geändert, dass Dateihandler vor dem Schreiben der Ausgabe geschlossen werden (#12474) (vielen Dank an @HumanEquivalentUnit!)
- Inkonsistente Ausnahmemeldung im Operator `-replace` korrigiert (#12388) (vielen Dank an @jackdcasey!)
- Laden des Moduls `WinCompat` so geändert, dass PowerShell 7-Module mit höherer Priorität behandelt werden (#12269)
- Wiederverwendung des Runspace `ForEach-Object -Parallel` implementiert (#12122)
- `Get-Service` so korrigiert, dass die Sammlung bei der Enumeration nicht geändert wird (#11851) (vielen Dank an @NextTurn!)
- IPC Named Pipe bei Beenden von PowerShell bereinigt (#12187)
- RegEx für Erkennung `<img />` in Web-Cmdlets korrigiert (#12099) (vielen Dank an @vexx32!)
- Kürzere signierte hexadezimale Literale mit entsprechenden Typsuffixen zulässig (#11844) (vielen Dank an @vexx32!)
- Verhalten des Parameters `UseNewEnvironment` im Cmdlet `Start-Process` unter Windows aktualisiert (#10830) (vielen Dank an @iSazonov!)
- Switch `-Shuffle` zu Befehl `Get-Random` hinzugefügt (#11093) (vielen Dank an @eugenesmlv!)
- `GetWindowsPowerShellModulePath` mit mehreren PS-Installationen kompatibel gestaltet (#12280)
- `Start-Job` so korrigiert, dass es auf Systemen funktioniert, die Windows PowerShell nicht als Standardshell registriert haben (#12296)
- Bei Angeben eines Alias und von `-Syntax` für `Get-Command` wird die Syntax mit Befehlen zurückgegeben, die mit Aliasen versehen sind (#10784) (vielen Dank an @ChrisLGardner!)
- CSV-Cmdlets funktionieren nun, wenn `-AsNeeded` verwendet wird und eine unvollständige Zeile vorhanden ist (#12281) (vielen Dank an @iSazonov!)
- Bei lokalen Aufrufen muss `-PowerShellVersion 5.1` nicht für `Get-FormatData` angefordert werden, um alle Formatdaten einzusehen. (#11270) (vielen Dank an @mklement0!)
- Unterstützung für Big Endian `UTF-32` hinzugefügt (#11947) (vielen Dank an @NoMoreFood!)
- Mögliche Race-Bedingung korrigiert, die ein Leck bei der Freigabe von PowerShell-Objekten in `ForEach-Object -Parallel` verursacht (#12227)
- `-FromUnixTime` zu `Get-Date` hinzugefügt, um die UNIX-Zeiteingabe zuzulassen (#12179) (vielen Dank an@jackdcasey!)
- Vorder- und Hintergrundfarben für Standardstatus für besseren Kontrast geändert (#11455) (vielen Dank an @rkeithhill!)
- `foreach -parallel` korrigiert, wenn das aktuelle Laufwerk nicht verfügbar ist (#12197)
- Zurückgegebenes Ergebnis nicht in `PSObject` umgebrochen, wenn `ScriptBlock` in `delegate` konvertiert wird (#10619)
- Keine DNS-Auflösungsfehler in `Test-Connection -Quiet` geschrieben (#12204) (vielen Dank an @vexx32!)
- Dedizierte Threads verwenden, um die umgeleiteten Ausgabe- und Fehlerdatenströme des untergeordneten Prozesses für Aufträge außerhalb des Prozesses zu lesen (#11713)
- Problem mit der bevorzugten Reihenfolge von Operatoren korrigiert (#12075) (vielen Dank an @DamirAinullin!)
- `NullReferenceException` korrigiert, wenn allgemeine Parameter des Typs gebunden werden `ActionPreference` (#12124)
- Standardformatierung für deserialisierte `MatchInfo` korrigiert (#11728) (vielen Dank an @iSazonov!)
- Asynchrone Datenströme in `Invoke-RestMethod` verwendet (#11095) (vielen Dank an @iSazonov!)
- UTF-8-Erkennung in `Get-Content -Tail` behoben (#11899) (vielen Dank an @NoMoreFood!)
- `IOException` in `Get-FileHash` behandelt (#11944) (vielen Dank an @iSazonov!)
- `PowerShell Core` in einer Ressourcenzeichenfolge in `PowerShell` geändert (#11928) (vielen Dank an @alexandair!)
- `MainWindowTitle` in `PSHostProcessInfo` reaktiviert (#11885) (vielen Dank an @iSazonov!)
- Sonstige geringfügige Updates der Windows-Kompatibilität (#11980)
- `ConciseView` so korrigiert, das `PositionMessage` mithilfe von `[Environment]::NewLine` aufgeteilt wird (#12010)
- Einschränkung für Netzwerk-Hops für interaktive Sitzungen aufgehoben (#11920)
- `NullReferenceException` in `SuspendStoppingPipeline()` und `RestoreStoppingPipeline()` korrigiert (#11870) (vielen Dank an @iSazonov!)
- GUID für `FormatViewDefinition` `InstanceId` generieren, falls nicht angegeben (#11896)
- `ConciseView` korrigiert, wenn die Fehlermeldung die Fensterbreite überschreitet und keine Leerzeichen enthält (#11880)
- Plattformübergreifenden Schlüsselaustausch von Remoteschlüssel für `CAPI-compatible` zulassen (#11185) (vielen Dank an @silijon!)
- Fehlermeldung korrigiert (#11862) (vielen Dank an @NextTurn!)
- `ConciseView` für den Fall korrigiert, dass es keine Konsole gibt, um die Breite abzurufen (#11784)
- `CmsCommands` so aktualisiert, dass Microsoft Store und nicht der Zertifikatanbieter verwendet wird (#11643) (vielen Dank an @mikeTWC1984!)
- `pwsh` für das Funktionieren auf Windows-Systemen aktiviert, auf denen `mpr.dll` und STA nicht verfügbar sind (#11748)
- `Restart-Computer` für `Un*x` und macOS umgestaltet und implementiert (#11319)
- Implementierung von `Stop-Computer` für Linux und macOS hinzugefügt (#11151)
- Funktion`help` so korrigiert, dass vor ihrem Verwenden geprüft wird, ob `less` verfügbar ist (#11737)
- `PSPath` in `certificate_format_ps1.xml` geändert (#11603) (vielen Dank an @xtqqczze!)
- Regulären Ausdruck entsprechend Beziehungstypen ohne Anführungszeichen im Linkheader geändert (#11711) (vielen Dank an @Marusyk!)
- Fehlermeldung beim Löschen symbolischer Verknüpfungen korrigiert (#11331)
- Benutzerdefinierten Typ `Selected.*` zu `PSCustomObject` in `Select-Object` nur einmal hinzugefügt (#11548) (vielen Dank an @iSazonov!)
- `-AsUTC` zum Cmdlet `Get-Date` hinzugefügt (#11611)
- Gruppierungsverhalten mit booleschen Werten in `Format-Hex` korrigiert (#11587) (vielen Dank an @vexx32!)
- Veranlasst, dass `Test-Connection` stets den Standardsynchronisierungskontext für das Senden von Ping-Anforderungen verwendet (#11517)
- Fehlermeldungen beim Start korrigiert (#11473) (vielen Dank an @iSazonov!)
- Header mit NULL-Werten in Web-Cmdlets ignorieren (#11424) (vielen Dank an @iSazonov!)
- Überprüfung von Freigabe des Auftrags `Invoke-Command` erneut hinzugefügt. (#11388)
- „Formatierer so aktualisieren, dass keine Zeilenumbrüche geschrieben werden, wenn der Inhalt leer ist (#11193)“ zurückgesetzt (#11342) (vielen Dank an @iSazonov!)
- `CompleteInput` erlauben, Ergebnisse von `ArgumentCompleter` zurückzugeben, wenn `AST` oder Skript eine passende Funktionsdefinition hat (#10574) (vielen Dank an @M1kep!)
- Formatierer so aktualisieren, dass keine Zeilenumbrüche geschrieben werden, wenn der Inhalt leer ist (#11193)

<!-- TODO: add more general contributor thank you listing -->
