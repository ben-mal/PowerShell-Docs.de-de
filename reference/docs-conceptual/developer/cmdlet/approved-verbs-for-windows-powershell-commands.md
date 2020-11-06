---
ms.date: 09/07/2018
ms.topic: reference
title: Genehmigte Verben für PowerShell-Befehle
description: Genehmigte Verben für PowerShell-Befehle
ms.openlocfilehash: fc1ff989ae86862e0f9cc24d8bcba2ff02ef68cc
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93355101"
---
# <a name="approved-verbs-for-powershell-commands"></a>Genehmigte Verben für PowerShell-Befehle

PowerShell verwendet Verb-Substantiv-Paare für die Namen von Cmdlets und deren abgeleitete .NET-Klassen.
Der Verbteil des Namens bezeichnet die Aktion, die das Cmdlet ausführt. Der Substantivteil des Namens bezeichnet die Entität, für die die Aktion ausgeführt wird. Beispielsweise ruft das Cmdlet `Get-Command` alle Befehle ab, die in PowerShell registriert sind.

> [!NOTE]
> PowerShell verwendet den Begriff _Verb_ , um ein Wort zu beschreiben, das eine Aktion impliziert, auch wenn es sich dabei in der englischen Sprache nicht um ein Verb handelt. Beispielsweise ist der Begriff _New_ ein gültiger PowerShell-Verbname, da er eine Aktion impliziert, auch wenn er im Englischen kein Verb ist.

Für jedes genehmigte Verb ist ein entsprechendes _Aliaspräfix_ definiert. Dieses Aliaspräfix wird in Aliasen für Befehle verwendet, die dieses Verb verwenden. Das Aliaspräfix für `Import` ist beispielsweise `ip` und der Alias für `Import-Module` folglich `ipmo`. Es handelt sich hierbei um eine Empfehlung und nicht um eine Regel. Diese muss insbesondere nicht bei Befehlsaliasen beachtet werden, die bekannte Befehle aus anderen Umgebungen imitieren.

## <a name="verb-naming-recommendations"></a>Benennungsempfehlungen für Verben

Die folgenden Empfehlungen helfen Ihnen bei der Auswahl eines geeigneten Verbs für Ihr Cmdlet, um Konsistenz zwischen den von Ihnen erstellten, den von PowerShell bereitgestellten und den von anderen entworfenen Cmdlets sicherzustellen.

- Verwenden Sie einen der von PowerShell bereitgestellten vordefinierten Verbnamen.
- Verwenden Sie das Verb, um den allgemeinen Zweck der Aktion zu beschreiben, und Parameter, um die Aktion des Cmdlets genauer zu definieren.
- Verwenden Sie keine Synonyme von genehmigten Verben. Verwenden Sie z. B. immer `Remove` und nie `Delete` oder `Eliminate`.
- Verwenden Sie nur die in diesem Artikel aufgeführte Verbform. Verwenden Sie z. B. `Get`, aber nicht `Getting` oder `Gets`.
- Verwenden Sie nicht die folgenden reservierten Verben oder Aliase. Diese Verben werden in der PowerShell-Sprache oder ein paar wenigen der zugehörigen Cmdlets in besonderen Fällen verwendet.
  - ForEach (foreach)
  - [Format](/dotnet/api/System.Management.Automation.VerbsCommon.Format) (f): Hiermit werden Objekte in einer angegebenen Form oder einem angegebenen Layout angeordnet.
  - [Group](/dotnet/api/System.Management.Automation.VerbsData.Group) (gp): Hiermit werden eine oder mehrere Ressourcen an- oder zugeordnet.
  - [Ping](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Ping) (pi)
  - Sort (sr)
  - Tee (te)
  - Where (wh)

Über das `Get-Verb`-Cmdlet können Sie eine Liste mit allen Verben abrufen.

## <a name="similar-verbs-for-different-actions"></a>Ähnliche Verben für verschiedene Aktionen

Die folgenden ähnlichen Verben stehen für verschiedene Aktionen.

### <a name="new-vs-set"></a>New vs. Set

Verwenden Sie das Verb `New`, wenn Sie eine neue Ressource erstellen möchten. Verwenden Sie das Verb `Set`, um eine bereits vorhandene Ressource zu ändern bzw. optional zu erstellen, falls sie doch nicht vorhanden ist, z. B mit dem Cmdlet `Set-Variable`.

### <a name="find-vs-search"></a>Find vs. Suchen,

