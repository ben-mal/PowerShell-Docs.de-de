---
description: Beschreibt die Gruppenrichtlinie Einstellungen für PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: 1533908be91703efd8509653b30d30de6b7c4a84
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221575"
---
# <a name="about-group-policy-settings"></a>Informationen zu Gruppenrichtlinie Einstellungen

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt die Gruppenrichtlinie Einstellungen für PowerShell.

## <a name="long-description"></a>Lange Beschreibung

PowerShell enthält Gruppenrichtlinie Einstellungen, mit deren Hilfe Sie konsistente Konfigurationswerte für Windows-Computer in einer Unternehmensumgebung definieren können.

Die PowerShell-Gruppenrichtlinie Einstellungen befinden sich in den folgenden Gruppenrichtlinie Pfaden:

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

Die Gruppenrichtlinien Einstellungen im Benutzer Konfigurations Pfad haben Vorrang vor den Gruppenrichtlinie Einstellungen im Computer Konfigurations Pfad.

Nachdem Sie die Vorlagen installiert haben, können Sie diese Einstellungen im Gruppenrichtlinie-Editor ( `gpedit.msc` ) bearbeiten.

Die Richtlinien lauten wie folgt:

- Modul Protokollierung aktivieren: legt die **logpipelineexecutiondetails** -Eigenschaft von Modulen fest.
- Protokollierung von PowerShell-Skriptblöcken: Aktiviert die ausführliche Protokollierung aller PowerShell-Skripts.
- Skriptausführung aktivieren: Legt die PowerShell-Ausführungsrichtlinie fest.
- PowerShell-Aufzeichnung aktivieren: ermöglicht die Erfassung der Ein- und Ausgabe von PowerShell-Befehlen in textbasierten Transkripten.
- Legen Sie den Standard Quellpfad für fest `Update-Help` : legt die Quelle für die aktualisierbare Hilfe zu einem Verzeichnis, nicht zum Internet, fest.

Weitere Informationen zum Abrufen anderer Vorlagen und zum Konfigurieren der Gruppenrichtlinie finden [Sie unter Erstellen und Verwalten des zentralen Speicher für Gruppenrichtlinie administrative Vorlagen in Windows][gpstore].

## <a name="turn-on-module-logging"></a>Aktivieren der Modul Protokollierung

Mit der Richtlinien Einstellung " **Modul Protokollierung** aktivieren" wird die Protokollierung für ausgewählte PowerShell-Module aktiviert. Die Einstellung ist in allen Sitzungen auf allen betroffenen Computern wirksam.

Wenn Sie diese Richtlinien Einstellung aktivieren und ein oder mehrere Module angeben, werden Pipeline Ausführungs Ereignisse für die angegebenen Module im Windows PowerShell-Protokoll Ereignisanzeige aufgezeichnet.

Wenn Sie diese Richtlinien Einstellung deaktivieren, wird die Protokollierung von Ausführungs Ereignissen für alle PowerShell-Module deaktiviert.

Wenn diese Richtlinien Einstellung nicht konfiguriert ist, bestimmt die **logpipelineexecutiondetails** -Eigenschaft jedes Moduls, ob die Ausführungs Ereignisse eines Moduls protokolliert werden. Standardmäßig ist die **logpipelineexecutiondetails** -Eigenschaft aller Module auf false festgelegt.

Verwenden Sie das folgende Befehls Format, um die Modul Protokollierung für ein Modul zu aktivieren. Das Modul muss in die Sitzung importiert werden, und die Einstellung ist nur in der aktuellen Sitzung gültig.

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

Fügen Sie zum Aktivieren der Modul Protokollierung für alle Sitzungen auf einem bestimmten Computer die vorherigen Befehle zum PowerShell-Profil "alle Benutzer" ( `$Profile.AllUsersAllHosts` ) hinzu.

Weitere Informationen zur Modul Protokollierung finden Sie unter [about_Modules](about_Modules.md).

