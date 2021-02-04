---
description: Ermöglicht Ihnen, anzugeben, welche Namespaces in der Sitzung verwendet werden.
Locale: en-US
ms.date: 01/19/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: e3bdf9e1285fb8eaa2bdd83a03cce5bd1baa0e8b
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "98620155"
---
# <a name="about-using"></a>Informationen zur Verwendung von

## <a name="short-description"></a>KURZE BESCHREIBUNG
Ermöglicht Ihnen, anzugeben, welche Namespaces in der Sitzung verwendet werden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Mit der- `using` Anweisung können Sie angeben, welche Namespaces in der Sitzung verwendet werden. Das Hinzufügen von Namespaces vereinfacht die Verwendung von .NET-Klassen und-Membern und ermöglicht das Importieren von Klassen aus Skript Modulen und Assemblys.

Die- `using` Anweisungen müssen vor allen anderen Anweisungen in einem Skript oder Modul stehen. Es kann keine nicht kommentierten Anweisung vorangestellt werden, einschließlich der Parameter.

Die `using` Anweisung darf keine Variablen enthalten.

Die- `using` Anweisung sollte nicht mit dem bereichsmodifizierer `using:` für Variablen verwechselt werden. Weitere Informationen finden Sie unter [about_Remote_Variables](about_Remote_Variables.md).

## <a name="namespace-syntax"></a>Namespace Syntax

So geben Sie .NET-Namespaces an, aus denen Typen aufgelöst werden sollen:

```
using namespace <.NET-namespace>
```

Durch die Angabe eines Namespace wird es einfacher, auf Typen anhand ihrer Kurznamen zu verweisen.

## <a name="module-syntax"></a>Modul Syntax

So laden Sie Klassen aus einem PowerShell-Modul:

```
using module <module-name>
```

Der Wert von `<module-name>` kann ein Modulname, eine vollständige Modul Spezifikation oder ein Pfad zu einer Modul Datei sein.

Wenn `<module-name>` ein Pfad ist, kann der Pfad voll qualifiziert oder relativ sein. Ein relativer Pfad wird relativ zum Skript aufgelöst, das die using-Anweisung enthält.

Wenn `<module-name>` eine Name-oder Modul Spezifikation ist, durchsucht PowerShell den **psmodulepath** nach dem angegebenen Modul.

Eine Modul Spezifikation ist eine Hash Tabelle mit den folgenden Schlüsseln.

- `ModuleName` - **Erforderlich** Gibt den Namen des Moduls an.
- `GUID` - **Optional** Gibt die GUID des Moduls an.
- Es ist auch **erforderlich** , einen der drei folgenden Schlüssel anzugeben. Diese Schlüssel können nicht gleichzeitig verwendet werden.
  - `ModuleVersion` : Gibt eine zulässige Mindestversion des Moduls an.
  - `RequiredVersion` : Gibt eine exakte, erforderliche Version des Moduls an.
  - `MaximumVersion` : Gibt die maximal zulässige Version des Moduls an.

Die- `using module` Anweisung importiert Klassen aus dem Stamm Modul ( `ModuleToProcess` ) eines Skript Moduls oder eines binären Moduls. Klassen, die in geschposteten Modulen oder Klassen definiert sind, die in Skripts definiert sind, die in das Modul eingefügt werden, werden nicht konsistent importiert. Klassen, die für Benutzer außerhalb des Moduls verfügbar sein sollen, sollten im Stamm Modul definiert werden.

Während der Entwicklung eines Skript Moduls ist es üblich, Änderungen am Code vorzunehmen und dann die neue Version des Moduls `Import-Module` mit dem **Force** -Parameter zu laden. Dies funktioniert nur bei Änderungen an Funktionen im Stamm Modul. `Import-Module` führt keine erneuten Laden von Netz Modulen aus. Außerdem gibt es keine Möglichkeit, aktualisierte Klassen zu laden.

Um sicherzustellen, dass Sie die neueste Version ausführen, müssen Sie das Modul mit dem `Remove-Module` Cmdlet entladen. `Remove-Module` entfernt das Stamm Modul, alle in den Modulen definierten Klassen und Klassen. Anschließend können Sie das Modul und die Klassen mithilfe von `Import-Module` und der-Anweisung erneut laden `using module` .

## <a name="assembly-syntax"></a>Assemblysyntax

So laden Sie Typen aus einer .NET-Assembly vorab:

```
using assembly <.NET-assembly-path>
```

Durch das Laden einer Assembly werden .NET-Typen aus dieser Assembly zur Analysezeit vorab in ein Skript geladen. Dies ermöglicht es Ihnen, neue PowerShell-Klassen zu erstellen, die Typen aus der vorgeladenen Assembly verwenden.

Wenn Sie keine neuen PowerShell-Klassen erstellen, verwenden Sie `Add-Type` stattdessen das-Cmdlet. Weitere Informationen finden Sie unter [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).

## <a name="examples"></a>Beispiele

### <a name="example-1---add-namespaces-for-typename-resolution"></a>Beispiel 1: Hinzufügen von Namespaces für die Typname-Auflösung

Mit dem folgenden Skript wird der kryptografiehash für die Zeichenfolge "Hallo Welt" abgerufen.

Beachten Sie `using namespace System.Text` , wie und `using namespace System.IO` die Verweise auf `[UnicodeEncoding]` in `System.Text` und `[Stream]` und auf `[MemoryStream]` in vereinfachen `System.IO` .

```powershell
using namespace System.Text
using namespace System.IO

[string]$string = "Hello World"
## Valid values are "SHA1", "SHA256", "SHA384", "SHA512", "MD5"
[string]$algorithm = "SHA256"

[byte[]]$stringbytes = [UnicodeEncoding]::Unicode.GetBytes($string)

[Stream]$memorystream = [MemoryStream]::new($stringbytes)
$hashfromstream = Get-FileHash -InputStream $memorystream `
  -Algorithm $algorithm
$hashfromstream.Hash.ToString()
```

### <a name="example-2---load-classes-from-a-script-module"></a>Beispiel 2: Laden von Klassen aus einem Skript Modul

In diesem Beispiel verfügen wir über ein PowerShell-Skript Modul namens **Cardgames** , das die folgenden Klassen definiert:

- **Cardgames. Karten**
- **Cardgames. Card**

`Import-Module` und die- `#requires` Anweisung importiert nur die Modulfunktionen, Aliase und Variablen, wie vom Modul definiert. Klassen werden nicht importiert. Der `using module` Befehl importiert das Modul und lädt auch die Klassendefinitionen.

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a>Beispiel 3: Laden von Klassen aus einer Assembly

In diesem Beispiel wird eine Assembly geladen, damit Ihre Klassen zum Erstellen neuer PowerShell-Klassen verwendet werden können. Mit dem folgenden Skript wird eine neue PowerShell-Klasse erstellt, die von der **DirectoryContext** -Klasse abgeleitet wird.

```powershell
using assembly 'C:\Program Files\PowerShell\7\System.DirectoryServices.dll'
using namespace System.DirectoryServices.ActiveDirectory

class myDirectoryClass : System.DirectoryServices.ActiveDirectory.DirectoryContext
{

  [DirectoryContext]$domain

  myDirectoryClass([DirectoryContextType]$ctx) : base($ctx)
  {
    $this.domain = [DirectoryContext]::new([DirectoryContextType]$ctx)
  }

}

$myDomain = [myDirectoryClass]::new([DirectoryContextType]::Domain)
$myDomain
```

```Output
domain                                                    Name UserName ContextType
------                                                    ---- -------- -----------
System.DirectoryServices.ActiveDirectory.DirectoryContext                    Domain
```
