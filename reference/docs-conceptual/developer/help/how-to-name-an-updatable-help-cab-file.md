---
ms.date: 09/12/2016
ms.topic: reference
title: Benennen von aktualisierbaren CAB-Hilfedateien
description: Benennen von aktualisierbaren CAB-Hilfedateien
ms.openlocfilehash: 57ea188d07a382d1a986a49c9ae22c5919dafa8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658927"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>Benennen von aktualisierbaren CAB-Hilfedateien

In diesem Thema wird das erforderliche Namensformat für die aktualisierbaren Hilfe CAB- `.CAB` Dateien () erläutert.

## <a name="how-to-name-an-updatable-help-cab-file"></a>Benennen von aktualisierbaren CAB-Hilfedateien

Eine aktualisierbare CAB- `.CAB` Datei () muss einen Namen haben, der das folgende Format hat.

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

Die Elemente des Namens lauten wie folgt.

- `<ModuleName>` : Der Wert der **Name** -Eigenschaft des **ModuleInfo** -Objekts, das vom [Get-Module-](/powershell/module/Microsoft.PowerShell.Core/Get-Module) Cmdlet zurückgegeben wird.
- `<ModuleGUID>` : Der Wert des **GUID** -Schlüssels im Modul Manifest.
- `<UICulture>` : Die Benutzeroberflächen Kultur der Hilfedateien in der CAB-Datei. Dieser Wert muss mit dem Wert eines der **UICulture** -Elemente in der helpinfo-XML-Datei für das Modul identisch sein.

Wenn der Modulname beispielsweise "Testmodule" lautet, ist die Modul-GUID 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, und die Benutzeroberflächen Kultur ist "en-US", der Name der CAB-Datei lautet wie folgt:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
