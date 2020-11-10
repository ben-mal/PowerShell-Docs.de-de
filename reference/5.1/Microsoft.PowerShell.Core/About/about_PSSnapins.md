---
description: Beschreibt Windows PowerShell-Snap-Ins und zeigt, wie Sie verwendet und verwaltet werden.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSnapins
ms.openlocfilehash: 494b3275e4fe8a3aacdc358317950542962957cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388891"
---
# <a name="about-pssnapins"></a>Informationen zu pssnapins

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt Windows PowerShell-Snap-Ins und zeigt, wie Sie verwendet und verwaltet werden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Ein Windows PowerShell-Snap-in ist eine Microsoft .NET FrameworkAssembly, die Windows PowerShell-Anbieter und- \/ Cmdlets oder-Cmdlets enthält. Windows PowerShell umfasst eine Reihe von einfachen Snap-Ins, aber Sie können die Leistungsfähigkeit und den Wert von Windows PowerShell erweitern, indem Sie Snap-Ins hinzufügen, die Anbieter und Cmdlets enthalten, die Sie erstellen oder von anderen Benutzern erhalten.

Wenn Sie ein Snap-in hinzufügen, sind die darin enthaltenen Cmdlets und Anbieter sofort für die Verwendung in der aktuellen Sitzung verfügbar, aber die Änderung wirkt sich nur auf die aktuelle Sitzung aus.

Um das Snap-in zu allen zukünftigen Sitzungen hinzuzufügen, speichern Sie es in Ihrem Windows PowerShell-Profil. Sie können auch das Cmdlet "Export-Console" verwenden, um die Snap-in-Namen in einer Konsolen Datei zu speichern und Sie dann in zukünftigen Sitzungen zu verwenden. Sie können sogar mehrere Konsolen Dateien mit jeweils einem anderen Satz von Snap-Ins speichern.

Hinweis: Windows PowerShell-Snap-Ins (pssnapins) stehen zur Verwendung in Windows PowerShell 3,0 und Windows PowerShell 2,0 zur Verfügung. Sie werden möglicherweise in nachfolgenden Versionen geändert oder sind nicht verfügbar. Verwenden Sie zum Packen von Windows PowerShell-Cmdlets und Anbietern Module. Weitere Informationen zum Erstellen von Modulen und zum Umrechnen von Snap-Ins in Module finden Sie unter [Schreiben eines Windows PowerShell-Moduls](/powershell/scripting/developer/module/writing-a-windows-powershell-module).

### <a name="finding-snap-ins"></a>Suchen von Snap-Ins

Um eine Liste der Windows PowerShell-Snap-Ins auf dem Computer zu erhalten, geben Sie Folgendes ein:

```powershell
Get-PSSnapin
```

Um das Snap-in für jeden Windows PowerShell-Anbieter zu erhalten, geben Sie Folgendes ein:

```powershell
Get-PSProvider | Format-List name, pssnapin
```

Um eine Liste der Cmdlets in einem Windows PowerShell-Snap-in zu erhalten, geben Sie Folgendes ein:

```powershell
Get-Command -Module <snap-in_name>
```

### <a name="installing-a-snap-in"></a>Installieren eines Snap-Ins

Die integrierten Snap-Ins werden im System registriert und der Standard Sitzung beim Starten von Windows PowerShell hinzugefügt. Sie müssen jedoch Snap-Ins registrieren, die Sie erstellen oder von anderen erhalten, und dann die Snap-Ins zur Sitzung hinzufügen.

### <a name="registering-a-snap-in"></a>Registrieren eines Snap-Ins

Bei einem Windows PowerShell-Snap-in handelt es sich um ein Programm, das in einer .NET Framework Sprache geschrieben ist, die in eine DLL-Datei kompiliert wird. Wenn Sie die Anbieter und Cmdlets in einem Snap-in verwenden möchten, müssen Sie zuerst das Snap-in registrieren (es der Registrierung hinzufügen).

