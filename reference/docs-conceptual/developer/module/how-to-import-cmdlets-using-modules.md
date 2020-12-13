---
ms.date: 08/28/2019
ms.topic: reference
title: Importieren von Cmdlets mit Modulen
description: Importieren von Cmdlets mit Modulen
ms.openlocfilehash: 485a4be4d2accaf050a6536e7f92a0673f62a30b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657291"
---
# <a name="how-to-import-cmdlets-using-modules"></a>Importieren von Cmdlets mit Modulen

In diesem Artikel wird beschrieben, wie Sie Cmdlets mithilfe eines binären Moduls in eine PowerShell-Sitzung importieren.

> [!NOTE]
> Die Member von Modulen können Cmdlets, Anbieter, Funktionen, Variablen, Aliase und vieles mehr enthalten. Snap-Ins können nur Cmdlets und Anbieter enthalten.

## <a name="how-to-load-cmdlets-using-a-module"></a>Vorgehensweise beim Laden von Cmdlets mithilfe eines Moduls

1. Erstellen Sie einen Modul Ordner, der denselben Namen hat wie die Assemblydatei, in der die Cmdlets implementiert sind. In diesem Verfahren wird der Modul Ordner im Windows-Ordner erstellt `system32` .

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. Stellen Sie sicher, dass die `PSModulePath` Umgebungsvariable den Pfad zum neuen Modul Ordner enthält. Standardmäßig ist der Systemordner bereits der `PSModulePath` Umgebungsvariablen hinzugefügt. Geben Sie zum Anzeigen von Folgendes ein `PSModulePath` : `$env:PSModulePath` .

1. Kopieren Sie die Cmdlet-Assembly in den Modul Ordner.

1. Fügen Sie im Stamm Ordner des Moduls eine Modul Manifest-Datei ( `.psd1` ) hinzu. PowerShell verwendet das Modul Manifest, um das Modul zu importieren. Weitere Informationen finden Sie unter Gewusst [wie: Schreiben eines PowerShell-Modul Manifests](../module/how-to-write-a-powershell-module-manifest.md).

1. Führen Sie den folgenden Befehl aus, um der Sitzung die Cmdlets hinzuzufügen:

   `Import-Module [Module_Name]`

   Mithilfe dieses Verfahrens können Sie die Cmdlets testen. Der Sitzung werden alle Cmdlets in der Assembly hinzugefügt. Weitere Informationen zu Modulen finden Sie unter [Schreiben eines Windows PowerShell-Moduls](../module/writing-a-windows-powershell-module.md).

## <a name="see-also"></a>Siehe auch

[Schreiben eines PowerShell-Binärmoduls](../module/how-to-write-a-powershell-module-manifest.md)

[Importieren eines PowerShell-Moduls](../module/importing-a-powershell-module.md)

[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[Installieren von Modulen](../module/installing-a-powershell-module.md)

[Ändern des Installationspfads PSModulePath](../module/modifying-the-psmodulepath-installation-path.md)

[Schreiben eines Windows PowerShell-Cmdlets](../cmdlet/cmdlet-overview.md)
