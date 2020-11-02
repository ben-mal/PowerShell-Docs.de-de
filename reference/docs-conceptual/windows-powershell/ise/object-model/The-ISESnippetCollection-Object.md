---
ms.date: 12/31/2019
title: Das ISESnippetCollection-Objekt
description: Das ISESnippetCollection-Objekt ist eine Sammlung von ISESnippet-Objekten. Die einem PowerShellTab-Objekt zugeordnete Dateisammlung ist ein Member dieser Klasse.
ms.openlocfilehash: e6170ddf72d5ead840aa3015d4de1dcb21dbfeff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655961"
---
# <a name="the-isesnippetcollection-object"></a>Das ISESnippetCollection-Objekt

Das **ISESnippetCollection** -Objekt ist eine Sammlung von **ISESnippet** -Objekten. Die einem **PowerShellTab** -Objekt zugeordnete Dateisammlung ist ein Member dieser Klasse. Ein Beispiel ist die `$psISE.CurrentPowerShellTab.Files`-Auflistung.

## <a name="methods"></a>Methoden

### <a name="load-filepathname-"></a>Load\( FilePathName \)

In Windows PowerShell ISE 3.0 und höher unterstützt, in früheren Versionen nicht enthalten.

Lädt eine `.snippets.ps1xml`-Datei mit benutzerdefinierten Codeausschnitten. Die einfachste Möglichkeit zum Erstellen von Codeausschnitten ist das `New-IseSnippet`-Cmdlet, das die Ausschnitte automatisch im Profilordner speichert, sodass sie bei jedem Start der Windows PowerShell ISE geladen werden.

**FilePathName** – Zeichenfolge – der Pfad und der Dateiname für eine Datei mit der Erweiterung „.snippets.ps1xml“, die Codeausschnittdefinitionen enthält.

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a>Weitere Informationen

- [Das ISESnippet-Objekt](The-ISESnippetObject.md)
- [Zweck des Windows PowerShell ISE-Skriptobjektmodells](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Die ISE-Objektmodellhierarchie](The-ISE-Object-Model-Hierarchy.md)
