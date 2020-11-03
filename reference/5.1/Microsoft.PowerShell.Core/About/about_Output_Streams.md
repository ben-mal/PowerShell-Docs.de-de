---
description: Erläutert die Verfügbarkeit und den Zweck der Ausgabedaten Ströme in PowerShell.
keywords: PowerShell, Cmdlet
Locale: en-US
ms.date: 10/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_output_streams?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Output_Streams
ms.openlocfilehash: 2f63c468f6b0d82559fca354a8ce5c1343eb2084
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224324"
---
# <a name="about-output-streams"></a>Informationen zu Ausgabedaten strömen

## <a name="short-description"></a>Kurze Beschreibung
Erläutert die Verfügbarkeit und den Zweck der Ausgabedaten Ströme in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

PowerShell bietet mehrere Ausgabestreams. Die Streams stellen Kanäle für verschiedene Nachrichten Typen bereit. Sie können in diese Streams schreiben, indem Sie das zugeordnete Cmdlet oder die zugehörige Umleitung verwenden. Weitere Informationen finden Sie unter [about_Redirection](about_Redirection.md).

PowerShell unterstützt die folgenden Ausgabedaten Ströme.

| Streich # |      BESCHREIBUNG       | Eingeführt in  |    Cmdlet schreiben     |
| -------- | ---------------------- | -------------- | ------------------- |
| 1        | **Erfolgs** Datenstrom     | PowerShell 2.0 | `Write-Output`      |
| 2        | **Fehler** Datenstrom       | PowerShell 2.0 | `Write-Error`       |
| 3        | **Warnungs** Datenstrom     | PowerShell 3.0 | `Write-Warning`     |
| 4        | **Verbose** Stream     | PowerShell 3.0 | `Write-Verbose`     |
| 5        | **Debug** -Stream       | PowerShell 3.0 | `Write-Debug`       |
| 6        | **Informationsdaten** Strom | PowerShell 5.0 | `Write-Information` |
| –      | **Fortschritts** Datenstrom    | PowerShell 3.0 | `Write-Progress`    |

> [!NOTE]
> Der **Fortschritts** Datenstrom unterstützt keine Umleitung.

## <a name="success-stream"></a>Erfolgs Datenstrom

Der **Erfolgs** Datenstrom ist der Standardstream für normale, erfolgreiche Ergebnisse.
Verwenden `Write-Output` Sie das Cmdlet, um explizit Objekte in diesen Stream zu schreiben. Dieser Stream wird zum Übergeben von Objekten über die PowerShell-Pipeline verwendet. Der **Erfolgs** Datenstrom ist mit dem **stdout** -Datenstrom für native Anwendungen verbunden.

## <a name="error-stream"></a>Fehler Datenstrom

Der **Fehler** Datenstrom ist der Standardstream für Fehler Ergebnisse. Verwenden `Write-Error` Sie das Cmdlet, um explizit in diesen Stream zu schreiben. Der **Fehler** Datenstrom ist mit dem **stderr** -Datenstrom für native Anwendungen verbunden. Unter den meisten Bedingungen können diese Fehler die Ausführungs Pipeline beenden. Fehler, die in diesen Stream geschrieben werden, werden auch der `$Error` automatischen Variablen hinzugefügt. Weitere Informationen finden Sie unter [about_Automatic_Variables](about_Automatic_Variables.md).

## <a name="warning-stream"></a>Warnungs Datenstrom

Der **Warnungs** Datenstrom ist für Fehlerbedingungen bestimmt, die weniger schwerwiegend sind als Fehler, die in den **Fehler** Datenstrom geschrieben wurden. Unter normalen Bedingungen beenden diese Warnungen nicht die Ausführung. Warnungen werden nicht in die `$Error` Automatische Variable geschrieben. Verwenden `Write-Warning` Sie das Cmdlet, um explizit in diesen Stream zu schreiben.

## <a name="verbose-stream"></a>Ausführlicher Datenstrom

Der ausführliche Stream ist für Nachrichten bestimmt, die Benutzer bei der Problembehandlung von **Befehlen unterstützen** , während Sie interaktiv oder über ein Skript ausgeführt werden. Verwenden `Write-Verbose` Sie das Cmdlet, um explizit Nachrichten in diesen Stream zu schreiben. Viele Cmdlets bieten eine ausführliche Ausgabe, die zum Verständnis der internen Funktionsweise des Cmdlets nützlich ist. Die ausführlichen Meldungen werden nur ausgegeben, wenn Sie den `-Verbose` Common-Parameter verwenden. Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).

## <a name="debug-stream"></a>Debugdatenstrom

Der **debugdatenstrom** wird für Nachrichten verwendet, die skriskriptern helfen zu verstehen, warum Ihr Code fehlschlägt. Verwenden `Write-Debug` Sie das Cmdlet, um explizit in diesen Stream zu schreiben. Die Debugmeldungen werden nur ausgegeben, wenn Sie den `-Debug` Common-Parameter verwenden. Weitere Informationen findest du unter [about_CommonParameters](about_CommonParameters.md).

Debugmeldungen sind für Skripts und Cmdlet-Entwickler mehr als Endbenutzer vorgesehen. Diese Debugmeldungen können interne Details enthalten, die für eine ausführliche Problembehandlung erforderlich sind.

## <a name="information-stream"></a>Informationsdaten Strom

Der **Informationsdaten** Strom soll eine Nachricht bereitstellen, die einem Benutzer hilft, den Funktionsumfang eines Skripts nachzuvollziehen. Sie kann auch von Entwicklern als zusätzlicher Stream verwendet werden, der zum Übergeben von Informationen über PowerShell verwendet wird. Der Entwickler kann Streamdaten markieren und eine bestimmte Behandlung für diesen Stream durcharbeiten. Verwenden `Write-Information` Sie das Cmdlet, um explizit in diesen Stream zu schreiben.

## <a name="progress-stream"></a>Fortschritts Datenstrom

Der **Fortschritts** Datenstrom wird für Nachrichten verwendet, die den Fortschritt in länger andauernden Befehlen und Skripts übermitteln. Verwenden `Write-Progress` Sie das Cmdlet, um explizit Nachrichten in diesen Stream zu schreiben. Der **Fortschritts** Datenstrom unterstützt keine Umleitung.

## <a name="see-also"></a>Weitere Informationen:

- [Write-Debug](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [Schreibfehler](xref:Microsoft.PowerShell.Utility.Write-Error)
- [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host)
- [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)
- [Write-Output](xref:Microsoft.PowerShell.Utility.Write-Output)
- [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [about_CommonParameters](about_CommonParameters.md)
- [about_Redirection](about_Redirection.md)
