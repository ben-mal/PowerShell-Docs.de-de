---
title: Erstellen einer XML-basierten Hilfe mithilfe von PlatyPS
description: PlatyPS ist eine schnelle und effiziente Möglichkeit, eine XML-basierte Hilfe zu erstellen.
ms.date: 07/21/2020
ms.openlocfilehash: 79cf8c077a07bf1e7aa8ea1ea799be5f8d4af12c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972586"
---
# <a name="create-xml-based-help-using-platyps"></a>Erstellen einer XML-basierten Hilfe mithilfe von PlatyPS

Beim Erstellen eines PowerShell-Moduls wird stets empfohlen, eine ausführliche Hilfe für die von Ihnen erstellten Cmdlets hinzuzufügen. Wenn Ihre Cmdlets in kompiliertem Code implementiert sind, müssen Sie die XML-basierte Hilfe verwenden. Dieses XML-Format wird als Microsoft Assistance Markup Language (MAML) bezeichnet.

In der Legacy-Dokumentation zum PowerShell SDK werden die Details zur Erstellung von Hilfe für in Modulen gepackte PowerShell-Cmdlets behandelt. PowerShell bietet jedoch keine Tools zum Erstellen der XML-basierten Hilfe. In der SDK-Dokumentation wird die Struktur der MAML-Hilfe erklärt, aber es bleibt Ihnen überlassen, den komplexen und tief geschachtelten MAML-Inhalt manuell zu erstellen.

An dieser Stelle kann das [PlatyPS][]-Modul helfen.

## <a name="what-is-platyps"></a>Was ist PlatyPS?

PlatyPS ist ein [Open-Source-][platyps-repo]-Tool, das als _Hackathon_-Projekt begann, um die Erstellung und Pflege von MAML zu vereinfachen. PlatyPS dokumentiert die Syntax von Parametersätzen und die einzelnen Parameter für jedes Cmdlet in Ihrem Modul. PlatyPS erstellt strukturierte [Markdown][]-Dateien mit Syntaxinformationen. Das Tool kann keine Beschreibungen erstellen oder Beispiele bereitstellen.

PlatyPS erstellt Platzhalter, die Sie zum Ausfüllen von Beschreibungen und Beispielen verwenden können. Nach Hinzufügen der erforderlichen Informationen kompiliert PlatyPS die Markdown-Dateien in MAML-Dateien. Das Hilfesystem von PowerShell ermöglicht auch konzeptionelle Hilfedateien in Textform (zu Themen). PlatyPS bietet ein Cmdlet zum Erstellen einer strukturierten Markdown-Vorlage für eine neue _Info_-Datei, wobei diese `about_*.help.txt`-Dateien jedoch manuell gepflegt werden müssen.

Sie können die MAML-und Texthilfedateien in Ihr Modul einschließen. Sie können mit PlatyPS auch die Hilfedateien zu einem CAB-Paket kompilieren, das für aktualisierbare Hilfe gehostet werden kann.

## <a name="get-started-using-platyps"></a>Erste Schritte mit PlatyPS

Zunächst müssen Sie PlatyPS aus dem PowerShell-Katalog herunterladen und installieren.

```powershell
Install-Module platyps -Force
Import-Module platyps
```

Im folgenden Flussdiagramm wird der Prozess zum Erstellen oder Aktualisieren von PowerShell-Referenzinhalten beschrieben.

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="Der Workflow zum Erstellen einer XML-basierten Hilfe mithilfe von PlatyPS":::

##  <a name="create-markdown-content-for-a-powershell-module"></a>Erstellen von Markdown-Inhalten für ein PowerShell-Modul

1. Importieren Sie Ihr neues Modul in die Sitzung. Wiederholen Sie diesen Schritt für jedes Modul, das Sie dokumentieren müssen.

   Führen Sie den folgenden Befehl aus, um die Module zu importieren:

   ```powershell
   Import-Module <your module name>
   ```

