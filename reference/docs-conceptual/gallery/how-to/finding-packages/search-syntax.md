---
ms.date: 06/12/2017
contributor: JKeithB
keywords: gallery,powershell,cmdlet,psgallery
title: Syntax für die Katalogsuche
ms.openlocfilehash: 9eaabc22090655076dabe177f04130738e081179
ms.sourcegitcommit: d757d64ea8c8af4d92596e8fbe15f2f40d48d3ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90846999"
---
# <a name="gallery-search-syntax"></a>Syntax für die Katalogsuche

Sie können den PowerShell-Katalog mit der [Website des PowerShell-Katalogs](https://www.powershellgallery.com/) durchsuchen. Die Website des PowerShell-Katalogs bietet ein Textsuchfeld in das Sie Wörter, Ausdrücke und Schlüsselwortausdrücke schreiben können, um die Suchergebnisse einzugrenzen.

## <a name="search-by-keywords"></a>Suche nach Schlüsselwörtern

```Syntax
dsc azure sql
```

Die Suche versucht, relevante Dokumente zu finden, die alle drei Schlüsselwörter enthalten, und zugehörige Dokumente zurückzugeben.

## <a name="search-using-phrases-and-keywords"></a>Suchen mithilfe von Ausdrücken und Schlüsselwörtern

```Syntax
"azure sql" deployment
```

Die Eingabe eines Ausdrucks zwischen Anführungszeichen ("") ändert den Suchvorgang. Es wird nun nach dem bestimmten Ausdruck statt nach einzelnen Schlüsselwörter gesucht. Übereinstimmende Dokumente sollten in der Regel den exakten Ausdruck "azure sql", einschließlich der Varianten bezüglich Groß-/Kleinschreibung enthalten, z.B. "Azure SQL" und sollten auch in der Regel das Wort „deployment“ (Bereitstellung) enthalten.

## <a name="filtering-on-fields"></a>Filtern nach Feldern

Sie können nach einer bestimmten Paket-ID (bzw. „Id“ oder „id“) oder nach bestimmten anderen Feldern suchen, indem Sie den Suchbegriffen den Feldnamen voranstellen.

Aktuell lauten die durchsuchbaren Felder „Id“, „Version“, „Tags“, „Author“ (Autor), „Owner“,(Besitzer) „Functions“ (Funktionen), „Cmdlets“, „DscResources“ und „PowerShellVersion“.

- Die ID ist der Name, den Sie in der Konsole verwenden.
- Der Titel ist das, was oben auf der Paketseite in den Suchergebnissen angezeigt wird.

## <a name="examples"></a>Beispiele

```Syntax
ID:PSReadline
```

sucht nach Paketen mit einer ID, die „PSReadline“ enthält.

```Syntax
Id:"AzureRM.Profile"
```

Dies ist eine andere Möglichkeit, Pakete mit „AzureRM.Profile“ im ID-Feld zu suchen.

Der Filter „Id“ ist eine Übereinstimmung bei Teilzeichenfolge, Sie suchen also nach Folgendem:

```Syntax
Id:"azure"
```

Es werden Ergebnisse bereitgestellt, die „AzureRM.Profile“ und “Azure.Storage“ enthalten.

Sie können auch nach mehreren Schlüsselwörtern in einem einzelnen Feld suchen.

```Syntax
id:azure tags:intellisense
```

Und Sie können die Suche nach Ausdrücken mit doppelten Anführungszeichen durchführen:

```Syntax
id:"azure.storage"
```

So suchen Sie alle Pakete mit DSC-Tag:

```Syntax
Tags:DSC
```

So suchen Sie alle Pakete mit der angegebenen Funktion:

```Syntax
Functions:Get-TreeSize
```

So suchen Sie alle Pakete mit dem angegebenen Cmdlet:

```Syntax
Cmdlets:Get-AzureRmEnvironment
```

So suchen Sie alle Pakete mit dem angegebenen DSC-Ressourcennamen:

```Syntax
DscResources:xArchive
```

So suchen Sie alle Pakete mit der angegebenen PowerShellVersion:

```Syntax
PowerShellVersion:2.0
```

Wenn Sie anschließend ein Feld verwenden, das nicht unterstützt wird, wie z.B. „commands“ (Befehle), wird es einfach ignoriert, und alle Felder werden durchsucht. Das folgende Query

```Syntax
commands:blobs storage
```

wird genau wie diese Abfrage interpretiert:

```Syntax
blobs storage
```
