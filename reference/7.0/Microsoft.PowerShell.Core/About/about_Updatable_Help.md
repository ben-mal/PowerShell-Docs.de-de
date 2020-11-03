---
description: Beschreibt das aktualisierbare Hilfesystem in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_updatable_help?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Updatable_Help
ms.openlocfilehash: e49881b9f051cc176cae72f43ac6c7040c03f0c8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222412"
---
# <a name="about-updatable-help"></a>Informationen zur aktualisierbaren Hilfe

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt das aktualisierbare Hilfesystem in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

PowerShell bietet verschiedene Möglichkeiten, auf die aktuellsten Hilfe Themen für PowerShell-Cmdlets und-Konzepte zuzugreifen.

Das aktualisierbare Hilfesystem, das in PowerShell 3,0 eingeführt wurde, soll sicherstellen, dass Sie immer über die neuesten Hilfe Themen auf dem lokalen Computer verfügen, damit Sie Sie in der Befehlszeile lesen können. Es erleichtert das herunterladen und Installieren von Hilfedateien und das Aktualisieren, wenn neuere Hilfedateien verfügbar werden.

Zum Bereitstellen der aktualisierten Hilfe für mehrere Computer in einem Unternehmen und für Computer, die keinen Internet Zugriff haben, können Sie mit der aktualisierbaren Hilfe Hilfedateien in ein Dateisystem Verzeichnis oder eine Dateifreigabe herunterladen und dann die Hilfedateien aus der Dateifreigabe installieren.

