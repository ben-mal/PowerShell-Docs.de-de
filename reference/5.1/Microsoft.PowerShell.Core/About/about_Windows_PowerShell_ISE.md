---
description: Beschreibt die Features und Systemanforderungen Windows PowerShell Integrated Scripting Environment (ISE).
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_ise?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_ISE
ms.openlocfilehash: ff543024d7c62c70217eeaf3ded192a5a24c4757
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388840"
---
# <a name="about-windows-powershell-ise"></a>Informationen zu Windows PowerShell ISE

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt die Features und Systemanforderungen Windows PowerShell Integrated Scripting Environment (ISE).

## <a name="long-description"></a>LANGE BESCHREIBUNG

Windows PowerShell ISE ist eine grafische Host Anwendung für Windows PowerShell.
In Windows PowerShell ISE können Sie Befehle ausführen und Skripts schreiben, testen und Debuggen, die auf einer einzigen Windows-basierten grafischen Benutzeroberfläche ausgeführt werden. Zu den Features gehören IntelliSense, mehrzeilige Bearbeitung, Vervollständigung mit der Tab-Taste, automatisches Speichern, Syntax Farben, selektive Ausführung, kontextabhängige Hilfe, Anzeige Befehl (Befehle in einem Fenster verfassen) und Unterstützung für Doppelbyte-Zeichensätze und von rechts nach links geschriebene Sprachen.

Windows PowerShell ISE ist ein hervorragendes Tool für Einsteiger. Die Registerkarte anzeigen Befehlsfenster und neuer Remote-PowerShell führt Sie durch Aufgaben, sodass Sie beim ersten Versuch erfolgreich sein können. Ausschnitte und Fehlerindikatoren helfen Ihnen beim Erlernen der Windows PowerShell-Sprache bei der Arbeit.

Erweiterte Benutzer können die ausgereiften Debuggingfunktionen, Add-ons und das Windows PowerShell ISE Objektmodell nutzen.

Neues in Windows PowerShell ISE in Windows PowerShell 4,0

In Windows PowerShell ISE werden zwei neue Features in Windows PowerShell 4,0 eingeführt.

- Windows PowerShell ISE unterstützt jetzt sowohl Windows PowerShell-Workflow-Debuggen als auch Remote Skript Debugging. Weitere Informationen finden Sie unter about_Debuggers.

- Die IntelliSense-Unterstützung wurde für Windows PowerShell-DSC-Anbieter und -Konfigurationen hinzugefügt.

## <a name="starting-windows-powershell-ise"></a>Starten Windows PowerShell ISE

Windows PowerShell ISE ist installiert, aktiviert und bereit für die Verwendung in allen unterstützten Versionen von Windows.

- Geben Sie in Windows 8.1, Windows 8, Windows Server 2012 R2 und Windows Server 2012 auf der Start Seite PowerShell_ISE ein, und klicken Sie dann auf PowerShell_ISE oder Windows PowerShell ISE.

- Klicken Sie unter Windows Server 2012 R2 und Windows Server 2012 in Server-Manager im Menü Extras auf Windows PowerShell ISE.

- In früheren Versionen von Windows, klicken Sie auf Start, alle Programme, Zubehör, Windows PowerShell, und klicken Sie dann auf Windows PowerShell ISE.

- Geben Sie in einer Windows PowerShell-Konsole Cmd.exe oder das Feld Ausführen oder suchen in Windows "PowerShell_ise.exe" ein. Sie können auch die Befehlszeilenparameter verwenden, einschließlich des NoProfile-Schalters. Weitere Informationen finden Sie unter [PowerShell_ISE.exe-Konsolen Hilfe](about_powershell_ise_exe.md).

## <a name="running-interactive-commands"></a>Ausführen interaktiver Befehle

Sie können einen beliebigen Windows PowerShell-Ausdruck oder-Befehl in Windows PowerShell ISE ausführen. Sie können Cmdlets, Anbieter, Snap-Ins und Module wie in der Windows PowerShell-Konsole verwenden.

Sie können interaktive Befehle in den Konsolen Bereich eingeben oder einfügen. Zum Ausführen der Befehle können Sie Schaltflächen, Menü Elemente und Tastenkombinationen verwenden.

Mit der mehrzeiligen Bearbeitungsfunktion können Sie mehrere Codezeilen gleichzeitig in den Konsolen Bereich eingeben oder einfügen. Wenn Sie die nach-oben-Taste drücken, um den vorherigen Befehl abzurufen, werden alle Zeilen im Befehl zurückgerufen. Wenn Sie Befehle eingeben, drücken Sie UMSCHALT + EINGABETASTE, um eine neue leere Zeile unter der aktuellen Zeile anzuzeigen.