Verwenden Sie das Verb `Find`, wenn Sie nach einem Objekt suchen möchten. Verwenden Sie das Verb `Search`, um einen Verweis auf eine Ressource in einem Container zu erstellen.

### <a name="get-vs-read"></a>Get vs. Lesen

Verwenden Sie das Verb `Get`, um Informationen über eine Ressource (z. B. eine Datei) abzurufen oder um ein Objekt abzurufen, mit dem Sie in Zukunft auf die Ressource zugreifen können. Verwenden Sie das Verb `Read`, um eine Ressource zu öffnen und darin enthaltene Informationen zu extrahieren.

### <a name="invoke-vs-start"></a>Invoke vs. Start

Verwenden Sie das Verb `Invoke`, um synchrone Vorgänge auszuführen, z. B. das Ausführen eines Befehls und das Warten, bis dieser Vorgang abgeschlossen ist. Verwenden Sie das Verb `Start`, um asynchrone Vorgänge zu starten (z. B. einen autonomen Prozess).

### <a name="ping-vs-test"></a>Ping vs. Test

Verwenden Sie das Verb `Test`.

## <a name="common-verbs"></a>Häufig verwendete Verben

PowerShell verwendet die Enumerationsklasse [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon) zum Definieren generischer Aktionen, die in fast allen Cmdlets verwendet werden können. In der folgenden Tabelle sind die meisten der definierten Verben aufgeführt.