In PowerShell 4,0 wird die **helpinfouri** -Eigenschaft über Windows PowerShell-Remoting beibehalten, wodurch die Verwendung von Modulen möglich ist, die `Save-Help` auf einem Remote Computer installiert sind, aber nicht unbedingt auf dem lokalen Computer installiert sind. Sie können ein **psmoduleinfo** -Objekt auf einem Datenträger oder einem Wechselmedium (z. b. einem USB-Laufwerk) speichern, indem Sie `Export-Clixml` auf einem Computer ausführen, der nicht über Internet Zugriff verfügt, das **psmoduleinfo** -Objekt auf einem Computer mit Internet Zugriff importieren und dann `Save-Help` auf dem **psmoduleinfo** -Objekt ausgeführt wird. Die gespeicherte Hilfe kann mithilfe von Wechselmedien auf den Remote Computer und den getrennten Computer kopiert und dann durch Ausführen von installiert werden `Update-Help` . Mit diesen Verbesserungen bei `Save-Help` der-Funktionalität können Sie die Hilfe auf Computern installieren, die ohne Netzwerk Zugriff sind. Ein Beispiel für die Verwendung der neuen `Save-Help` Funktionalität finden Sie unter Vorgehens [Weise beim Aktualisieren der Hilfe aus einer Dateifreigabe](#how-to-update-help-from-a-file-share) in diesem Thema.

Die aktualisierbare Hilfe unterstützt auch den Online Zugriff auf die neuesten Hilfe Themen und die grundlegende Hilfe für Cmdlets, auch wenn keine Hilfedateien auf dem Computer vorhanden sind.

PowerShell 3,0 enthält keine Hilfedateien. Sie können das Feature "aktualisierbare Hilfe" verwenden, um die Hilfedateien für alle Befehle zu installieren, die standardmäßig in PowerShell und für alle Windows-Module enthalten sind.

## <a name="updatable-help-cmdlets"></a>Aktualisierbare Help-Cmdlets

- `Update-Help`: Lädt die neuesten Hilfedateien aus dem Internet oder einer Dateifreigabe herunter und installiert Sie auf dem lokalen Computer.

- `Save-Help`: Lädt die neuesten Hilfedateien aus dem Internet herunter und speichert Sie in einem Dateisystem Verzeichnis oder einer Dateifreigabe. Verwenden Sie, um die Hilfedateien auf Computern zu installieren `Update-Help` .

- `Get-Help`: Zeigt Hilfe Themen in der Befehlszeile an. Ruft Hilfe aus den Hilfedateien auf dem Computer ab. Zeigt die automatisch generierte Hilfe für Cmdlets und Funktionen an, die keine Hilfedateien enthalten. Öffnet Online Hilfe Themen für Cmdlets, Funktionen, Skripts und Workflows in Ihrem standardmäßigen Internetbrowser.

## <a name="auto-generated-help-help-without-help-files"></a>Automatisch generierte Hilfe: Hilfe ohne Hilfedateien

Wenn Sie nicht über die Hilfedatei für ein Cmdlet, eine Funktion oder einen Workflow auf dem Computer verfügen, `Get-Help` zeigt das Cmdlet automatisch generierte Hilfe an und fordert Sie auf, die Hilfedateien herunterzuladen oder online zu lesen.

Die automatisch generierte Hilfe umfasst Syntax und Aliase sowie Hinweise, die erläutern, wie Sie die aktualisierbaren Hilfe-Cmdlets verwenden und auf die Online Hilfe Themen zugreifen können.

Der folgende Befehl ruft beispielsweise die grundlegende Hilfe für das `Get-Culture` Cmdlet ab. Die Ausgabe zeigt die `Get-Help` Anzeige an, wenn keine Hilfedateien auf dem Computer vorhanden sind.

```powershell
Get-Help Get-Culture
```

```output
NAME
    Get-Culture

SYNTAX
    Get-Culture [<CommonParameters>]

ALIASES
    None

REMARKS
    To get the latest Help content including descriptions and examples
    type: Update-Help.
```

## <a name="help-files-for-modules"></a>Hilfedateien für Module

Die kleinste Einheit der aktualisierbaren Hilfe ist die Hilfe für ein Modul. Die Modul Hilfe enthält Hilfe für alle Cmdlets, Funktionen, Workflows, Anbieter, Skripts und Konzepte in einem Modul. Sie können die Hilfe für alle Module aktualisieren, die auf dem Computer installiert sind, auch wenn Sie nicht in die aktuelle Sitzung importiert werden.

Sie können die Hilfe für das gesamte Modul aktualisieren, aber Sie können die Hilfe nicht für einzelne Cmdlets aktualisieren.

Um das Modul zu suchen, das ein bestimmtes Cmdlet enthält, verwenden Sie das folgende Befehls Format:

```powershell
(Get-Command <cmdlet-name>).ModuleName
```

Wenn Sie z. b. das Modul suchen möchten, das das `Set-ExecutionPolicy` Cmdlet enthält, geben Sie Folgendes ein:

```powershell
(Get-Command Set-ExecutionPolicy).ModuleName
```

Um die Hilfe für ein bestimmtes Modul zu aktualisieren, geben Sie Folgendes ein:

```powershell
Update-Help -Module <ModuleName>
```

Geben Sie beispielsweise Folgendes ein, um die Hilfe für das Modul zu aktualisieren, das das Cmdlet "Set-ExecutionPolicy" enthält:

```powershell
Update-Help -Module Microsoft.PowerShell.Security
```

## <a name="permissions-for-updatable-help"></a>Berechtigungen für aktualisierbare Hilfe

Um die Hilfe für die Module im Verzeichnis zu aktualisieren `$pshome/Modules` , müssen Sie Mitglied der Gruppe "Administratoren" auf dem Computer sein.

Wenn Sie kein Mitglied der Gruppe "Administratoren" sind, können Sie die Hilfe für diese Module nicht aktualisieren. Wenn Sie jedoch über Internetzugang verfügen, können Sie die Hilfe online anzeigen.

Zum Aktualisieren der Hilfe für Module im Verzeichnis `$home/Documents/PowerShell/Modules` oder in den Modulen in anderen Unterverzeichnissen des `$home` Verzeichnisses sind keine speziellen Berechtigungen erforderlich.

Die `Update-Help` -und- `Save-Help` Cmdlets verfügen über einen **usedefault-Anmelde** Informations Parameter, der die expliziten Anmelde Informationen des aktuellen Benutzers bereitstellt. Dieser Parameter ist für den Zugriff auf sichere Internet Speicherorte konzipiert.

Die `Update-Help` `Save-Help` Cmdlets und verfügen ebenfalls über einen **Credential** -Parameter, mit dem Sie den Befehl auf einem Remote Computer ausführen und auf eine Dateifreigabe auf einem dritten Computer zugreifen können. Der **Credential** -Parameter ist nur gültig, wenn Sie den SourcePath-Parameter oder den **literalpath** -Parameter von `Update-Help` und die **DestinationPath** -oder **literalpath** -Parameter von verwenden `Save-Help` .

## <a name="how-to-install-and-update-help-files"></a>Installieren und Aktualisieren von Hilfedateien

Verwenden Sie das-Cmdlet, um Hilfedateien zum ersten Mal herunterzuladen und zu installieren oder um die Hilfedateien auf Ihrem Computer zu aktualisieren `Update-Help` .

Mit dem- `Update-Help` Cmdlet werden alle hart arbeiten ausgeführt, einschließlich der folgenden Aufgaben.

- Bestimmt, welche Module aktualisierbare Hilfe unterstützen.
- Sucht den Internet Speicherort, an dem jedes Modul seine aktualisierbaren Hilfedateien speichert.
- Vergleicht die Hilfedateien für jedes Modul auf dem Computer mit den neuesten Hilfedateien, die für die einzelnen Module verfügbar sind.
- Hiermit werden die neuen Dateien aus dem Internet heruntergeladen.
- Entpackt das Hilfedatei Paket.
- Überprüft, ob es sich bei den Dateien um gültige Hilfedateien handelt.
- Installiert die Hilfedateien im sprachspezifischen Unterverzeichnis des Modul Verzeichnisses.

Verwenden Sie das-Cmdlet, um auf die neuen Hilfe Themen zuzugreifen `Get-Help` . PowerShell muss nicht neu gestartet werden.

Um die Hilfe für alle Module auf dem Computer zu installieren oder zu aktualisieren, der die aktualisierbare Hilfe unterstützt, geben Sie

```powershell
Update-Help
```

Um die Hilfe für bestimmte Module zu aktualisieren, fügen Sie den **Module** -Parameter von hinzu `Update-Help` . Platzhalter Zeichen sind im Modulnamen zulässig.

Wenn Sie z. b. die Hilfe für das Server Manager-Modul aktualisieren möchten, geben Sie Folgendes ein:

```powershell
Update-Help -Module ServerManager
```

Ohne Parameter `Update-Help` aktualisiert die Hilfe für alle Module in der Sitzung und für alle installierten Module, die die aktualisierbare Hilfe unterstützen. Module müssen in Verzeichnissen installiert werden, die im Wert der psmodulepath-Umgebungsvariablen aufgelistet sind. Dabei handelt es sich auch um Module, die von einem Get-Help-listavailable-Befehl zurückgegeben werden.

Wenn der Wert des **Module** -Parameters `*` (alle) lautet, versucht, die `Update-Help` Hilfe für alle installierten Module zu aktualisieren, einschließlich der Module, die die aktualisierbare Hilfe nicht unterstützen. Dieser Befehl generiert in der Regel viele Fehler, da das Cmdlet auf Module trifft, die eine aktualisierbare Hilfe nicht unterstützen.

## <a name="how-to-update-help-from-a-file-share"></a>Aktualisieren der Hilfe aus einer Dateifreigabe

Verwenden Sie das-Cmdlet, um Computer zu unterstützen, die nicht mit dem Internet verbunden sind, oder um die Aktualisierung von Hilfe in einem Unternehmen zu steuern oder zu optimieren `Save-Help` . Das `Save-Help` Cmdlet lädt Hilfedateien aus dem Internet herunter und speichert Sie in einem Dateisystem Verzeichnis, das Sie angeben.

`Save-Help` Vergleicht die Hilfedateien im angegebenen Verzeichnis mit den neuesten Hilfedateien, die für die einzelnen Module verfügbar sind. Wenn das Verzeichnis keine Hilfedateien enthält oder neuere Hilfedateien für das Modul verfügbar sind, `Save-Help` lädt das Cmdlet die neuen Dateien aus dem Internet herunter. Die Hilfedateien werden jedoch nicht entpackt oder installiert.

Verwenden Sie den **SourcePath** -Parameter des Cmdlets, um die Hilfedateien auf einem Computer aus Hilfedateien zu installieren oder zu aktualisieren, die in einem Dateisystem Verzeichnis gespeichert wurden `Update-Help` . Das `Update-Help` Cmdlet identifiziert die neuesten Hilfedateien, entpackt und überprüft Sie und installiert Sie in den sprachspezifischen Unterverzeichnissen der Modul Verzeichnisse.

Wenn Sie z. b. die Hilfe für alle installierten Module im Verzeichnis speichern möchten, geben Sie Folgendes ein `\\Server\Share` :

```powershell
Save-Help -DestinationPath \\Server\Share
```

Um die Hilfe aus dem Verzeichnis zu aktualisieren, geben Sie Folgendes ein `\\Server\Share` :

```powershell
Update-Help -SourcePath \\Server\Share
```

In den folgenden Beispielen wird die Verwendung von veranschaulicht `Save-Help` , um die Hilfe für Module zu speichern, die nicht auf dem lokalen Computer installiert sind. In diesem Beispiel führt der Administrator `Save-Help` aus, um die Hilfe für das dhcpserver-Modul von einem Client Computer mit Internetverbindung zu speichern, ohne das dhcpserver-Modul oder die DHCP-Server Rolle auf dem lokalen Computer zu installieren.

Option 1: führen Sie `Invoke-Command` aus, um das **psmoduleinfo** -Objekt für das Remote Modul abzurufen, speichern Sie es in einer Variablen, `$m` und führen Sie dann das `Save-Help` **psmoduleinfo** -Objekt aus, indem Sie die Variable `$m` als Modulnamen angeben.

```powershell
$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock
{ Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

Option 2: Öffnen Sie eine PSSession für den Computer, auf dem das DHCP-Server Modul ausgeführt wird, um das **psmoduleinfo** -Objekt für das Modul abzurufen, speichern Sie es in einer Variablen `$m` , und führen Sie dann `Save-Help` für das Objekt aus, das in der Variablen gespeichert ist `$m` .

```powershell
$s = New-PSSession -ComputerName RemoteServer
$m = Get-Module -PSSession $s -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

Option 3: Öffnen Sie eine CIM-Sitzung, die auf den Computer ausgerichtet ist, auf dem das DHCP-Server Modul ausgeführt wird, um das **psmoduleinfo** -Objekt für das Modul abzurufen, speichern Sie es in einer Variablen `$m` , und führen Sie dann `Save-Help` für das in der Variablen gespeicherte Objekt aus `$m` .

```powershell
$c = New-CimSession -ComputerName RemoteServer
$m = Get-Module -CimSession $c -Name DhcpServer -ListAvailable
Save-Help -Module $m -DestinationPath C:\SavedHelp
```

Im folgenden Beispiel installiert der Administrator die Hilfe für das DHCP-Server Modul auf einem Computer, der keinen Netzwerk Zugriff hat.

Führen Sie zuerst aus, `Export-Clixml` um das **psmoduleinfo** -Objekt in einen freigegebenen Ordner oder ein Wechselmedium zu exportieren.

```powershell
$m = Get-Module -Name DhcpServer -ListAvailable
Export-Clixml -Path E:\UsbFlashDrive\DhcpModule.xml -InputObject $m
```

Als nächstes transportieren Sie das Wechselmedium auf einen Computer, der über Internet Zugriff verfügt, und importieren dann das **psmoduleinfo** -Objekt mit `Import-Clixml` . Führen `Save-Help` Sie aus, um die Hilfe für das importierte dhcpserver-Modul **psmoduleinfo** -Objekt zu speichern.

```powershell
$deserialized_m = Import-Clixml E:\UsbFlashDrive\DhcpModule.xml
Save-Help -Module $deserialized_m -DestinationPath E:\UsbFlashDrive\SavedHelp
```

Transportieren Sie schließlich das Wechselmedium zurück an den Computer, der keinen Netzwerk Zugriff hat, und installieren Sie die Hilfe, indem Sie Ausführen `Update-Help` .

```powershell
Update-Help -Module DhcpServer -SourcePath E:\UsbFlashDrive\SavedHelp
```

Ohne Parameter `Save-Help` lädt die Hilfe für alle Module in der Sitzung und für alle installierten Module herunter, die die aktualisierbare Hilfe unterstützen. Module müssen auf `$env:PSModulePath` dem lokalen Computer oder auf einem Remote Computer, für den Sie die Hilfe speichern möchten, in Verzeichnissen installiert werden, die im Wert der Umgebungsvariablen aufgelistet sind. Dies sind auch Module, die durch Ausführen eines-Befehls zurückgegeben werden `Get-Help -ListAvailable` .

## <a name="how-to-update-help-files-in-different-languages"></a>Aktualisieren von Hilfedateien in verschiedenen Sprachen

Standardmäßig laden die `Update-Help` -und- `Save-Help` Cmdlets die-Hilfe in die Benutzeroberflächen Kultur und-Sprache herunter, die für Windows auf dem lokalen Computer festgelegt ist. , Wenn Hilfedateien für die angegebenen Module in der lokalen Benutzeroberflächen Kultur nicht verfügbar sind, `Update-Help` und `Save-Help` verwenden Sie die Windows-Regeln für die Fall Back Regel, um die beste unterstützte Sprache zu finden.

Sie können jedoch die **UICulture** -Parameter der `Update-Help` -und- `Save-Help` Cmdlets verwenden, um Hilfedateien in alle Benutzeroberflächen Kulturen herunterzuladen und zu installieren, in denen Sie verfügbar sind.

Um beispielsweise die neuesten Hilfedateien für alle Module in der Sitzung in Japanisch (ja-JP) und Französisch (fr-FR) zu speichern, geben Sie Folgendes ein:

```powershell
Save-Help -Path \Server\Share -UICulture ja-jp, fr-fr
```

Wenn Hilfedateien für die Module in den von Ihnen angegebenen Sprachen nicht verfügbar sind, `Update-Help` geben die-und- `Save-Help` Cmdlets eine Fehlermeldung zurück, in der die Sprachen aufgelistet sind, in denen die Hilfe für die einzelnen Module verfügbar ist, sodass Sie die Alternative auswählen können, die Ihren Anforderungen am besten entspricht.

> [!NOTE]
> Aktuell werden aktualisierbare Hilfe Inhalte nur in englischer Sprache (en-US) veröffentlicht. Auf einigen nicht-Windows-Systemen müssen Sie den **UICulture** -Parameter verwenden, um den Inhalt explizit anzufordern `en-US` .

## <a name="how-to-use-online-help"></a>Verwenden der Online Hilfe

Wenn Sie die Hilfedateien auf dem lokalen Computer nicht aktualisieren können, können Sie die neuesten Hilfedateien weiterhin online erhalten.

Verwenden Sie zum Öffnen des Online Hilfe Themas für ein beliebiges Cmdlet oder eine Funktion den **Online-** Parameter des `Get-Help` Cmdlets.

Der folgende Befehl öffnet z. b. das Online Hilfethema für das `Get-Job` Cmdlet in Ihrem Standard Internetbrowser:

```powershell
Get-Help Get-Job -Online
```

Um Online Hilfe für ein Skript zu erhalten, verwenden Sie den **Online-** Parameter und den vollständigen Pfad zum Skript.

Der **Online-** Parameter funktioniert nicht mit Informationen zu Themen. Informationen zu den Themen zu PowerShell, einschließlich der Hilfe Themen zur PowerShell-Sprache, finden Sie unter [PowerShell about topics](about.md).

## <a name="how-to-minimize-or-prevent-internet-downloads"></a>Minimieren oder verhindern von Internet Downloads

Verwenden Sie das-Cmdlet, um Internet Downloads zu minimieren und Benutzern, die nicht mit dem Internet verbunden sind, eine aktualisierbare Hilfe zu bieten `Save-Help` . Laden Sie die Hilfe aus dem Internet herunter, und speichern Sie Sie auf einer Netzwerkfreigabe. Erstellen Sie dann eine Gruppenrichtlinie Einstellung oder einen geplanten Auftrag, der `Update-Help` auf allen Computern einen Befehl ausführt. Legen Sie den Wert des **SourcePath** -Parameters des `Update-Help` Cmdlets auf die Netzwerkfreigabe fest.

Um zu verhindern, dass Benutzer, die über Internet Zugriff verfügen, eine aktualisierbare Hilfe aus dem Internet herunterladen, verwenden Sie die Einstellung **Standard Quellpfad für Update-Hilfe Gruppenrichtlinie festlegen** .

Diese Gruppenrichtlinie Einstellung fügt implizit den **SourcePath** -Parameter, dem Dateisystem Speicherort, den Sie angeben, für jeden `Update-Help` Befehl auf allen betroffenen Computern hinzu. Benutzer können den **SourcePath** -Parameter explizit verwenden, um einen anderen Dateisystem Speicherort anzugeben, Sie können den **SourcePath** -Parameter jedoch nicht ausschließen und die Hilfe aus dem Internet herunterladen.

> [!NOTE]
> Die Gruppenrichtlinien Einstellung **Standard Quellpfad für Update-Hilfe festlegen** wird unter **Computer Konfiguration** und **Benutzerkonfiguration** angezeigt. Allerdings ist nur die Richtlinien Einstellung unter **Computer Konfiguration** wirksam. Die Richtlinien Einstellung unter **Benutzerkonfiguration** wird ignoriert.

Weitere Informationen finden Sie unter [about_Group_Policy_Settings](about_Group_Policy_Settings.md).

## <a name="how-to-update-help-for-non-standard-modules"></a>Aktualisieren der Hilfe für nicht standardmäßige Module

Um die Hilfe für ein Modul zu aktualisieren oder zu speichern, das nicht durch den **listavailable** -Parameter des `Get-Module` Cmdlets zurückgegeben wird, importieren Sie das Modul in die aktuelle Sitzung, bevor Sie einen- `Update-Help` Befehl oder- `Save-Help` Befehl ausführen. Importieren Sie das Modul vor dem Ausführen des Befehls auf einem Remote Computer `Save-Help` in die aktuelle Sitzung bzw `Invoke-Command` . den Skriptblock, der mit dem Remote Computer verbunden ist.

Wenn das Modul in der aktuellen Sitzung ausgeführt wird, führen `Update-Help` `Save-Help` Sie die Cmdlets oder ohne Parameter aus, oder verwenden Sie den **Module** -Parameter, um den Modulnamen anzugeben.

Die **Modul** Parameter der `Update-Help` -und- `Save-Help` Cmdlets akzeptieren nur einen Modulnamen. Sie akzeptieren nicht den Pfad zu einer Modul Datei.

Verwenden Sie dieses Verfahren, um die Hilfe für alle Module zu aktualisieren oder zu speichern, die nicht durch den **listavailable** -Parameter des `Get-Module` Cmdlets zurückgegeben werden. beispielsweise ein Modul, das an einem Speicherort installiert ist, der nicht in der `$env:PSModulePath` Umgebungsvariablen aufgeführt ist, oder ein Modul, das nicht wohl geformt ist (das Modul Verzeichnis enthält nicht mindestens eine Datei, deren basename mit dem Verzeichnisnamen identisch ist).

## <a name="how-to-support-updatable-help"></a>So unterstützen Sie die aktualisierbare Hilfe

Wenn Sie ein Modul erstellen, können Sie die Online Hilfe und die aktualisierbare Hilfe für Ihre Module unterstützen. Weitere Informationen finden Sie [unter unterstützen der aktualisierbaren Hilfe](/powershell/scripting/developer/help/supporting-updatable-help) und [unterstützen der Online Hilfe](/powershell/scripting/developer/module/supporting-online-help) in der Microsoft-Dokumentation.

Aktualisierbare Hilfe ist für PowerShell-Snap-Ins oder Kommentar basierte Hilfe nicht verfügbar.

## <a name="remarks"></a>Hinweise

Die `Update-Help` `Save-Help` Cmdlets und werden auf Windows Preinstallation Environment (Windows PE) nicht unterstützt.

## <a name="see-also"></a>Weitere Informationen:

[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

[Save-Help](xref:Microsoft.PowerShell.Core.Save-Help)

[Update-Help](xref:Microsoft.PowerShell.Core.Update-Help)
