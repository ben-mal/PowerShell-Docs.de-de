---
description: Beschreibt einfachere, natürlichere Methoden für Skript Filter für Objekt Auflistungen.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: dbd30d566414f784e7d5eca04af716c2bf1642b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603157"
---
# <a name="about_simplified_syntax"></a>about_Simplified_Syntax

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt einfachere, natürlichere Methoden für Skript Filter für Objekt Auflistungen.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Mithilfe der vereinfachten Syntax, die in Windows PowerShell 3,0 eingeführt wurde, können Sie einige Filter Befehle erstellen, ohne Skriptblöcke zu verwenden. Die vereinfachte Syntax ähnelt in natürlicher Sprache und ist in erster Linie bei Auflistungen von Objekten nützlich, die in Befehle `Where-Object` und in `ForEach-Object` den zugehörigen Aliasen und angezeigt werden `where` `foreach` .

Sie können eine Methode für die Member einer Auflistung verwenden (in der Regel ein Array), ohne auf die automatische Variable `$_` innerhalb eines Skript Blocks zu verweisen.

Beachten Sie die folgenden beiden Aufrufe:

### <a name="standard-syntax"></a>Standard Syntax

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }
```

### <a name="simplified-syntax"></a>Vereinfachte Syntax

Unter der vereinfachten Syntax werden Vergleichs Operatoren, die an Membern von Objekten in einer Auflistung arbeiten, als Parameter behandelt. Sie können eine Methode für Objekte in einer Auflistung aufrufen, ohne auf die automatische Variable `$_` innerhalb eines Skript Blocks zu verweisen.
Vergleichen Sie die folgenden beiden Aufrufe mit denen des vorherigen Beispiels:

```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

Obwohl beide Syntaxen funktionieren, gibt die vereinfachte Syntax Ergebnisse zurück, ohne dass auf die automatische Variable `$_` in einem Skriptblock verwiesen wird.
Der Methodenname `GetKeyAlgorithm` wird als Parameter von behandelt `ForEach-Object` .
Mit dem zweiten Befehl werden dieselben Ergebnisse zurückgegeben, jedoch ohne Fehler, da die vereinfachte Syntax nicht versucht, Ergebnisse für Elemente zurückzugeben, für die das angegebene Argument nicht gilt.

In diesem Beispiel wird die- `Process` Eigenschaft `Description` als Element namens Parameter an den- `ForEach-Object` Befehl übergeben. Die Ergebnisse sind Beschreibungen aktiver Prozesse.

```powershell
Get-Process | foreach Description
```

In diesem Beispiel wird die- `DirectoryInfo` Methode `GetFiles` als Elementname-Parameter des Befehls übergeben `ForEach-Object` .  
Die-Methode wird mit dem Suchmuster Parameter aufgerufen `.*` .  
Die Ergebnisse sind `FileInfo` Datensätze für alle ausgeblendeten Dateien im Unix-Stil in Benutzerbasis Verzeichnissen. 

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a>SIEHE AUCH

- [about_Comparison_Operators](about_Comparison_Operators.md)
- [about_Foreach](about_Foreach.md)
- [Where-Object](xref:Microsoft.PowerShell.Core.Where-Object)
- [ForEach-Objekt](xref:Microsoft.PowerShell.Core.ForEach-Object)

