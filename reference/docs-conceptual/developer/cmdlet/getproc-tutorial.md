---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc-Tutorial
description: GetProc-Tutorial
ms.openlocfilehash: 9379e791dd5361fcf5b79061bf0a601ebeb84f42
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652789"
---
# <a name="getproc-tutorial"></a>GetProc-Tutorial

Dieser Abschnitt enthält ein Tutorial zum Erstellen eines Get-Proc Cmdlets, das dem von Windows PowerShell bereitgestellten Cmdlet " [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) " sehr ähnlich ist. Dieses Tutorial enthält Code Fragmente, die veranschaulichen, wie Cmdlets implementiert werden, und eine Erläuterung des Codes.

## <a name="topics-in-this-tutorial"></a>Themen in diesem Tutorial

Die Themen in diesem Lernprogramm sind so konzipiert, dass Sie sequenziell gelesen werden, wobei jedes Thema auf den im vorherigen Thema behandelten Themen aufbaut.

[Erstellen eines Cmdlets ohne Parameter](./creating-a-cmdlet-without-parameters.md) In diesem Abschnitt wird beschrieben, wie Sie ein Cmdlet erstellen, das Informationen vom lokalen Computer abruft, ohne Parameter zu verwenden, und dann die Informationen in die Pipeline schreibt.

[Hinzufügen von Parametern, die Command-Line Eingabe verarbeiten](./adding-parameters-that-process-command-line-input.md) In diesem Abschnitt wird beschrieben, wie Sie dem Get-Proc-Cmdlet einen Parameter hinzufügen, damit das Cmdlet Eingaben auf der Grundlage von expliziten Objekten verarbeiten kann, die an das Cmdlet übergeben werden. In der hier beschriebenen Implementierung werden Prozesse anhand ihres Namens abgerufen und dann in die Pipeline geschrieben.

[Hinzufügen von Parametern, die Pipeline Eingaben verarbeiten](./adding-parameters-that-process-pipeline-input.md) In diesem Abschnitt wird beschrieben, wie Sie dem Get-Proc-Cmdlet einen Parameter hinzufügen, damit das Cmdlet Objekte verarbeiten kann, die über die Pipeline an das Cmdlet übergeben werden. Das hier beschriebene Implementierungs-Cmdlet ruft Prozesse auf der Grundlage von Objekten ab, die an das Cmdlet übergeben werden, und schreibt dann die Informationen in die Pipeline.

[Hinzufügen der Fehlerberichterstattung für nicht abschließende Informationen zum Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) In diesem Abschnitt wird beschrieben, wie einem Cmdlet eine nicht abschließende Fehlerberichterstattung hinzugefügt wird. Die hier beschriebene Implementierung erkennt nicht abschließende Fehler, die bei der Verarbeitung von Eingaben auftreten, und schreibt einen Fehler Daten Satz in den Fehler Datenstrom.

## <a name="see-also"></a>Weitere Informationen

[Erstellen eines Cmdlet ohne Parameter](./creating-a-cmdlet-without-parameters.md)

[Hinzufügen von Parametern, die Command-Line Eingabe verarbeiten](./adding-parameters-that-process-command-line-input.md)

[Hinzufügen von Parametern, die Pipelineeingaben verarbeiten](./adding-parameters-that-process-pipeline-input.md)

[Hinzufügen der Fehlerberichterstattung für nicht abschließende Informationen zum Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