1. Verwenden Sie PlatyPS, um Markdown-Dateien für Ihre Modulseite und alle zugehörigen Cmdlets innerhalb des Moduls zu generieren. Wiederholen Sie diesen Schritt für jedes Modul, das Sie dokumentieren müssen.

   ```powershell
   $OutputFolder = <output path>
   $parameters = @{
       Module = <ModuleName>
       OutputFolder = $OutputFolder
       AlphabeticParamsOrder = $true
       WithModulePage = $true
       ExcludeDontShow = $true
       Encoding = 'UTF8BOM'
   }
   New-MarkdownHelp @parameters

   New-MarkdownAboutHelp -OutputFolder $OutputFolder -AboutName "topic_name"
   ```

   Wenn der Ausgabeordner nicht vorhanden ist, wird er von `New-MarkdownHelp` erstellt. In diesem Beispiel erstellt `New-MarkdownHelp` eine Markdown-Datei für jedes Cmdlet im Modul. Außerdem wird die _Modulseite_ in einer Datei namens `<ModuleName>.md` erstellt. Diese Modulseite enthält eine Liste der Cmdlets im Modul und Platzhalter für die beschreibende **Übersicht**. Die Metadaten auf der Modulseite stammen aus dem Modulmanifest und werden von PlatyPS zur Erstellung der HelpInfo-XML-Datei verwendet (wie [nachstehend](#creating-an-updateable-help-package) erklärt).

   `New-MarkdownAboutHelp` erstellt eine neue _Info_-Datei mit dem Namen `about_topic_name.md`.

   Weitere Informationen finden Sie unter [New-MarkdownHelp][] und [New-MarkdownAboutHelp][].

### <a name="update-existing-markdown-content-when-the-module-changes"></a>Aktualisieren vorhandener Markdown-Inhalte bei Moduländerungen

Mit PlatyPS können auch vorhandene Markdown-Dateien für ein Modul aktualisiert werden. Mit diesem Schritt können Sie vorhandene Module aktualisieren, die über neue Cmdlets, neue Parameter oder geänderte Parameter verfügen.

1. Importieren Sie Ihr neues Modul in die Sitzung. Wiederholen Sie diesen Schritt für jedes Modul, das Sie dokumentieren müssen.

   Führen Sie den folgenden Befehl aus, um die Module zu importieren:

   ```powershell
   Import-Module <your module name>
   ```

1. Verwenden Sie PlatyPS, um Markdown-Dateien für Ihre Modulzielseite und alle zugehörigen Cmdlets innerhalb des Moduls zu aktualisieren. Wiederholen Sie diesen Schritt für jedes Modul, das Sie dokumentieren müssen.

   ```powershell
   $parameters = @{
       Path = <folder with Markdown>
       RefreshModulePage = $true
       AlphabeticParamsOrder = $true
       UpdateInputOutput = $true
       ExcludeDontShow = $true
       LogPath = <path to store log file>
       Encoding = 'UTF8BOM'
   }
   Update-MarkdownHelpModule @parameters
   ```

   `Update-MarkdownHelpModule` aktualisiert die Markdown-Dateien für Cmdlets und Module im angegebenen Ordner.
   Die `about_*.md`-Dateien werden damit nicht aktualisiert. Die Moduldatei (`ModuleName.md`) empfängt jeglichen neuen Text für die **Übersicht**, der den Cmdlet-Dateien hinzugefügt wurde. Zu Aktualisierungen von Cmdlet-Dateien zählen folgende Änderungen:

   - Neue Parametersätze
   - Neue Parameter
   - Aktualisierte Metadaten von Parametern
   - Aktualisierte Informationen zu Ein- und Ausgabetyp

   Weitere Informationen finden Sie unter [Update-MarkdownHelpModule][].

## <a name="edit-the-new-or-updated-markdown-files"></a>Bearbeiten der neuen oder aktualisierten Markdown-Dateien

PlatyPS dokumentiert die Syntax der Parametersätze und einzelnen Parameter. Das Tool kann keine Beschreibungen erstellen oder Beispiele bereitstellen. Die spezifischen Bereiche, in denen Inhalte benötigt werden, stehen in geschweiften Klammern. Beispiel: `{{ Fill in the Description }}`

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="Der Workflow zum Erstellen einer XML-basierten Hilfe mithilfe von PlatyPS":::

Sie müssen eine Übersicht, eine Beschreibung des Cmdlets und der einzelnen Parameter sowie mindestens ein Beispiel hinzufügen.

Ausführliche Informationen zum Schreiben von PowerShell-Inhalten finden Sie in den folgenden Artikeln:

- [Styleguide für PowerShell](/powershell/scripting/community/contributing/powershell-style-guide)
- [Bearbeiten von Referenzartikeln](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> PlatyPS weist ein bestimmtes Schema auf, das als Cmdlet-Referenz verwendet wird. Dieses Schema lässt nur bestimmte Markdown-Blöcke in bestimmten Abschnitten des Dokuments zu. Wenn Sie Inhalte an der falschen Stelle ablegen, schlägt der PlatyPS-Buildschritt fehl. Weitere Informationen finden Sie in der Dokumentation zum [Schema][] im PlatyPS-Repository. Ein umfassendes Beispiel einer wohlgeformten Cmdlet-Referenz finden Sie unter [Get-Item][].

Nachdem Sie den erforderlichen Inhalt für jedes Ihrer Cmdlets bereitgestellt haben, müssen Sie die Zielseite des Moduls aktualisieren. Vergewissern Sie sich, dass Ihr Modul die richtigen Werte für `Module Guid` und `Download Help Link` in den YAML-Metadaten der Datei `<module-name>.md` enthält. Fügen Sie fehlende Metadaten hinzu.

Sie werden auch feststellen, dass einigen Cmdlets möglicherweise eine **Übersicht** (_Kurzbeschreibung_) fehlt. Der folgende Befehl aktualisiert die Zielseite des Moduls mit dem Beschreibungstext Ihrer **Übersicht**. Öffnen Sie die Zielseite des Moduls, um die Beschreibungen zu überprüfen.

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

Nachdem Sie den gesamten Inhalt eingegeben haben, können Sie nun die MAML-Hilfedateien erstellen, die von `Get-Help` in der PowerShell-Konsole angezeigt werden.

## <a name="create-the-external-help-files"></a>Erstellen der externen Hilfedateien

In diesem Schritt werden die MAML-Hilfedateien erstellt, die von `Get-Help` in der PowerShell-Konsole angezeigt werden.

Führen Sie den folgenden Befehl aus, um die MAML-Dateien zu erstellen:

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

`New-ExternalHelp` konvertiert alle Markdown-Dateien von Cmdlets in eine (oder mehrere) MAML-Dateien. Info-Dateien werden in einfache Textdateien mit dem folgenden Namensformat konvertiert: `about_topic_name.help.txt`.
Der Markdown-Inhalt muss die Anforderung des PlatyPS-Schemas erfüllen. `New-ExternalHelp` wird mit Fehlern beendet, wenn der Inhalt nicht dem Schema folgt. Sie müssen die Dateien bearbeiten und die Schemaverstöße beheben.

> [!CAUTION]
> PlatyPS wandelt die `about_*.md`-Dateien schlecht in einfachen Text um. Sie müssen sehr einfaches Markdown verwenden, um akzeptable Ergebnisse zu erzielen. Möglicherweise möchten Sie die Dateien im einfachen Textformat `about_topic_name.help.txt` beibehalten, anstatt PlatyPS die Umwandlung zu erlauben.

Nach diesem Schritt sehen Sie die Dateien `*-help.xml` und `about_*.help.txt` im Zielausgabeordner.

Weitere Informationen finden Sie unter [New-ExternalHelp][].

### <a name="test-the-compiled-help-files"></a>Testen der kompilierten Hilfedateien

Sie können den Inhalt mit dem Cmdlet [Get-HelpPreview][] überprüfen:

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

Das Cmdlet liest die kompilierte MAML-Datei und gibt den Inhalt in dem Format aus, das Sie von `Get-Help` empfangen würden. Auf diese Weise können Sie die Ergebnisse überprüfen, um sicherzustellen, dass die Markdown-Dateien einwandfrei kompiliert wurden und die gewünschten Ergebnisse liefern. Wenn Sie einen Fehler finden, bearbeiten Sie die Markdown-Dateien erneut, und kompilieren Sie die MAML-Dateien neu.

Nun können Sie Ihre Hilfedateien veröffentlichen.

## <a name="publishing-your-help"></a>Veröffentlichen Ihrer Hilfe

Nun, da Sie die Markdown-Dateien zu PowerShell-Hilfedateien kompiliert haben, können Sie die Dateien den Benutzern zur Verfügung stellen. Es gibt in der PowerShell-Konsole zwei Optionen für die Bereitstellung von Hilfe.

- Packen der Hilfedateien mit dem Modul
- Erstellen eines aktualisierbaren Hilfepakets, das Benutzer mit dem Cmdlet `Update-Help` installieren

### <a name="packaging-help-with-the-module"></a>Packen der Hilfe mit dem Modul

Die Hilfedateien können mit Ihrem Modul gepackt werden. Ausführliche Informationen zur Ordnerstruktur finden Sie unter [Schreiben von Hilfe für Module][]. Sie sollten die Liste der Hilfedateien in den Wert des Schlüssels **FileList** im Modulmanifest aufnehmen.

### <a name="creating-an-updateable-help-package"></a>Erstellen eines aktualisierbaren Hilfepakets

Die allgemeinen Schritte zum Erstellen einer aktualisierbaren Hilfe sind wie folgt:

1. Bestimmen einer Internetwebsite zum Hosten der Hilfedateien
1. Hinzufügen des Schlüssels **HelpInfoURI** zum Modulmanifest
1. Erstellen der XML-Datei HelpInfo
1. Erstellen von CAB-Dateien
1. Hochladen Ihrer Dateien

Weitere Informationen finden Sie unter [Unterstützen einer aktualisierbaren Hilfe: ausführliche Anleitung][step-by-step].

PlatyPS unterstützt Sie bei einigen dieser Schritte.

**HelpInfoURI** ist eine URL, die auf den Speicherort verweist, an dem Ihre Hilfedateien im Internet gehostet werden. Dieser Wert wird im Modulmanifest konfiguriert. `Update-Help` liest das Modulmanifest, um diese URL zu erhalten und den aktualisierbaren Hilfeinhalt herunterzuladen. Diese URL darf nur auf den Speicherort des Ordners und nicht auf einzelne Dateien verweisen. `Update-Help` erstellt die herunterzuladenden Dateinamen auf Grundlage anderer Informationen im Modulmanifest und in der HelpInfo-XML-Datei.

> [!IMPORTANT]
> **HelpInfoURI** muss mit einem Schrägstrich (`/`) enden. Ohne dieses Zeichen kann `Update-Help` die ordnungsgemäßen Dateipfade zum Herunterladen des Inhalts nicht erstellen. Außerdem wird bei den meisten HTTP-basierten Dateidiensten Groß-/Kleinschreibung beachtet. Es ist wichtig, dass die Modulmetadaten in der HelpInfo-XML-Datei die richtige Groß-/Kleinschreibung enthalten.

Mit dem Cmdlet `New-ExternalHelp` wird die HelpInfo-XML-Datei im Ausgabeordner erstellt. Die HelpInfo-XML-Datei wird mithilfe von YAML-Metadaten erstellt, die in den Markdown-Dateien (`ModuleName.md`) des Moduls enthalten sind.

Das Cmdlet `New-ExternalHelpCab` erstellt ZIP- und CAB-Dateien mit den von Ihnen kompilierten MAML- und `about_*.help.txt`-Dateien. CAB-Dateien sind mit allen Versionen von PowerShell kompatibel.
Ab PowerShell 6 können ZIP-Dateien verwendet werden.

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

Nach dem Erstellen der ZIP- und CAB-Dateien laden Sie die ZIP-, CAB- und HelpInfo-XML-Dateien auf Ihren HTTP-Dateiserver hoch. Legen Sie die Dateien an dem von **HelpInfoURI** angegebenen Speicherort ab.

Weitere Informationen finden Sie unter [New-ExternalHelpCab][].

### <a name="other-publishing-options"></a>Weitere Veröffentlichungsoptionen

Markdown ist ein vielseitiges Format, das sich für die Veröffentlichung problemlos in andere Formate umwandeln lässt. Mit einem Tool wie [Pandoc][] können Sie Ihre Markdown-Hilfedateien in viele verschiedene Dokumentformate konvertieren, darunter Nur-Text, HTML, PDF und Office.

Darüber hinaus können die Cmdlets [ConvertFrom-Markdown][] und [Show-Markdown][] ab PowerShell 6 verwendet werden, um Markdown in HTML zu konvertieren oder eine farbige Anzeige in der PowerShell-Konsole zu erstellen.

## <a name="known-issues"></a>Bekannte Probleme

PlatyPS reagiert sehr empfindlich auf das [-Schema][] für die Struktur der Markdown-Dateien, die es erstellt und kompiliert. Es ist sehr einfach, gültige Markdown-Inhalte zu schreiben, die gegen dieses Schema verstoßen. Weitere Informationen finden Sie im [Styleguide für PowerShell][] und unter[Bearbeiten von Referenzartikeln][].

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[schema]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[Styleguide für PowerShell]: /powershell/scripting/community/contributing/powershell-style-guide
[Bearbeiten von Referenzartikeln]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Schreiben von Hilfe für Module]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown
