---
title: Module und Snap-Ins | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 07cdc55fd6d1462130f1a81deb30056623a525e6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787307"
---
# <a name="modules-and-snap-ins"></a>Module und Snap-Ins

Cmdlets können einer Sitzung mithilfe von Modulen (eingeführt von Windows PowerShell 2,0) oder Snap-Ins hinzugefügt werden. Nachdem das Cmdlet der Sitzung hinzugefügt wurde, kann es Programm gesteuert von einer Host Anwendung oder interaktiv in der Befehlszeile ausgeführt werden.

Es wird empfohlen, Module als Übermittlungs Methode zum Hinzufügen von Cmdlets zu einer Sitzung aus den folgenden Gründen zu verwenden:

- Mit Modulen können Sie Cmdlets hinzufügen, indem Sie die Assembly laden, in der das Cmdlet definiert ist. Es ist nicht erforderlich, eine Snap-in-Klasse zu implementieren.

- Mit Modulen können Sie weitere Ressourcen hinzufügen, z. b. Variablen, Funktionen, Skripts, Typen und Formatierungs Dateien.

- Snap-Ins können nur zum Hinzufügen von Cmdlets und Anbietern zur Sitzung verwendet werden.

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Moduls](writing-a-windows-powershell-module.md)

[Schreiben eines Windows PowerShell-Cmdlets](../cmdlet/cmdlet-overview.md)