## <a name="turn-on-powershell-script-block-logging"></a>Aktivieren der PowerShell-Skriptblock Protokollierung

Die Richtlinien Einstellung **PowerShell-Skript Block Protokollierung aktivieren** ermöglicht das Protokollieren aller PowerShell-Skript Eingaben im Ereignisprotokoll Microsoft-Windows-PowerShell/Operational. Wenn Sie diese Richtlinien Einstellung aktivieren, protokolliert PowerShell Core die Verarbeitung von Befehlen, Skript Blöcken, Funktionen und Skripts, unabhängig davon, ob Sie interaktiv aufgerufen werden, oder durch Automatisierung.

Wenn Sie diese Richtlinieneinstellung deaktivieren, ist das Protokollieren von PowerShell-Skript-Eingaben deaktiviert. Wenn Sie die Protokollierung von Skriptblockaufrufen aktivieren, protokolliert PowerShell zusätzlich Protokollereignisse, wenn ein Befehl, ein Skriptblock, eine Funktion oder Skriptstarts oder -stops aufgerufen werden. Das Aktivieren der Protokollierung von Aufrufen führt zu einer großen Anzahl von Ereignisprotokollen.

## <a name="turn-on-script-execution"></a>Skriptausführung aktivieren

Mit der Richtlinien Einstellung **Skriptausführung aktivieren** wird die Ausführungs Richtlinie für Computer und Benutzer festgelegt, die bestimmt, welche Skripts ausgeführt werden dürfen.

Wenn Sie die Richtlinien Einstellung aktivieren, können Sie zwischen den folgenden Richtlinien Einstellungen wählen.

- **Nur signierte Skripts zulassen** : Skripts können nur ausgeführt werden, wenn Sie von einem vertrauenswürdigen Herausgeber signiert wurden. Diese Richtlinien Einstellung entspricht der AllSigned-Ausführungs Richtlinie.

- **Lokale Skripts und Remote signierte Skripts zulassen** ermöglicht das Ausführen aller lokalen Skripts. Skripts, die aus dem Internet stammen, müssen von einem vertrauenswürdigen Herausgeber signiert werden. Diese Richtlinien Einstellung entspricht der RemoteSigned-Ausführungs Richtlinie.

- **Alle Skripts zulassen** ermöglicht das Ausführen aller Skripts. Diese Richtlinien Einstellung entspricht der uneingeschränkten Ausführungs Richtlinie.

Wenn Sie diese Richtlinien Einstellung deaktivieren, dürfen keine Skripts ausgeführt werden. Diese Richtlinien Einstellung entspricht der eingeschränkten Ausführungs Richtlinie.

Wenn Sie diese Richtlinien Einstellung deaktivieren oder nicht konfigurieren, bestimmt die Ausführungs Richtlinie, die vom Cmdlet für den Computer oder Benutzer festgelegt wird, `Set-ExecutionPolicy` ob Skripts ausgeführt werden dürfen. Der Standardwert ist "Restricted".

Weitere Informationen finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).

## <a name="turn-on-powershell-transcription"></a>Aktivieren der PowerShell-Aufzeichnung

Mithilfe der Richtlinien Einstellung **PowerShell** -Aufzeichnung aktivieren können Sie die Eingabe und die Ausgabe von PowerShell Core-Befehlen in textbasierte Transkriptionen aufzeichnen. Wenn Sie diese Richtlinien Einstellung aktivieren, aktiviert PowerShell Core die Protokollierungs Protokollierung für PowerShell Core und alle anderen Anwendungen, die die PowerShell-Kern-Engine nutzen. Standardmäßig zeichnet PowerShell Core die Transkriptions Ausgabe im Verzeichnis "eigene Dateien" der einzelnen Benutzer auf, wobei der Dateiname "PowerShell_transcript" sowie der Computername und die Startzeit enthalten.
Die Aktivierung dieser Richtlinie entspricht dem Aufrufen des Start-Transcript Cmdlets für jede PowerShell-Kern Sitzung.