|Verb (Alias)|Aktion|Zu vermeidende Synonyme|
|--------------------|------------|--------------|
|[Add](/dotnet/api/System.Management.Automation.VerbsCommon.Add) (a)|Hiermit wird einem Container eine Ressource hinzugefügt oder ein Element an ein anderes Element angefügt. Das Cmdlet `Add-Content` ergänzt z. B. Inhalte in einer Datei. Dieses Verb ist das Gegenstück zu `Remove`.|Append, Attach, Concatenate, Insert|
|[Clear](/dotnet/api/System.Management.Automation.VerbsCommon.Clear) (cl)|Hiermit werden alle Ressourcen in einem Container entfernt, der Container selbst wird jedoch nicht gelöscht. Das Cmdlet `Clear-Content` entfernt z. B. den Inhalt einer Datei, löscht die Datei jedoch nicht.|Flush, Erase, Release, Unmark, Unset, Nullify|
|[Close](/dotnet/api/System.Management.Automation.VerbsCommon.Close) (cs)|Hiermit wird der Zustand einer Ressource geändert, um sie unzugänglich, nicht verfügbar oder nicht verwendbar zu machen. Dieses Verb ist das Gegenstück zu `Open.`.||
|[Copy](/dotnet/api/System.Management.Automation.VerbsCommon.Copy) (cp)|Hiermit wird eine Ressource in einen anderen Namen oder einen anderen Container kopiert. Das Cmdlet `Copy-Item` kopiert beispielsweise ein Element (z. B. eine Datei) von einem Speicherort im Datenspeicher an einen anderen Speicherort.|Duplicate, Clone, Replicate, Sync|
|[Enter](/dotnet/api/System.Management.Automation.VerbsCommon.Enter) (et)|Hiermit wird eine Aktion angegeben, die dem Benutzer das Wechseln zu einer Ressource ermöglicht. Beispielsweise wechselt der Benutzer mit dem Cmdlet `Enter-PSSession` in eine interaktive Sitzung. Dieses Verb ist das Gegenstück zu `Exit`.|Push, Into|
|[Exit](/dotnet/api/System.Management.Automation.VerbsCommon.Exit) (ex)|Hiermit wird die aktuelle Umgebung oder der aktuelle Kontext auf den zuletzt verwendeten Kontext festgelegt. Beispielsweise wechselt der Benutzer mit dem Cmdlet `Exit-PSSession` in die Sitzung, die zum Starten der interaktiven Sitzung verwendet wurde. Dieses Verb ist das Gegenstück zu `Enter`.|Pop, Out|
|[Find](/dotnet/api/System.Management.Automation.VerbsCommon.Find) (fd)|Hiermit wird nach einem Objekt in einem unbekannten, impliziten, optionalen oder angegebenen Container gesucht.|Suchen,|
|[Get](/dotnet/api/System.Management.Automation.VerbsCommon.Get) (g)|Hiermit wird eine Aktion angegeben, die eine Ressource abruft. Dieses Verb ist das Gegenstück zu `Set`.|Read, Open, Cat, Type, Dir, Obtain, Dump, Acquire, Examine, Find, Search|
|[Hide](/dotnet/api/System.Management.Automation.VerbsCommon.Hide) (h)|Hiermit wird eine Ressource unauffindbar gemacht. Beispielsweise kann ein Cmdlet, dessen Name das Verb „Hide“ enthält, einen Dienst vor einem Benutzer verbergen. Dieses Verb ist das Gegenstück zu `Show`.|Blockieren|
|[Join](/dotnet/api/System.Management.Automation.VerbsCommon.Join) (j)|Hiermit werden Ressourcen zu einer Ressource kombiniert. Das Cmdlet `Join-Path` kombiniert z. B. einen Pfad mit einem untergeordneten Pfad, um daraus einen Gesamtpfad zu erstellen. Dieses Verb ist das Gegenstück zu `Split`.|Combine, Unite, Connect, Associate|
|[Lock](/dotnet/api/System.Management.Automation.VerbsCommon.Lock) (lk)|Hiermit wird eine Ressource geschützt. Dieses Verb ist das Gegenstück zu `Unlock`.|Restrict, Secure|
|[Move](/dotnet/api/System.Management.Automation.VerbsCommon.Move) (m)|Hiermit wird eine Ressource von einem Speicherort an einen anderen verschoben. Das Cmdlet `Move-Item` verschiebt z. B. ein Element von einem Speicherort im Datenspeicher an einen anderen Speicherort.|Transfer, Name, Migrate|
|[New](/dotnet/api/System.Management.Automation.VerbsCommon.New) (n)|Dient zum Erstellen einer Ressource. (Das Verb `Set` kann auch verwendet werden, wenn eine Ressource erstellt wird, die Daten enthält, wie beim Cmdlet `Set-Variable`.)|Create, Generate, Build, Make, Allocate|
|[Open](/dotnet/api/System.Management.Automation.VerbsCommon.Open) (op)|Hiermit wird der Zustand einer Ressource geändert, um sie zugänglich, verfügbar oder verwendbar zu machen. Dieses Verb ist das Gegenstück zu `Close`.||
|[Optimize](/dotnet/api/System.Management.Automation.VerbsCommon.Optimize) (om)|Hiermit wird die Effektivität einer Ressource gesteigert.||
|[Pop](/dotnet/api/System.Management.Automation.VerbsCommon.Pop) (pop)|Hiermit wird ein Element ganz oben im Stapel entfernt. Das Cmdlet `Pop-Location` ändert z. B. den aktuellen Speicherort in den Speicherort, der zuletzt oben zum Stapel hinzugefügt wurde.||
|[Push](/dotnet/api/System.Management.Automation.VerbsCommon.Push) (pu)|Hiermit wird ein Element oben zu einem Stapel hinzugefügt. Das Cmdlet `Push-Location` fügt z. B. den aktuellen Speicherort oben zum Stapel hinzu.||
|[Redo](/dotnet/api/System.Management.Automation.VerbsCommon.Redo) (re)|Hiermit wird eine Ressource auf den Zustand zurückgesetzt, der zuvor rückgängig gemacht wurde.||
|[Remove](/dotnet/api/System.Management.Automation.VerbsCommon.Remove) (r)|Hiermit wird eine Ressource aus einem Container gelöscht. Das Cmdlet `Remove-Variable` löscht z. B. eine Variable und deren Wert. Dieses Verb ist das Gegenstück zu `Add`.|Clear, Cut, Dispose, Discard, Erase|
|[Rename](/dotnet/api/System.Management.Automation.VerbsCommon.Rename) (rn)|Hiermit wird der Name einer Ressource geändert. Das Cmdlet `Rename-Item`, das für den Zugriff auf gespeicherte Daten verwendet wird, ändert z. B. den Namen eines Elements im Datenspeicher.|Change|
|[Reset](/dotnet/api/System.Management.Automation.VerbsCommon.Reset) (rs)|Hiermit wird eine Ressource auf den ursprünglichen Zustand zurückgesetzt.||
|[Resize](/dotnet/api/System.Management.Automation.VerbsCommon.Resize)(rz)|Hiermit wird die Größe einer Ressource geändert.||
|[Search](/dotnet/api/System.Management.Automation.VerbsCommon.Search) (sr)|Hiermit wird ein Verweis auf eine Ressource in einem Container erstellt.|Find, Locate|
|[Select](/dotnet/api/System.Management.Automation.VerbsCommon.Select) (sc)|Hiermit wird eine Ressource in einem Container gesucht. Das Cmdlet `Select-String` sucht z. B. Text in Zeichenfolgen und Dateien.|Find, Locate|
|[Set](/dotnet/api/System.Management.Automation.VerbsCommon.Set) (s)|Hiermit werden Daten in einer vorhandenen Ressource ersetzt, oder eine Ressource, die bestimmte Daten enthält, wird erstellt. Das Cmdlet `Set-Date` ändert z. B. die Systemzeit auf dem lokalen Computer. (Das Verb `New` kann auch verwendet werden, um eine Ressource zu erstellen.) Dieses Verb ist das Gegenstück zu `Get`.|Write, Reset, Assign, Configure|
|[Show](/dotnet/api/System.Management.Automation.VerbsCommon.Show) (sh)|Hiermit wird eine Ressource für den Benutzer sichtbar gemacht. Dieses Verb ist das Gegenstück zu `Hide`.|Display, Produce|
|[Skip](/dotnet/api/System.Management.Automation.VerbsCommon.Skip) (sk)|Hiermit werden in einer Sequenz eine oder mehrere Ressourcen oder Punkte übersprungen.|Bypass, Jump|
|[Split](/dotnet/api/System.Management.Automation.VerbsCommon.Split) (sl)|Hiermit werden Teile einer Ressource getrennt. Das Cmdlet `Split-Path` gibt z. B. verschiedene Teile eines Pfads zurück. Dieses Verb ist das Gegenstück zu `Join`.|Getrennt|
|[Step](/dotnet/api/System.Management.Automation.VerbsCommon.Step) (st)|Hiermit wird in einer Sequenz zum nächsten Punkt oder zur nächsten Ressource gewechselt.||
|[Switch](/dotnet/api/System.Management.Automation.VerbsCommon.Switch) (sw)|Hiermit wird eine Aktion angegeben, die zwischen zwei Ressourcen wechselt, z. B. ein Wechsel zwischen zwei verschiedenen Speicherorten, Zuständigkeiten oder Zuständen.||
|[Undo](/dotnet/api/System.Management.Automation.VerbsCommon.Undo) (un)|Hiermit wird eine Ressource auf den vorherigen Zustand zurückgesetzt.||
|[Unlock](/dotnet/api/System.Management.Automation.VerbsCommon.Unlock) (uk)|Hiermit wird eine gesperrte Ressource freigegeben. Dieses Verb ist das Gegenstück zu `Lock`.|Release, Unrestrict, Unsecure|
|[Watch](/dotnet/api/System.Management.Automation.VerbsCommon.Watch) (wc)|Hiermit wird eine Ressource kontinuierlich auf Änderungen überprüft oder überwacht.||

