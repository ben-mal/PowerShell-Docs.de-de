---
ms.date: 09/13/2016
ms.topic: reference
title: Schreiben eines Windows PowerShell-Moduls
description: Schreiben eines Windows PowerShell-Moduls
ms.openlocfilehash: 307241f0fb4d12c1a5cbd651a0ae4d5303098b27
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659438"
---
# <a name="writing-a-windows-powershell-module"></a>Schreiben eines Windows PowerShell-Moduls

Dieses Dokument ist für Administratoren, Skriptentwickler und Cmdlet-Entwickler geschrieben, die Ihre Windows PowerShell-Cmdlets Verpacken und verteilen müssen. Mithilfe von Windows PowerShell-Modulen können Sie Windows PowerShell-Lösungen Verpacken und verteilen, ohne eine kompilierte Sprache zu verwenden.

Mit Windows PowerShell-Modulen können Sie Ihren Windows PowerShell-Code in eigenständige, wiederverwendbare Einheiten partitionieren, organisieren und abstrahieren. Mit diesen wiederverwendbaren Einheiten können Sie Ihre Module problemlos direkt für andere freigeben. Wenn Sie ein Skriptentwickler sind, können Sie auch Drittanbieter Module neu verpacken, um benutzerdefinierte skriptbasierte Anwendungen zu erstellen. Module, die mit Modulen in anderen Skriptsprachen wie z. b. perl und python vergleichbar sind, ermöglichen die Bereitstellung von Skript Erstellungs Lösungen, die wiederverwendbare, verteilbare Komponenten verwenden. der zusätzliche Vorteil besteht darin, dass Sie mehrere Komponenten erneut Verpacken und abstrahieren können, um benutzerdefinierte Lösungen

Windows PowerShell behandelt in den meisten Fällen jeden gültigen Windows PowerShell-Skriptcode, der in einer psm1-Datei gespeichert ist, als Modul. PowerShell behandelt auch automatisch jede binäre Cmdlet-Assembly als Modul. Sie können jedoch auch ein Modul (oder genauer gesagt, ein Modul Manifest) verwenden, um eine gesamte Projekt Mappe zusammenzufassen. In den folgenden Szenarien werden typische Verwendungsmöglichkeiten für Windows PowerShell-Module beschrieben.

### <a name="libraries"></a>Bibliotheken

Module können zum Verpacken und Verteilen von zusammenhängenden Bibliotheken von Funktionen verwendet werden, die allgemeine Aufgaben ausführen. In der Regel verwenden die Namen dieser Funktionen ein oder mehrere Nomen, die die allgemeine Aufgabe widerspiegeln, für die Sie verwendet werden. Diese Funktionen können auch .NET Framework Klassen in ähneln, dass Sie öffentliche und private Member haben können. Eine Bibliothek kann z. b. eine Reihe von Funktionen für Dateiübertragungen enthalten. In diesem Fall kann das Substantiv, das die allgemeine Aufgabe widerspiegelt, "file" lauten.

### <a name="configuration"></a>Konfiguration

Module können verwendet werden, um Ihre Umgebung anzupassen, indem bestimmte Cmdlets, Anbieter, Funktionen und Variablen hinzugefügt werden.

### <a name="compiled-code-development-and-distribution"></a>Entwicklung und Verteilung kompilierter Codes

Cmdlet-und Anbieter Entwickler können Module verwenden, um Ihren kompilierten Code zu testen und zu verteilen, ohne Snap-Ins erstellen zu müssen. Sie können die Assembly, die den kompilierten Code enthält, als Modul (ein binäres Modul) importieren, ohne Snap-Ins erstellen und registrieren zu müssen.

## <a name="see-also"></a>Weitere Informationen

[Grundlegendes zum Windows PowerShell-Modul](./understanding-a-windows-powershell-module.md)

[Schreiben eines PowerShell-Skriptmoduls](./how-to-write-a-powershell-script-module.md)

[Schreiben eines PowerShell-Binärmoduls](./how-to-write-a-powershell-binary-module.md)

[Schreiben eines PowerShell-Binärmoduls](how-to-write-a-powershell-module-manifest.md)

[Ändern des Installationspfads PSModulePath](./modifying-the-psmodulepath-installation-path.md)

[Importieren eines PowerShell-Moduls](./importing-a-powershell-module.md)

[Installieren eines PowerShell-Moduls](./installing-a-powershell-module.md)
