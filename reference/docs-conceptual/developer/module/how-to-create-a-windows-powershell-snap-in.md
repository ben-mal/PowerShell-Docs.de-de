---
title: Erstellen eines Windows PowerShell-Snap-Ins | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- snap-ins [PowerShell SDK], examples
ms.openlocfilehash: 4150ba582544d1daa4a898f0ff20b169c24a0ee0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787324"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a>Erstellen eines Windows PowerShell-Snap-Ins

Ein Windows PowerShell-Snap-in bietet einen Mechanismus zum Registrieren von Cmdlets-Sätzen und eines anderen Windows PowerShell-Anbieters mit der Shell und erweitert so die Funktionalität der Shell. Mit einem Windows PowerShell-Snap-in können alle Cmdlets und Anbieter in einer einzelnen Assembly registriert werden, oder es kann eine bestimmte Liste von Cmdlets und Anbietern registriert werden.

Snap-in-Assemblys sollten in einem geschützten Verzeichnis installiert werden, genauso wie bei anderen Betriebssystemen. Andernfalls können böswillige Benutzer eine Assembly durch unsicheren Code ersetzen.

## <a name="windows-powershell-snap-in-classes"></a>Windows PowerShell-Snap-in-Klassen

Alle Windows PowerShell-Snap-in-Klassen werden von der [System. Management. Automation. PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) -Klasse oder der [System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn) -Klasse abgeleitet.

## <a name="examples"></a>Beispiele

[Schreiben eines Windows PowerShell-Snap-Ins](./writing-a-windows-powershell-snap-in.md): in diesem Beispiel wird gezeigt, wie ein Snap-in erstellt wird, das zum Registrieren aller Cmdlets und Anbieter in einer Assembly verwendet wird.

[Schreiben eines benutzerdefinierten Windows PowerShell-Snap-Ins](./writing-a-custom-windows-powershell-snap-in.md): in diesem Beispiel wird gezeigt, wie ein benutzerdefiniertes Snap-in erstellt wird, das zum Registrieren eines bestimmten Satzes von Cmdlets und Anbietern verwendet wird, die in einer einzelnen Assembly vorhanden sein könnten oder nicht.

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn)

[System. Management. Automation. CustomPSSnapIn](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[Registrieren von Cmdlets](./registering-cmdlets.md)

[Windows PowerShell Shell SDK](../windows-powershell-reference.md)