## <a name="communications-verbs"></a>Kommunikationsverben

PowerShell verwendet die Klasse [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications) zum Definieren von Aktionen für die Kommunikation. In der folgenden Tabelle sind die meisten der definierten Verben aufgeführt.

|Verb (Alias)|Aktion|Zu vermeidende Synonyme|
|--------------------|------------|--------------|
|[Connect](/dotnet/api/System.Management.Automation.VerbsCommunications.Connect) (cc)|Hiermit wird eine Verbindung zwischen einer Quelle und einem Ziel hergestellt. Dieses Verb ist das Gegenstück zu `Disconnect`.|Join, Telnet|
|[Disconnect](/dotnet/api/System.Management.Automation.VerbsCommunications.Disconnect) (dc)|Hiermit wird eine Verbindung zwischen einer Quelle und einem Ziel getrennt. Dieses Verb ist das Gegenstück zu `Connect`.|Break, Logoff|
|[Read](/dotnet/api/System.Management.Automation.VerbsCommunications.Read) (rd)|Hiermit werden Informationen aus einer Quelle abgerufen. Dieses Verb ist das Gegenstück zu `Write`.|Acquire, Prompt, Get|
|[Receive](/dotnet/api/System.Management.Automation.VerbsCommunications.Receive) (rc)|Hiermit werden von einer Quelle gesendete Informationen akzeptiert. Dieses Verb ist das Gegenstück zu `Send`.|Read, Accept, Peek|
|[Send](/dotnet/api/System.Management.Automation.VerbsCommunications.Send) (sd)|Hiermit werden Informationen an ein Ziel gesendet. Dieses Verb ist das Gegenstück zu `Receive`.|Put, Broadcast, Mail, Fax|
|[Write](/dotnet/api/System.Management.Automation.VerbsCommunications.Write) (wr)|Hiermit werden einem Ziel Informationen hinzugefügt. Dieses Verb ist das Gegenstück zu `Read`.|Put, Print|

