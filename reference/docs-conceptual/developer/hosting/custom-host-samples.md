---
title: Beispiele für benutzerdefinierte Hosts | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 6a10d3da6d8bf93986a3f5b029fdae3afb23a903
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779521"
---
# <a name="custom-host-samples"></a>Beispiele für benutzerdefinierte Hosts

Dieser Abschnitt enthält Beispielcode zum Schreiben eines benutzerdefinierten Hosts. Mit Microsoft Visual Studio können Sie eine Konsolenanwendung erstellen und dann den Code aus den Themen in diesem Abschnitt in die Host Anwendung kopieren.

## <a name="in-this-section"></a>In diesem Abschnitt

 [Host01-Beispiel](./host01-sample.md) Dieses Beispiel zeigt, wie eine Host Anwendung implementiert wird, die einen einfachen benutzerdefinierten Host verwendet.

 [Host02-Beispiel](./host02-sample.md) In diesem Beispiel wird gezeigt, wie eine Host Anwendung geschrieben wird, die die Windows PowerShell-Laufzeit zusammen mit einer benutzerdefinierten Host Implementierung verwendet. Die Host Anwendung legt die Host Kultur auf Deutsch fest, führt das [Get-Process-](/powershell/module/Microsoft.PowerShell.Management/Get-Process) Cmdlet aus und zeigt die Ergebnisse an, wie Sie Sie mit pwrsh.exe anzeigen. Anschließend werden die aktuellen Daten und die aktuelle Zeit in Deutsch ausgegeben.

 [Host03-Beispiel](./host03-sample.md) Dieses Beispiel zeigt, wie eine interaktive konsolenbasierte Host Anwendung erstellt wird, die Befehle in der Befehlszeile liest, die Befehle ausführt und die Ergebnisse anschließend in der Konsole anzeigt.

 [Host04-Beispiel](./host04-sample.md) Dieses Beispiel zeigt, wie eine interaktive konsolenbasierte Host Anwendung erstellt wird, die Befehle in der Befehlszeile liest, die Befehle ausführt und die Ergebnisse anschließend in der Konsole anzeigt. Diese Hostanwendung unterstützt auch das Anzeigen von Eingabeaufforderungen, die es den Benutzern ermöglichen, mehrere Auswahlmöglichkeiten anzugeben.

 [Host05-Beispiel](./host05-sample.md) Dieses Beispiel zeigt, wie eine interaktive konsolenbasierte Host Anwendung erstellt wird, die Befehle in der Befehlszeile liest, die Befehle ausführt und die Ergebnisse anschließend in der Konsole anzeigt. Diese Host Anwendung unterstützt auch Aufrufe von Remote Computern mithilfe der Cmdlets [Enter-PSSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) und [Exit-PSSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) .

 [Host06-Beispiel](./host06-sample.md) Dieses Beispiel zeigt, wie eine interaktive konsolenbasierte Host Anwendung erstellt wird, die Befehle in der Befehlszeile liest, die Befehle ausführt und die Ergebnisse anschließend in der Konsole anzeigt. Darüber hinaus verwendet dieses Beispiel die Tokenizer-APIs, um die Farbe des vom Benutzer eingegebenen Texts anzugeben.

## <a name="see-also"></a>Weitere Informationen