Die meisten Snap-Ins enthalten ein Installationsprogramm (eine exe-oder MSI-Datei), das die DLL-Datei für Sie registriert. Wenn Sie jedoch ein Snap-in als DLL-Datei erhalten, können Sie es auf Ihrem System registrieren. Weitere Informationen finden Sie unter [Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).

Geben Sie Folgendes ein, um alle registrierten Snap-Ins auf Ihrem System zu erhalten oder um zu überprüfen, ob ein Snap-in registriert ist:

```powershell
Get-PSSnapin -registered
```

### <a name="adding-the-snap-in-to-the-current-session"></a>Hinzufügen des Snap-Ins zur aktuellen Sitzung

Verwenden Sie das Cmdlet "Add-PsSnapin", um der aktuellen Sitzung ein registriertes Snap-in hinzuzufügen. Wenn Sie z. b. der Sitzung das Microsoft SQL Server-Snap-in hinzufügen möchten, geben Sie Folgendes ein:

```powershell
Add-PSSnapin sql
```

Nachdem der Befehl abgeschlossen wurde, sind die Anbieter und Cmdlets im Snap-in in der Sitzung verfügbar. Sie sind jedoch nur in der aktuellen Sitzung verfügbar, sofern Sie Sie nicht speichern.

### <a name="saving-the-snap-ins"></a>Speichern der Snap-Ins

Wenn Sie in zukünftigen Windows PowerShell-Sitzungen ein Snap-in verwenden möchten, fügen Sie dem Windows PowerShell-Profil den Befehl Add-PsSnapin hinzu. Oder exportieren Sie die Snap-in-Namen in eine Konsolen Datei.

Wenn Sie den Add-PSSnapin Befehl zu Ihrem Profil hinzufügen, steht er in allen zukünftigen Windows PowerShell-Sitzungen zur Verfügung. Wenn Sie die Namen der Snap-Ins in Ihrer Sitzung exportieren, können Sie die Exportdatei nur verwenden, wenn Sie die Snap-Ins benötigen.

Um den Add-PsSnapin Befehl dem Windows PowerShell-Profil hinzuzufügen, öffnen Sie das Profil, fügen Sie den Befehl ein, oder geben Sie ihn ein, und speichern Sie dann das Profil. Weitere Informationen finden Sie unter „about_Profiles“.

Um die Snap-Ins aus einer Sitzung in der Konsolen Datei (. psc1) zu speichern, verwenden Sie das Cmdlet "Export-Console". Wenn Sie z. b. die Snap-Ins in der aktuellen Sitzungs Konfiguration in der newconsole. psc1-Datei im aktuellen Verzeichnis speichern möchten, geben Sie Folgendes ein:

```powershell
Export-Console NewConsole
```

Weitere Informationen finden Sie unter Export-Console.

### <a name="opening-windows-powershell-with-a-console-file"></a>Öffnen von Windows PowerShell mit einer Konsolen Datei

Um eine Konsolen Datei zu verwenden, die das-Snap-in enthält, starten Sie Windows PowerShell (PowerShell.exe) über die Eingabeaufforderung in Cmd.exe oder in einer anderen Windows PowerShell-Sitzung. Verwenden Sie den Parameter PsConsoleFile, um die Konsolen Datei anzugeben, in der das Snap-in enthalten ist. Beispielsweise wird mit dem folgenden Befehl Windows PowerShell mit der newconsole. psc1-Konsolen Datei gestartet:

```powershell
PowerShell.exe -psconsolefile NewConsole.psc1
```

Die Anbieter und Cmdlets im Snap-in sind jetzt für die Verwendung in der Sitzung verfügbar.

### <a name="removing-a-snap-in"></a>Entfernen eines Snap-Ins

Verwenden Sie das Cmdlet "Remove-PsSnapin", um ein Windows PowerShell-Snap-in aus der aktuellen Sitzung zu entfernen. Wenn Sie z. b. das SQL Server-Snap-in aus der aktuellen Sitzung entfernen möchten, geben Sie Folgendes ein:

```powershell
Remove-PSSnapin sql
```

