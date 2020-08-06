---
title: Cmdlet-Beispiele | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 633e4a5108673b09a92679c7992421b6b3405b72
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774744"
---
# <a name="cmdlet-samples"></a>Cmdlet-Beispiele

In diesem Abschnitt wird der Beispielcode beschrieben, der im Windows PowerShell 2,0 SDK bereitgestellt wird. Sie können Code aus den Themen in diesem Abschnitt kopieren oder die mit dem SDK installierten Quelldateien öffnen. Das [Windows PowerShell 2,0 Software Development Kit (SDK)](https://www.microsoft.com/en-us/download/details.aspx?id=2560) stellt Info Dateien, Quelldateien und Visual Studio-Projektdateien für die einzelnen Beispiele bereit. Wenn das SDK installiert ist, können Sie die Beispiele im `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` Ordner finden.

## <a name="in-this-section"></a>In diesem Abschnitt

[GetProcessSample01-Beispiel](./getprocesssample01-sample.md) Dieses Beispiel zeigt, wie Sie ein Cmdlet schreiben, das die Prozesse auf dem lokalen Computer abruft.

[GetProcessSample02-Beispiel](./getprocesssample02-sample.md) Dieses Beispiel zeigt, wie Sie ein Cmdlet schreiben, das die Prozesse auf dem lokalen Computer abruft. Sie stellt einen Name-Parameter bereit, der zum Angeben der abzurufenden Prozesse verwendet werden kann.

[GetProcessSample03-Beispiel](./getprocesssample03-sample.md) Dieses Beispiel zeigt, wie Sie ein Cmdlet schreiben, das die Prozesse auf dem lokalen Computer abruft. Sie stellt einen Name-Parameter bereit, der ein Objekt aus der Pipeline oder einen Wert aus einer Eigenschaft eines Objekts akzeptieren kann, dessen Eigenschaftsname mit dem Parameternamen identisch ist.

[GetProcessSample04-Beispiel](./getprocesssample04-sample.md) Dieses Beispiel zeigt, wie Sie ein Cmdlet schreiben, das die Prozesse auf dem lokalen Computer abruft. Wenn beim Abrufen eines Prozesses ein Fehler auftritt, wird ein Fehler vom Typ "nicht abgebrochen" generiert.

[GetProcessSample05-Beispiel](./getprocesssample05-sample.md) Dieses Beispiel zeigt eine vollständige Version des Get-proc-Cmdlets.

[StopProcessSample01-Beispiel](./stopprocesssample01-sample.md) Dieses Beispiel zeigt, wie ein Cmdlet geschrieben wird, das Feedback vom Benutzer anfordert, bevor versucht wird, einen Prozess zu beenden, und wie ein Parameter implementiert wird, der `PassThru` angibt, dass der Benutzer das Cmdlet zum Zurückgeben eines Objekts wünscht.

[StopProcessSample02-Beispiel](./stopprocesssample02-sample.md) In diesem Beispiel wird gezeigt, wie ein Cmdlet geschrieben wird, das beim Beenden von Prozessen auf dem lokalen Computer Debug-, ausführliche und Warnmeldungen schreibt.

[StopProcessSample03-Beispiel](./stopprocesssample03-sample.md) In diesem Beispiel wird gezeigt, wie ein Cmdlet geschrieben wird, dessen Parameter Aliase aufweisen und Platzhalter Zeichen unterstützen.

[StopProcessSample04-Beispiel](./stopprocesssample04-sample.md) Dieses Beispiel zeigt, wie Sie ein Cmdlet schreiben, das Parametersätze deklariert, den Standardparameter Satz angibt und ein Eingabe Objekt akzeptieren kann.

[Events01-Beispiel](./events01-sample.md) In diesem Beispiel wird gezeigt, wie ein Cmdlet erstellt wird, das es dem Benutzer ermöglicht, sich für Ereignisse zu registrieren, die von [System. IO. FileSystemWatcher](/dotnet/api/System.IO.FileSystemWatcher)ausgelöst werden. Mit diesem Cmdlet können Benutzer z. b. eine Aktion registrieren, die ausgeführt wird, wenn eine Datei unter einem bestimmten Verzeichnis erstellt wird. Dieses Beispiel wird von der [Microsoft. PowerShell. Commands. objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) -Basisklasse abgeleitet.

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