## <a name="viewing-output"></a>Anzeigen der Ausgabe

Die Ergebnisse von Befehlen und Skripts werden im Konsolenfenster angezeigt. Sie können die Ergebnisse im Konsolen Bereich mithilfe von Tastenkombinationen oder der Schaltfläche Kopieren auf der Symbolleiste verschieben oder kopieren, und Sie können die Ergebnisse im Skript Bereich oder in den Konsolen Bereichen oder anderen Programmen einfügen. Um den Konsolen Bereich zu löschen, klicken Sie auf die Schaltfläche "Ausgabebereich löschen", oder geben Sie einen der folgenden Befehle ein:

```
Clear-Host
cls
```

## <a name="writing-scripts-and-functions"></a>Schreiben von Skripts und Funktionen

Im Skript Bereich können Sie Skripts öffnen, verfassen, bearbeiten und ausführen. Im Skript Bereich können Sie Skripts mithilfe von Schaltflächen und Tastenkombinationen bearbeiten. Zwischen dem Skript Bereich und dem Konsolen Bereich können Sie auch Text kopieren, Ausschneiden und einfügen.

Sie können das Feature für die selektive Durchführung verwenden, um ein Skript vollständig oder teilweise auszuführen. Um einen Teil eines Skripts auszuführen, wählen Sie den Text aus, den Sie ausführen möchten, und klicken Sie dann auf die Schaltfläche Auswahl ausführen, oder drücken Sie F8. Standardmäßig führt F8 die aktuelle Zeile aus.

Erweiterte Bearbeitungsfunktionen umfassen Klammern, erweitern/reduzieren, Zeilennummern, Fehlerindikatoren, Blockbearbeitung und Einzug, umfangreiche Kopie und Fall Konvertierung.

## <a name="getting-help"></a>Abrufen von Hilfe

Windows PowerShell ISE enthält Hilfe Themen, in denen die Verwendung beschrieben wird. Außerdem können Sie über die Skript-und Befehls Bereiche auf alle installierten Hilfedateien zugreifen.

Windows PowerShell ISE unterstützt auch die kontextbezogene Hilfe. Um Hilfe zu einem bestimmten Cmdlet, Anbieter oder Schlüsselwort zu erhalten, platzieren Sie den Cursor in den Namen des Elements, und drücken Sie F1. Drücken Sie zum Durchsuchen der Hilfe Themen F1, und geben Sie den Suchbegriff ein.

Um die Hilfe Themen auf dem Computer zu aktualisieren, verwenden Sie das Hilfe Element Windows PowerShell aktualisieren im Menü Hilfe. Dieses Element aktualisiert die Hilfe für die Module in der aktuellen Sitzung in der aktuellen Benutzeroberflächen Kultur. Dies entspricht dem Ausführen des Update-Help Cmdlets ohne Parameter. Um die Hilfe für die Cmdlets zu aktualisieren, die in Windows PowerShell enthalten sind, starten Sie Windows PowerShell ISE mit der Option "als Administrator ausführen".

Sie können auch die Cmdlets "Get-Help", "Save-Help" und "Update-Help" in Windows PowerShell ISE verwenden, genauso wie Sie es in der Windows PowerShell-Konsole verwenden. In Windows PowerShell ISE zeigt die Hilfe Funktion jedoch das gesamte Hilfethema, nicht jeweils eine Seite an.

## <a name="debugging-scripts"></a>Debugskripts

Mit dem Windows PowerShell ISE Debugger können Sie ein Windows PowerShell-Skript oder eine Windows PowerShell-Funktion Debuggen. Wenn Sie ein Skript Debuggen, können Sie mit Menü Elementen und Tastenkombinationen viele der Aufgaben ausführen, die Sie auch in der Windows PowerShell-Konsole ausführen würden. Um z. b. einen Zeilen Haltepunkt in einem Skript festzulegen, klicken Sie mit der rechten Maustaste auf die Codezeile, und klicken Sie dann auf Breakpoint umschalten.

Beim Durchlaufen eines Skripts während des Debuggens zeigt das Debugger highheller genau an, welcher Teil des Befehls ausgeführt wird, und öffnet automatisch Dateien, die aufgerufene Funktionen und Skripts enthalten.

Standardmäßig legt das Menü Element Haltepunkt umschalten einen Haltepunkt auf einer ganzen Zeile in einem Skript fest, Sie können jedoch einen Haltepunkt für eine Variable oder einen Befehlsnamen festlegen.
Sie können auch einen Haltepunkt in einem Befehl nach Zeilen-und Spaltennummer festlegen, um das Debuggen langer Pipeline Befehle zu vereinfachen.

