---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet-Beispiele
description: Cmdlet-Beispiele
ms.openlocfilehash: 6ee149f611e5af5c45a62363e19e66bf200c0c0a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668251"
---
# <a name="cmdlet-samples"></a>Cmdlet-Beispiele

In diesem Abschnitt wird der Beispielcode beschrieben, der im Windows PowerShell 2.0 SDK bereitgestellt wird. Sie können für die Themen in diesem Abschnitt den entsprechenden Code kopieren oder die mit dem SDK installierten Quelldateien öffnen. Das [Windows PowerShell 2.0 Software Development Kit (SDK)](https://www.microsoft.com/download/details.aspx?id=2560) enthält Infodateien, Quelldateien und Visual Studio-Projektdateien für jedes Beispiel. Wenn das SDK installiert ist, finden Sie die Beispiele im Ordner `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`.

## <a name="in-this-section"></a>In diesem Abschnitt

[GetProcessSample01-Beispiel](./getprocesssample01-sample.md): Dieses Beispiel zeigt ein Cmdlet, das die Prozesse auf dem lokalen Computer abruft.

[GetProcessSample02-Beispiel](./getprocesssample02-sample.md): Dieses Beispiel zeigt ein Cmdlet, das die Prozesse auf dem lokalen Computer abruft. Es enthält den Parameter „Name“, mit dem Sie die Prozesse angeben können, die abgerufen werden sollen.

[GetProcessSample03-Beispiel](./getprocesssample03-sample.md): Dieses Beispiel zeigt ein Cmdlet, das die Prozesse auf dem lokalen Computer abruft. Es enthält den Parameter „Name“, der ein Objekt aus der Pipeline oder einen Wert aus einer Eigenschaft eines Objekts akzeptieren kann, dessen Eigenschaftenname mit dem Parameternamen übereinstimmt.

[GetProcessSample04-Beispiel](./getprocesssample04-sample.md): Dieses Beispiel zeigt ein Cmdlet, das die Prozesse auf dem lokalen Computer abruft. Darin wird ein Fehler ohne Abbruch generiert, wenn es beim Abrufen eines Prozesses zu einem Fehler kommt.

[GetProcessSample05-Beispiel](./getprocesssample05-sample.md): Dieses Beispiel zeigt eine vollständige Version des Cmdlets „Get-Proc“.

[StopProcessSample01-Beispiel](./stopprocesssample01-sample.md): Dieses Beispiel zeigt ein Cmdlet, das vor dem Versuch zur Beendigung eines Prozesses Feedback vom Benutzer anfordert. Außerdem wird gezeigt, wie Sie einen `PassThru`-Parameter implementieren, über den das Cmdlet angewiesen werden kann, ein Objekt zurückzugeben.

[StopProcessSample02-Beispiel](./stopprocesssample02-sample.md): Dieses Beispiel zeigt ein Cmdlet, das Prozesse auf dem lokalen Computer beendet und dabei Debugmeldungen, ausführliche Meldungen und Warnmeldungen erzeugt.

[StopProcessSample03-Beispiel](./stopprocesssample03-sample.md): Dieses Beispiel zeigt ein Cmdlet, dessen Parameter über Aliase verfügen und Platzhalterzeichen unterstützen.

[StopProcessSample04-Beispiel](./stopprocesssample04-sample.md): Dieses Beispiel zeigt ein Cmdlet, das Parametersätze deklariert, den Standardparametersatz angibt und ein Eingabeobjekt akzeptieren kann.

[Events01-Beispiel](./events01-sample.md): Dieses Beispiel zeigt ein Cmdlet, das es Benutzern erlaubt, sich für Ereignisse zu registrieren, die von [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher) ausgelöst werden. Mit diesem Cmdlet können Benutzer z. B. eine Aktion registrieren, die ausgeführt wird, wenn in einem bestimmten Verzeichnis eine Datei erstellt wird. Dieses Beispiel ist aus der Basisklasse [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) abgeleitet.

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