## <a name="data-verbs"></a>Datenverben

PowerShell verwendet die Klasse [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData) zum Definieren von Aktionen für die Datenverarbeitung. In der folgenden Tabelle sind die meisten der definierten Verben aufgeführt.

|Verbname (Alias)|Aktion|Zu vermeidende Synonyme|
|-------------------------|------------|--------------|
|[Backup](/dotnet/api/System.Management.Automation.VerbsData.Backup) (ba)|Hiermit werden Daten durch Replikation gespeichert.|Save, Burn, Replicate, Sync|
|[Checkpoint](/dotnet/api/System.Management.Automation.VerbsData.Checkpoint) (ch)|Hiermit wird eine Momentaufnahme des aktuellen Zustands der Daten oder ihrer Konfiguration erstellt.|Diff|
|[Compare](/dotnet/api/System.Management.Automation.VerbsData.Compare) (cr)|Hiermit werden die Daten aus einer Ressource im Vergleich mit Daten aus einer anderen Ressource ausgewertet.|Diff|
|[Compress](/dotnet/api/System.Management.Automation.VerbsData.Compress) (cm)|Hiermit werden die Daten einer Ressource komprimiert. Dieses Verb ist das Gegenstück zu `Expand`.|Kompakt|
|[Convert](/dotnet/api/System.Management.Automation.VerbsData.Convert) (cv)|Hiermit wird die Darstellung der Daten in eine andere geändert, wenn das Cmdlet bidirektionale Konvertierung oder die Konvertierung zwischen verschiedenen Datentypen unterstützt.|Change, Resize, Resample|
|[ConvertFrom](/dotnet/api/System.Management.Automation.VerbsData.ConvertFrom) (cf)|Hiermit wird ein primärer Eingabetyp (das Substantiv des Cmdlets gibt die Eingabe an) in einen oder mehrere unterstützte Ausgabetypen konvertiert.|Export, Output, Out|
|[ConvertTo](/dotnet/api/System.Management.Automation.VerbsData.ConvertTo) (ct)|Hiermit wird von einem oder mehreren Eingabetypen in einen primären Ausgabetyp konvertiert. Das Substantiv des Cmdlets gibt den Ausgabetyp an.|Import, Input, In|
|[Dismount](/dotnet/api/System.Management.Automation.VerbsData.Dismount) (dm)|Hiermit wird eine angegebene Entität von einem Speicherort getrennt. Dieses Verb ist das Gegenstück zu `Mount`.|Unmount, Unlink|
|[Edit](/dotnet/api/System.Management.Automation.VerbsData.Edit) (ed)|Hiermit werden vorhandene Daten durch Hinzufügen oder Entfernen von Inhalten geändert.|Change, Update, Modify|
|[Expand](/dotnet/api/System.Management.Automation.VerbsData.Expand) (en)|Hiermit wird der ursprüngliche Zustand der Daten einer komprimierten Ressource wiederhergestellt. Dieses Verb ist das Gegenstück zu `Compress`.|Explode, Uncompress|
|[Export](/dotnet/api/System.Management.Automation.VerbsData.Export) (ep)|Hiermit wird die primäre Eingabe in einem beständigen Datenspeicher gespeichert, z. B. in einer Datei, oder in einem Austauschformat. Dieses Verb ist das Gegenstück zu `Import`.|Extract, Backup|
|[Import](/dotnet/api/System.Management.Automation.VerbsData.Import) (ip)|Hiermit wird eine Ressource aus Daten erstellt, die in einem beständigen Datenspeicher (z. B. einer Datei) oder in einem Austauschformat gespeichert sind. Das Cmdlet `Import-CSV` importiert z. B. Daten aus einer CSV-Datei (Comma-Separated Value File, durch Trennzeichen getrennte Datei) in Objekte, die von anderen Cmdlets verwendet werden können. Dieses Verb ist das Gegenstück zu `Export`.|BulkLoad, Load|
|[Initialize](/dotnet/api/System.Management.Automation.VerbsData.Initialize) (in)|Hiermit wird eine Ressource für die Verwendung vorbereitet und in einen Standardzustand versetzt.|Erase, Init, Renew, Rebuild, Reinitialize, Setup|
|[Limit](/dotnet/api/System.Management.Automation.VerbsData.Limit) (l)|Hiermit werden Einschränkungen auf eine Ressource angewendet.|Kontingent|
|[Merge](/dotnet/api/System.Management.Automation.VerbsData.Merge) (mg)|Hiermit wird aus mehreren Ressourcen eine einzelne erstellt.|Combine, Join|
|[Mount](/dotnet/api/System.Management.Automation.VerbsData.Mount) (mt)|Hiermit wird eine angegebene Entität mit einem Speicherort verknüpft. Dieses Verb ist das Gegenstück zu `Dismount`.|Verbinden|
|[Out](/dotnet/api/System.Management.Automation.VerbsData.Out) (o)|Hiermit werden Daten aus der Umgebung heraus gesendet. Das Cmdlet `Out-Printer` sendet z. B. Daten an einen Drucker.||
|[Publish](/dotnet/api/System.Management.Automation.VerbsData.Publish) (pb)|Hiermit wird eine Ressource anderen zur Verfügung gestellt. Dieses Verb ist das Gegenstück zu `Unpublish`.|Deploy, Release, Install|
|[Restore](/dotnet/api/System.Management.Automation.VerbsData.Restore) (rr)|Hiermit wird eine Ressource in einen vordefinierten Zustand versetzt, z. B. in einen über `Checkpoint` festgelegten. Das Cmdlet `Restore-Computer` startet z. B. eine Systemwiederherstellung auf dem lokalen Computer.|Repair, Return, Undo, Fix|
|[Save](/dotnet/api/System.Management.Automation.VerbsData.Save) (sv)|Hiermit werden Daten gespeichert, um einen Verlust zu vermeiden.||
|[Sync](/dotnet/api/System.Management.Automation.VerbsData.Sync) (sy)|Hiermit wird sichergestellt, dass sich zwei oder mehr Ressourcen im gleichen Zustand befinden.|Replicate, Coerce, Match|
|[Unpublish](/dotnet/api/System.Management.Automation.VerbsData.Unpublish) (ub)|Hiermit wird eine Ressource für andere unzugänglich gemacht. Dieses Verb ist das Gegenstück zu `Publish`.|Uninstall, Revert, Hide|
|[Update](/dotnet/api/System.Management.Automation.VerbsData.Update) (ud)|Hiermit wird eine Ressource auf den neuesten Stand gebracht, um Zustand, Richtigkeit, Konformität oder Compliance aufrechtzuerhalten. Das Cmdlet `Update-FormatData` aktualisiert z. B. Formatdateien und fügt diese der aktuellen PowerShell-Konsole hinzu.|Refresh, Renew, Recalculate, Re-index|

