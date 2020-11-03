---
description: Beschreibt die Verwendung von Platzhalter Zeichen in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 3/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wildcards?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Wildcards
ms.openlocfilehash: 3a3146210a7d133190631f177d3a69ca120d1432
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220959"
---
# <a name="about-wildcards"></a>Informationen zu Platzhaltern

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt die Verwendung von Platzhalter Zeichen in PowerShell.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Platzhalter Zeichen stellen ein oder mehrere Zeichen dar. Sie können Sie zum Erstellen von Wort Mustern in Befehlen verwenden. Wenn Sie z. b. alle Dateien im `C:\Techdocs` Verzeichnis mit der `.ppt` Dateinamenerweiterung erhalten möchten, geben Sie Folgendes ein:

```powershell
Get-ChildItem C:\Techdocs\*.ppt
```

In diesem Fall stellt das Platzhalter `*` Zeichen Sternchen () alle Zeichen dar, die vor der `.ppt` Dateinamenerweiterung angezeigt werden.

PowerShell unterstützt die folgenden Platzhalter Zeichen:

|Platzhalter|BESCHREIBUNG               |Beispiel |Match        |Keine Entsprechung|
|--------|--------------------------|--------|-------------|--------|
|\*      |Entsprechung für NULL oder mehr Zeichen | ein\*  | AA, AG, Apple | Bananen |
|?       |Mit einem Zeichen an dieser Position vergleichen | ? n | ein, in, ein | an |
|\[ \]   |Mit einem Zeichenbereich vergleichen | \[a-l \] ook | Buch, Kochen, ansehen | dauerte |
|\[ \]   |Mit bestimmten Zeichen vergleichen | \[BC- \] ook | Buch, Kochen | Schließen |

Sie können mehrere Platzhalter Zeichen in das gleiche Word-Muster einschließen. Wenn Sie z. b. Textdateien suchen möchten, deren Namen mit den Buchstaben **a** bis **l** beginnen, geben Sie Folgendes ein:

```powershell
Get-ChildItem C:\Techdocs\[a-l]*.txt
```

Viele Cmdlets akzeptieren Platzhalter Zeichen in Parameterwerten. Im Hilfethema für jedes Cmdlet wird beschrieben, welche Parameter Platzhalter Zeichen akzeptieren. Bei Parametern, die Platzhalter Zeichen akzeptieren, wird bei der Verwendung die Groß-/Kleinschreibung

Sie können Platzhalter Zeichen in Befehlen und Skript Blöcken verwenden, z. b. zum Erstellen eines Word-Musters, das Eigenschaftswerte darstellt. Beispielsweise werden mit dem folgenden Befehl Dienste abgerufen, in denen der **serviceType** -Eigenschafts Wert **interaktiv** enthalten ist.

```powershell
Get-Service | Where-Object {$_.ServiceType -Like "*Interactive*"}
```

Im folgenden Beispiel enthält die- `If` Anweisung eine Bedingung, die Platzhalter Zeichen verwendet, um Eigenschaftswerte zu suchen. Wenn die **Beschreibung** des Wiederherstellungs Punkts **PowerShell** enthält, fügt der Befehl den Wert **der Eigenschaft "** " der Wiederherstellungspunkt-Eigenschaft einer Protokolldatei hinzu.

```powershell
$p = Get-ComputerRestorePoint
foreach ($point in $p) {
  if ($point.description -like "*PowerShell*") {
    Add-Content -Path C:\TechDocs\RestoreLog.txt "$($point.CreationTime)"
  }
}
```

## <a name="see-also"></a>SIEHE AUCH

[about_Language_Keywords](about_Language_Keywords.md)

[about_If](about_If.md)

[about_Script_Blocks](about_Script_Blocks.md)
