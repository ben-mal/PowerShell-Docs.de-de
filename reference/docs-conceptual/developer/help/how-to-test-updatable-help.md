---
ms.date: 09/12/2016
ms.topic: reference
title: Testen der aktualisierbaren Hilfe
description: Testen der aktualisierbaren Hilfe
ms.openlocfilehash: 47873089bfa1b918ea9970915e829a22aa7254c5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667622"
---
# <a name="how-to-test-updatable-help"></a>Testen der aktualisierbaren Hilfe

In diesem Thema werden die Ansätze zum Testen der aktualisierbaren Hilfe für ein Modul beschrieben.

## <a name="using-verbose-to-detect-errors"></a>Verwenden von Verbose zum Erkennen von Fehlern

Nachdem Sie die helpinfo-XML-Datei und die CAB-Dateien für das Modul hochgeladen haben, testen Sie die Dateien, indem Sie einen [Update-Help-](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Befehl mit dem Parameter **verbose** ausführen Der **verbose** -Parameter weist `Update-Help` an, die wichtigen Schritte in seinen Aktionen zu melden, von dem Lesen des **helpinfouri** -Schlüssels im Modul Manifest, um die Dateitypen in der entpackten CAB-Datei zu überprüfen und die Dateien in das sprachspezifische Modul Verzeichnis zu platzieren.

Wenn alle ausführlichen Meldungen aufgelöst werden, führen Sie einen `Update-Help` Befehl mit dem **Debug** -Parameter aus.
Dieser Parameter sollte alle verbleibenden Probleme mit den aktualisierbaren Hilfedateien erkennen.