## <a name="diagnostic-verbs"></a>Diagnoseverben

PowerShell verwendet die Klasse [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic) zum Definieren von Aktionen für die Diagnose. In der folgenden Tabelle sind die meisten der definierten Verben aufgeführt.

|Verb (Alias)|Aktion|Zu vermeidende Synonyme|
|--------------------|------------|--------------|
|[Debug](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Debug) (db)|Hiermit wird eine Ressource untersucht, um Funktionsprobleme zu erkennen.|Diagnose|
|[Measure](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Measure) (ms)|Hiermit werden Ressourcen ermittelt, die von einem angegebenen Vorgang genutzt werden, oder Statistiken über eine Ressource abgerufen.|Calculate, Determine, Analyze|
|[Repair](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Repair) (rp)|Hiermit wird ein verwendbarer Zustand einer Ressource wiederhergestellt.|Fix, Restore|
|[Resolve](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Resolve) (rv)|Hiermit wird eine Kurzdarstellung einer Ressource einer ausführlicheren Darstellung zugeordnet.|Expand, Determine|
|[Test](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Test) (t)|Hiermit wird die Funktion oder Konsistenz einer Ressource überprüft.|Diagnose, Analyze, Salvage, Verify|
|[Trace](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Trace) (tr)|Hiermit werden die Aktivitäten einer Ressource nachverfolgt.|Track, Follow, Inspect, Dig|

## <a name="lifecycle-verbs"></a>Lebenszyklusverben

PowerShell verwendet die Klasse [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) zum Definieren von Aktionen in Bezug auf den Lebenszyklus einer Ressource. In der folgenden Tabelle sind die meisten der definierten Verben aufgeführt.

