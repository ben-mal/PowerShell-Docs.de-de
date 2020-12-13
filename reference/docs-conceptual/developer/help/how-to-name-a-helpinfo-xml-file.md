---
ms.date: 09/12/2016
ms.topic: reference
title: Benennen einer XML-Datei HelpInfo
description: Benennen einer XML-Datei HelpInfo
ms.openlocfilehash: 55bc2ef9530fc457e4d9ddf18e79e7226c991663
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659031"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a>Benennen einer XML-Datei HelpInfo

In diesem Thema wird das erforderliche Namensformat für die aktualisierbaren Hilfe Informationsdateien erläutert, die häufig als helpinfo-XML-Dateien bezeichnet werden.

## <a name="how-to-name-a-helpinfo-xml-file"></a>Benennen einer XML-Datei HelpInfo

Eine helpinfo-XML-Datei muss einen Namen haben, der das folgende Format hat.

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

Die Elemente des Namens lauten wie folgt.

- `<ModuleName>` : Der Wert der **Name** -Eigenschaft des **ModuleInfo** -Objekts, das vom [Get-Module-](/powershell/module/Microsoft.PowerShell.Core/Get-Module) Cmdlet zurückgegeben wird.

- `<ModuleGUID>` : Der Wert des **GUID** -Schlüssels im Modul Manifest.

Wenn der Modulname beispielsweise "Testmodule" und die Modul-GUID 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 ist, lautet der Name der helpinfo-XML-Datei für das Modul wie folgt:

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
