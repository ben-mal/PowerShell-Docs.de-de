---
ms.date: 09/13/2016
ms.topic: reference
title: Module und Snap-Ins
description: Module und Snap-Ins
ms.openlocfilehash: de4ff1de9a29b78d7783fe7ed0265f5516db1fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658674"
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