|Verb (Alias)|Aktion|Zu vermeidende Synonyme|
|--------------------|------------|--------------|
|[Approve](/dotnet/api/System.Management.Automation.VerbsLifecycle.Approve) (ap)|Hiermit wird der Zustand einer Ressource oder eines Prozesses bestätigt oder akzeptiert.||
|[Assert](/dotnet/api/System.Management.Automation.VerbsLifecycle.Assert) (as)|Hiermit wird der Zustand einer Ressource überprüft.|Certify|
|[Build](/dotnet/api/System.Management.Automation.VerbsLifecycle.Build) (bd)|Hiermit wird ein Artefakt (in der Regel eine Binärdatei oder ein Dokument) aus einer Gruppe von Eingabedateien erstellt (in der Regel Quellcode oder deklarative Dokumente). Dieses Verb wurde in PowerShell 6 hinzugefügt.||
|[Complete](/dotnet/api/system.management.automation.host.buffercelltype) (cp)|Hiermit wird ein Vorgang beendet.||
|[Confirm](/dotnet/api/System.Management.Automation.VerbsLifecycle.Confirm) (cn)|Hiermit wird der Zustand einer Ressource oder eines Prozesses anerkannt, verifiziert oder validiert.|Acknowledge, Agree, Certify, Validate, Verify|
|[Deny](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deny) (dn)|Hiermit wird der Zustand einer Ressource oder eines Prozesses nicht zugelassen, abgelehnt, blockiert oder verweigert.|Block, Object, Refuse, Reject|
|[Deploy](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deploy) (dp)|Hiermit wird eine Anwendung, Website oder Lösung an ein oder mehrere Remoteziele gesendet, sodass ein Endbenutzer dieser Lösung nach Abschluss der Bereitstellung darauf zugreifen kann. Dieses Verb wurde in PowerShell 6 hinzugefügt.||
|[Disable](/dotnet/api/System.Management.Automation.VerbsLifecycle.Disable) (d)|Hiermit wird eine Ressource so konfiguriert, dass sie nicht verfügbar oder inaktiv ist. Das Cmdlet `Disable-PSBreakpoint` deaktiviert z. B. einen Breakpoint. Dieses Verb ist das Gegenstück zu `Enable`.|Halt, Hide|
|[Enable](/dotnet/api/System.Management.Automation.VerbsLifecycle.Enable) (e)|Hiermit wird eine Ressource so konfiguriert, dass sie verfügbar oder aktiv ist. Das Cmdlet `Enable-PSBreakpoint` aktiviert z. B. einen Breakpoint. Dieses Verb ist das Gegenstück zu `Disable`.|Start, Begin|
|[Install](/dotnet/api/System.Management.Automation.VerbsLifecycle.Install) (is)|Hiermit wird eine Ressource an einem Speicherort platziert und optional initialisiert. Dieses Verb ist das Gegenstück zu `Uninstall`.|Einrichten|
|[Invoke](/dotnet/api/System.Management.Automation.VerbsLifecycle.Invoke) (i)|Hiermit wird eine Aktion ausgeführt, z. B. das Ausführen eines Befehls oder einer Methode.|Run, Start|
|[Register](/dotnet/api/System.Management.Automation.VerbsLifecycle.Register) (rg)|Hiermit wird ein Eintrag für eine Ressource in einem Repository erstellt, z. B. in einer Datenbank. Dieses Verb ist das Gegenstück zu `Unregister`.||
|[Request](/dotnet/api/System.Management.Automation.VerbsLifecycle.Request) (rq)|Hiermit werden Ressourcen oder Berechtigungen angefordert.||
|[Restart](/dotnet/api/System.Management.Automation.VerbsLifecycle.Restart) (rt)|Hiermit wird ein Vorgang beendet und dann wieder gestartet. Das Cmdlet `Restart-Service` beendet z. B. einen Dienst und startet ihn dann wieder.|Recyceln|
|[Resume](/dotnet/api/System.Management.Automation.VerbsLifecycle.Resume) (ru)|Hiermit wird ein angehaltener Vorgang gestartet. Das Cmdlet `Resume-Service` startet z. B. einen Dienst, der angehalten wurde. Dieses Verb ist das Gegenstück zu `Suspend`.||
|[Start](/dotnet/api/System.Management.Automation.VerbsLifecycle.Start) (sa)|Hiermit wird ein Vorgang initiiert. Das Cmdlet `Start-Service` startet z. B. einen Dienst. Dieses Verb ist das Gegenstück zu `Stop`.|Launch, Initiate, Boot|
|[Stop](/dotnet/api/System.Management.Automation.VerbsLifecycle.Stop) (sp)|Hiermit wird eine Aktivität beendet. Dieses Verb ist das Gegenstück zu `Start`.|End, Kill, Terminate, Cancel|
|[Submit](/dotnet/api/System.Management.Automation.VerbsLifecycle.Submit) (sb)|Hiermit wird eine Ressource zur Genehmigung übermittelt.|Posten|
|[Suspend](/dotnet/api/System.Management.Automation.VerbsLifecycle.Suspend) (ss)|Hiermit wird eine Aktivität angehalten. Das Cmdlet `Suspend-Service` hält z. B. einen Dienst an. Dieses Verb ist das Gegenstück zu `Resume`.|Anhalten|
|[Uninstall](/dotnet/api/System.Management.Automation.VerbsLifecycle.Uninstall) (us)|Hiermit wird eine Ressource an einem bestimmten Speicherort entfernt. Dieses Verb ist das Gegenstück zu `Install`.||
|[Unregister](/dotnet/api/System.Management.Automation.VerbsLifecycle.Unregister) (ur)|Hiermit wird der Eintrag für eine Ressource in einem Repository entfernt. Dieses Verb ist das Gegenstück zu `Register`.|Remove (Entfernen)|
|[Wait](/dotnet/api/System.Management.Automation.VerbsLifecycle.Wait) (w)|Hiermit wird ein Vorgang angehalten, bis ein angegebenes Ereignis eintritt. Das Cmdlet `Wait-Job` hält z. B. Vorgänge an, bis ein oder mehrere Hintergrundaufträge abgeschlossen sind.|Sleep, Pause|

