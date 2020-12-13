---
ms.date: 09/13/2016
ms.topic: reference
title: Konzepte der Fehlerberichterstattung
description: Konzepte der Fehlerberichterstattung
ms.openlocfilehash: 353e628c63667a2db010556b2ed9169809b742f4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653031"
---
# <a name="error-reporting-concepts"></a>Konzepte der Fehlerberichterstattung

Windows PowerShell bietet zwei Mechanismen zum Melden von Fehlern: einen Mechanismus zum *Beenden von Fehlern* und einen anderen Mechanismus für *Fehler ohne* Abbruch. Es ist wichtig, dass das Cmdlet Fehler ordnungsgemäß meldet, damit die Host Anwendung, die die Cmdlets ausführen, auf angemessene Weise reagieren kann.

Ihr Cmdlet sollte bei Auftreten eines Fehlers die [System. Management. Automation. Cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) -Methode aufgerufen werden, bei der das Cmdlet die Verarbeitung seiner Eingabe Objekte nicht zulässt. Ihr Cmdlet muss die [System. Management. Automation. Cmdlet. Write-error](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) -Methode zum Melden von Fehlern ohne Abbruch verwenden, wenn das Cmdlet die Verarbeitung der Eingabe Objekte fortsetzen kann. Beide Methoden stellen einen Fehler Daten Satz bereit, der von der Host Anwendung verwendet werden kann, um die Ursache des Fehlers zu untersuchen.

Verwenden Sie die folgenden Richtlinien, um zu bestimmen, ob ein Fehler ein Abbruch Fehler oder ein Fehler ohne Abbruch ist.

- Ein Fehler ist ein Abbruch Fehler, wenn das Cmdlet verhindert, dass das aktuelle Objekt weiterhin verarbeitet wird oder wenn andere Eingabe Objekte unabhängig von Ihrem Inhalt erfolgreich verarbeitet werden.

- Ein Fehler ist ein Beendigungs Fehler, wenn Sie nicht möchten, dass das Cmdlet die Verarbeitung des aktuellen Objekts oder weiterer Eingabe Objekte, unabhängig von deren Inhalten, fortsetzt.

- Ein Fehler ist ein Abbruch Fehler, wenn er in einem Cmdlet auftritt, das ein Objekt nicht akzeptiert oder zurückgibt, oder wenn es in einem Cmdlet vorkommt, das nur ein Objekt akzeptiert oder zurückgibt.

- Ein Fehler ist ein Fehler ohne Abbruch, wenn Sie möchten, dass das Cmdlet die Verarbeitung des aktuellen Objekts und aller weiteren Eingabe Objekte fortsetzt.

- Ein Fehler ist ein Fehler ohne Abbruch, wenn er mit einem bestimmten Eingabe Objekt oder einer Teilmenge von Eingabe Objekten verknüpft ist.

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. Cmdlet. ThrowTerminatingError *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System. Management. Automation. Cmdlet. Write error](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Windows PowerShell-Fehlerdatensätze](./windows-powershell-error-records.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