Mit diesem Cmdlet wird das Snap-in aus der Sitzung entfernt. Das Snap-in ist weiterhin geladen, die Anbieter und Cmdlets, die es unterstützt, sind jedoch nicht mehr verfügbar.

### <a name="built-in-commands"></a>integrierte Befehle

In Windows PowerShell 2,0 und älteren Host Programmen in Windows PowerShell 3,0 und höher werden die integrierten Befehle, die mit Windows PowerShell installiert werden, in Snap-Ins verpackt, die automatisch zu jeder Windows PowerShell-Sitzung hinzugefügt werden.

Beginnend mit Windows PowerShell 3,0 in Host Programmen im neueren Stil, die Sitzungen mithilfe der initialsessionstate. CreateDefault2-Methode starten, werden die integrierten Befehle in Modulen verpackt. Die Ausnahme ist "Microsoft. PowerShell. Core", die immer als Snap-in angezeigt wird. Das Core-Snap-in ist standardmäßig in jeder Sitzung enthalten. Die integrierten Module werden automatisch bei der ersten Verwendung geladen.

Hinweis: Remote Sitzungen, einschließlich Sitzungen, die mit dem Cmdlet "New-PSSession" gestartet werden, sind Sitzungen älterer Sitzungen, in denen die integrierten Befehle in Snap-Ins verpackt werden.

Die folgenden Snap-Ins (oder Module) werden mit Windows PowerShell installiert.

- Microsoft. PowerShell. Core: enthält Anbieter und Cmdlets, die zum Verwalten der grundlegenden Features von Windows PowerShell verwendet werden. Es enthält die Dateisystem-, Registrierungs-, Alias-, Umgebungs-, Funktions-und Variablen Anbieter sowie grundlegende Cmdlets wie "Get-Help", "Get-Command" und "Get-History".

- Microsoft. PowerShell. Host: enthält Cmdlets, die vom Windows PowerShell-Host verwendet werden, z. b. Start-Transcript und das Abbrechen von Skripts.

- Microsoft. PowerShell. Management: enthält Cmdlets, z. b. Get-Service und Get-ChildItem, die zum Verwalten von Windows-basierten Features verwendet werden.

- Microsoft. PowerShell. Security: enthält den Zertifikat Anbieter und die Cmdlets, die zum Verwalten der Windows PowerShell-Sicherheit verwendet werden, z. b. "Get-ACL", "Get-AuthenticodeSignature" und "ConvertTo-SecureString".

- Microsoft. PowerShell. Utility: enthält Cmdlets, die zum Bearbeiten von Objekten und Daten verwendet werden, z. b. "Get-Member", "Write-Host" und "Format-List".

- Microsoft. WSMAN. Management: enthält den WSMAN-Anbieter und Cmdlets, die den Windows-Remoteverwaltung Dienst verwalten, z. b. Connect-WSMan und enable-wsmankredssp.

## <a name="logging-snap-in-events"></a>Protokollieren von Snap-in-Ereignissen

Ab Windows PowerShell 3,0 können Sie Ausführungs Ereignisse für die Cmdlets in Windows PowerShell-Modulen und-Snap-Ins aufzeichnen, indem Sie die logpipelineexecutiondetails-Eigenschaft von Modulen und Snap-Ins auf "true" festlegen. Weitere Informationen finden Sie unter [about_EventLogs](about_EventLogs.md).

## <a name="see-also"></a>SIEHE AUCH

[Add-PSSnapin](xref:Microsoft.PowerShell.Core.Add-PSSnapin)

[Get-PSSnapin](xref:Microsoft.PowerShell.Core.Get-PSSnapin)

[Remove-PSSnapIn](xref:Microsoft.PowerShell.Core.Remove-PSSnapin)

[Export-Console](xref:Microsoft.PowerShell.Core.Export-Console)

[Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)

[about_Profiles](about_Profiles.md)

[about_Modules](about_Modules.md)

## <a name="keywords"></a>Keywords

about_Snapins, about_Snap_ins, about_Snap-ins