## <a name="security-verbs"></a>Sicherheitsverben

PowerShell verwendet die Klasse [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity) zum Definieren von Aktionen in Bezug auf Sicherheit. In der folgenden Tabelle sind die meisten der definierten Verben aufgeführt.

|Verb (Alias)|Aktion|Zu vermeidende Synonyme|
|--------------------|------------|--------------|
|[Block](/dotnet/api/System.Management.Automation.VerbsSecurity.Block) (bl)|Hiermit wird der Zugriff auf eine Ressource eingeschränkt. Dieses Verb ist das Gegenstück zu `Unblock`.|Prevent, Limit, Deny|
|[Grant](/dotnet/api/System.Management.Automation.VerbsSecurity.Grant) (gr)|Hiermit wird der Zugriff auf eine Ressource ermöglicht. Dieses Verb ist das Gegenstück zu `Revoke`.|Allow, Enable|
|[Protect](/dotnet/api/System.Management.Automation.VerbsSecurity.Protect) (pt)|Hiermit wird eine Ressource vor Angriffen oder Verlusten geschützt. Dieses Verb ist das Gegenstück zu `Unprotect`.|Encrypt, Safeguard, Seal|
|[Revoke](/dotnet/api/System.Management.Automation.VerbsSecurity.Revoke) (rk)|Hiermit wird eine Aktion angegeben, die den Zugriff auf eine Ressource nicht zulässt. Dieses Verb ist das Gegenstück zu `Grant`.|Remove, Disable|
|[Unblock](/dotnet/api/System.Management.Automation.VerbsSecurity.Unblock) (ul)|Hiermit werden Einschränkungen für eine Ressource entfernt. Dieses Verb ist das Gegenstück zu `Block`.|Clear, Allow|
|[Unprotect](/dotnet/api/System.Management.Automation.VerbsSecurity.Unprotect) (up)|Hiermit werden Schutzvorrichtungen aus einer Ressource entfernt, die hinzugefügt wurden, um Angriffe oder Verluste zu verhindern. Dieses Verb ist das Gegenstück zu `Protect`.|Decrypt, Unseal|

## <a name="other-verbs"></a>Andere Verben

PowerShell verwendet die Klasse [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther) zum Definieren kanonischer Verbnamen, die nicht in eine bestimmte Verbnamenkategorie wie häufig verwendete Verben oder Kommunikations-, Daten-, Lebenszyklus- oder Sicherheitsverben passen.

|Verb (Alias)|Aktion|Zu vermeidende Synonyme|
|--------------------|------------|--------------|
|[Use](/dotnet/api/System.Management.Automation.VerbsOther.Use) (u)|Hiermit wird eine Ressource allein oder zusammen mit anderen Ressourcen für eine Aktion verwendet.||

## <a name="see-also"></a>Weitere Informationen

- [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)
- [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)
- [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData)
- [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)
- [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)
- [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)
- [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)
- [Cmdlet-Deklaration](./cmdlet-class-declaration.md)
- [Windows PowerShell-Programmiererhandbuch](../prog-guide/windows-powershell-programmer-s-guide.md)
- [Referenz zu Windows PowerShell](../windows-powershell-reference.md)
