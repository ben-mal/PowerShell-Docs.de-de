---
title: Getproc-Tutorial | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: cc99cb4de8e3b8fcab8eac28b21162764aecd8a1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784264"
---
# <a name="getproc-tutorial"></a>GetProc-Tutorial

Dieser Abschnitt enthält ein Tutorial zum Erstellen eines Get-proc-Cmdlets, das dem von Windows PowerShell bereitgestellten Cmdlet " [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) " sehr ähnlich ist. Dieses Tutorial enthält Code Fragmente, die veranschaulichen, wie Cmdlets implementiert werden, und eine Erläuterung des Codes.

## <a name="topics-in-this-tutorial"></a>Themen in diesem Tutorial

Die Themen in diesem Lernprogramm sind so konzipiert, dass Sie sequenziell gelesen werden, wobei jedes Thema auf den im vorherigen Thema behandelten Themen aufbaut.

[Erstellen eines Cmdlets ohne Parameter](./creating-a-cmdlet-without-parameters.md) In diesem Abschnitt wird beschrieben, wie Sie ein Cmdlet erstellen, das Informationen vom lokalen Computer abruft, ohne Parameter zu verwenden, und dann die Informationen in die Pipeline schreibt.

[Hinzufügen von Parametern zur Verarbeitung der Befehlszeilen Eingabe](./adding-parameters-that-process-command-line-input.md) In diesem Abschnitt wird beschrieben, wie Sie dem Get-proc-Cmdlet einen Parameter hinzufügen, damit das Cmdlet Eingaben auf der Grundlage von expliziten Objekten verarbeiten kann, die an das Cmdlet übergeben werden. In der hier beschriebenen Implementierung werden Prozesse anhand ihres Namens abgerufen und dann in die Pipeline geschrieben.

[Hinzufügen von Parametern, die Pipeline Eingaben verarbeiten](./adding-parameters-that-process-pipeline-input.md) In diesem Abschnitt wird beschrieben, wie Sie dem Get-proc-Cmdlet einen Parameter hinzufügen, damit das Cmdlet Objekte verarbeiten kann, die über die Pipeline an das Cmdlet übergeben werden. Das hier beschriebene Implementierungs-Cmdlet ruft Prozesse auf der Grundlage von Objekten ab, die an das Cmdlet übergeben werden, und schreibt dann die Informationen in die Pipeline.

[Hinzufügen der Fehlerberichterstattung für nicht abschließende Informationen zum Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) In diesem Abschnitt wird beschrieben, wie einem Cmdlet eine nicht abschließende Fehlerberichterstattung hinzugefügt wird. Die hier beschriebene Implementierung erkennt nicht abschließende Fehler, die bei der Verarbeitung von Eingaben auftreten, und schreibt einen Fehler Daten Satz in den Fehler Datenstrom.

## <a name="see-also"></a>Weitere Informationen

[Erstellen eines Cmdlet ohne Parameter](./creating-a-cmdlet-without-parameters.md)

[Hinzufügen von Parametern zur Verarbeitung der Befehlszeilen Eingabe](./adding-parameters-that-process-command-line-input.md)

[Hinzufügen von Parametern, die Pipelineeingaben verarbeiten](./adding-parameters-that-process-pipeline-input.md)

[Hinzufügen der Fehlerberichterstattung für nicht abschließende Informationen zum Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