Wenn Sie diese Richtlinien Einstellung deaktivieren, ist die Protokollierungs Protokollierung von PowerShell-basierten Anwendungen standardmäßig deaktiviert, obwohl das transkripting weiterhin über das Cmdlet "Start-Transcript" aktiviert werden kann.

Wenn Sie die Einstellung OutputDirectory verwenden, um die Protokollierungs Protokollierung an einem freigegebenen Speicherort zu aktivieren, achten Sie darauf, den Zugriff auf dieses Verzeichnis einzuschränken, um zu verhindern, dass Benutzer die Protokolle anderer Benutzer oder Computer anzeigen.

## <a name="set-the-default-source-path-for-update-help"></a>Standard Quellpfad für Update-Help festlegen

Die Richtlinien Einstellung **Standard Quellpfad für Update-Hilfe festlegen** legt einen Standardwert für den **SourcePath** -Parameter des `Update-Help` Cmdlets fest.
Diese Einstellung verhindert, dass Benutzer das `Update-Help` Cmdlet zum Herunterladen der Hilfedateien aus dem Internet verwenden.

> [!NOTE]
> Diese Gruppenrichtlinie Einstellung wird unter **Computer Konfiguration** und **Benutzerkonfiguration** angezeigt. Allerdings ist nur die Einstellung Gruppenrichtlinie unter **Computer Konfiguration** wirksam. Die Gruppenrichtlinie Einstellung unter **Benutzerkonfiguration** wird ignoriert.

Mit dem- `Update-Help` Cmdlet werden die neuesten Hilfedateien für PowerShell-Module heruntergeladen und installiert und auf dem Computer installiert. Standardmäßig `Update-Help` lädt neue Hilfedateien von einem durch das Modul angegebenen Internet Speicherort herunter.

Sie können das `Save-Help` Cmdlet jedoch verwenden, um die neuesten Hilfedateien an einen Dateisystem Speicherort (z. b. eine Netzwerkfreigabe) herunterzuladen. verwenden Sie dann das `Update-Help` Cmdlet, um die Hilfedateien vom Dateisystem Speicherort zu erhalten und auf dem Computer zu installieren. Der **SourcePath** -Parameter des `Update-Help` Cmdlets gibt den Speicherort des Dateisystems an.

Durch die Angabe eines Standardwerts für den **SourcePath** -Parameter fügt diese Gruppenrichtlinie Einstellung allen Befehlen implizit den **SourcePath** -Parameter hinzu `Update-Help` . Benutzer können den angegebenen Dateisystem Speicherort, der als Standardwert angegeben ist, überschreiben, indem Sie einen anderen Dateisystem Speicherort eingeben.
Der **SourcePath** -Parameter kann jedoch nicht aus dem `Update-Help` Befehl entfernt werden.

Wenn Sie diese Richtlinien Einstellung aktivieren, können Sie einen Standardwert für den **SourcePath** -Parameter angeben. Geben Sie einen Dateisystem Speicherort ein.

Wenn diese Richtlinien Einstellung deaktiviert oder nicht konfiguriert ist, gibt es keinen Standardwert für den **SourcePath** -Parameter des `Update-Help` Cmdlets. Benutzer können die Hilfe aus dem Internet oder von einem beliebigen Dateisystem Speicherort herunterladen.

Weitere Informationen hierzu finden Sie unter [about_Updatable_Help](about_Updatable_Help.md).

## <a name="keywords"></a>Keywords

about_Group_Policies about_GroupPolicy

## <a name="see-also"></a>Weitere Informationen:

[about_Execution_Policies](about_Execution_Policies.md)

[about_Modules](about_Modules.md)

[about_Updatable_Help](about_Updatable_Help.md)

[Get-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)

[Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)

[Save-Help](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759