Häufig können Sie Syntax Fehler in einem Skript Debuggen, indem Sie die Skriptdatei in Windows PowerShell ISE öffnen. Mit den Fehlerindikatoren werden Syntax Fehler identifiziert, und mit den Gliederungs Features können Sie Teile des Skripts reduzieren, um sich auf die Probleme zu konzentrieren.

Sie können auch die Windows PowerShell-Debugger-Cmdlets im Befehlsbereich genauso wie in der-Konsole verwenden.

## <a name="running-remote-commands"></a>Ausführen von Remotebefehlen

Die neue Registerkarte "Remote-PowerShell-Registerkarte" erleichtert das Einrichten einer permanenten, vom Benutzer verwalteten Windows PowerShell-Sitzung ("PSSession") auf dem lokalen Computer oder einem Remote Computer. Der Befehl öffnet ein Popup Fenster, in dem Sie zur Eingabe eines Computer namens aufgefordert werden, und für das Benutzerkonto, das über die Berechtigung zum Ausführen von Befehlen auf dem Remote Computer verfügt.

## <a name="customizing-the-view"></a>Anpassen der Ansicht

Mit Windows PowerShell ISE Features können Sie den Konsolen Bereich und den Skript Bereich verschieben und die Größe ändern. Sie können beide Bereiche anzeigen und ausblenden, und Sie können die Textgröße in allen Bereichen ändern.

Sie können das Fenster Optionen auch verwenden, um die Darstellung und den Betrieb von Windows PowerShell ISE anzupassen. Außerdem verfügt Windows PowerShell ISE über eine benutzerdefinierte Host Variable, $psISE, die Sie zum Anpassen von Windows PowerShell ISE verwenden können, einschließlich Hinzufügen von Menüs und Menü Elementen.

## <a name="windows-powershell-ise-profile"></a>Windows PowerShell ISE Profil

Windows PowerShell ISE über ein eigenes Windows PowerShell-Profil verfügt, Microsoft.PowerShellISE_profile.ps1. In diesem Profil können Sie Funktionen, Aliase, Variablen und Befehle speichern, die Sie in Windows PowerShell ISE verwenden.

Elemente in den Windows PowerShell allhosts-Profilen (CurrentUser \\ allhosts und ALLUSERS \\ allhosts) sind ebenfalls in Windows PowerShell ISE verfügbar, genauso wie Sie in jedem Windows PowerShell-Host Programm vorhanden sind. Allerdings sind die Elemente in den Windows PowerShell-Konsolen Profilen in Windows PowerShell ISE nicht verfügbar.

Anweisungen zum Verschieben und erneuten Konfigurieren ihrer Profile finden Sie in Windows PowerShell ISE Hilfe und in about_Profiles.

## <a name="notes"></a>HINWEISE

Windows PowerShell ISE ist eine optionale Windows-Funktion, die standardmäßig auf Client-und Serverversionen von Windows aktiviert ist. Um Windows PowerShell ISE in Client Versionen von Windows zu aktivieren und zu deaktivieren, verwenden Sie in der Systemsteuerung die Option Windows-Funktionen ein-oder ausschalten. Um Windows PowerShell ISE in Serverversionen von Windows zu aktivieren und zu deaktivieren, verwenden Sie den Assistenten zum Hinzufügen von Rollen und Features in Server-Manager.

Da Windows PowerShell ISE eine Benutzeroberfläche erfordert, funktioniert es nicht bei Server Core-Installationen von Windows Server. Wenn Sie jedoch das Windows PowerShell ISE Feature hinzufügen, wird die Installation automatisch auf den Server mit grafischer Benutzeroberfläche konvertiert.

Windows PowerShell ISE beruht auf Windows Presentation Foundation (WPF).
Wenn die grafischen Elemente von Windows PowerShell ISE auf dem System nicht ordnungsgemäß gerendert werden, können Sie das Problem beheben, indem Sie die Grafik Rendering-Einstellungen für die WPF-Hardware Beschleunigung in Ihrem System hinzufügen oder anpassen. Weitere Informationen finden Sie unter [Registrierungseinstellungen für das Rendern von Grafiken](/dotnet/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings).

## <a name="see-also"></a>SIEHE AUCH

[about_Debuggers](about_Debuggers.md)

[about_Profiles](about_Profiles.md)

[about_Updatable_Help](about_Updatable_Help.md)

[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

[Get-IseSnippet](xref:ISE.Get-IseSnippet)

[Import-IseSnippet](xref:ISE.Import-IseSnippet)

[New-IseSnippet](xref:ISE.New-IseSnippet)

[Save-Help](xref:Microsoft.PowerShell.Core.Save-Help)

[Show-Command](xref:Microsoft.PowerShell.Utility.Show-Command)

[Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)
