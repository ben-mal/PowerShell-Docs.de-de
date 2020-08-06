---
title: Unterstützung für Platzhalter in Cmdlet-Parametern
ms.date: 08/26/2019
ms.openlocfilehash: 062e3d50dddd0bc84e57f5254a93289acbabe38b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786406"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a>Unterstützung für Platzhalter in Cmdlet-Parametern

Häufig müssen Sie ein Cmdlet so entwerfen, dass es für eine Gruppe von Ressourcen und nicht für eine einzelne Ressource ausgeführt wird. Beispielsweise muss ein Cmdlet möglicherweise alle Dateien in einem Datenspeicher mit dem gleichen Namen oder der gleichen Erweiterung suchen. Beim Entwerfen eines Cmdlets, das für eine Gruppe von Ressourcen ausgeführt werden soll, müssen Sie Unterstützung für Platzhalter Zeichen bereitstellen.

> [!NOTE]
> Die Verwendung von Platzhalter Zeichen wird manchmal als " *glob"* bezeichnet.

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a>Windows PowerShell-Cmdlets, die Platzhalter verwenden

 Viele Windows PowerShell-Cmdlets unterstützen Platzhalter Zeichen für Ihre Parameterwerte. Beispielsweise unterstützt fast jedes Cmdlet mit dem-Parameter oder dem-Parameter Platzhalter `Name` `Path` Zeichen für diese Parameter. (Obwohl die meisten Cmdlets, die über einen Parameter verfügen, `Path` auch über einen `LiteralPath` Parameter verfügen, der keine Platzhalter Zeichen unterstützt.) Der folgende Befehl zeigt, wie ein Platzhalter Zeichen verwendet wird, um alle Cmdlets in der aktuellen Sitzung zurückzugeben, deren Name das Get-Verb enthält.

 `Get-Command get-*`

## <a name="supported-wildcard-characters"></a>Unterstützte Platzhalter Zeichen

Windows PowerShell unterstützt die folgenden Platzhalter Zeichen.

| Platzhalter |                             Beschreibung                             |  Beispiel   |     Treffer      | Stimmt nicht überein mit |
| -------- | ------------------------------------------------------------------- | ---------- | ---------------- | -------------- |
| *        | Entspricht 0 (null) oder mehr Zeichen, beginnend an der angegebenen Position. | `a*`       | A, AG, Apple     |                |
| ?        | Entspricht einem beliebigen Zeichen an der angegebenen Position.                     | `?n`       | Ein, in, ein       | an            |
| [ ]      | Entspricht einem Zeichenbereich.                                       | `[a-l]ook` | Buch, Kochen, ansehen | Nook, hat     |
| [ ]      | Entspricht den angegebenen Zeichen                                    | `[bn]ook`  | Buch, Nook       | Kochen, sehen     |

Wenn Sie Cmdlets entwerfen, die Platzhalter Zeichen unterstützen, lassen Sie Kombinationen von Platzhalter Zeichen zu. Der folgende Befehl verwendet z. b. das `Get-ChildItem` Cmdlet zum Abrufen aller txt-Dateien, die sich im Ordner c:\techdocs befinden und mit den Buchstaben "a" bis "l" beginnen.

`Get-ChildItem c:\techdocs\[a-l]\*.txt`

Der vorherige Befehl verwendet den Bereichs `[a-l]` Platzhalter, um anzugeben, dass der Dateiname mit den Zeichen "a" bis "l" beginnen soll, und verwendet das `*` Platzhalter Zeichen als Platzhalter für alle Zeichen zwischen dem ersten Buchstaben des Datei namens und der Erweiterung " **. txt** ".

Im folgenden Beispiel wird ein Bereichs Halter Muster verwendet, das den Buchstaben "d" ausschließt, aber alle anderen Buchstaben von "a" bis "f" umfasst.

`Get-ChildItem c:\techdocs\[a-cef]\*.txt`

## <a name="handling-literal-characters-in-wildcard-patterns"></a>Verarbeiten von Literalzeichen in Platzhalter Mustern

Wenn das von Ihnen angegebene Platzhalter Muster Literalzeichen enthält, die nicht als Platzhalter Zeichen interpretiert werden sollen, verwenden Sie das Graviszeichen-Zeichen ( `` ` `` ) als Escapezeichen. Wenn Sie die Literalzeichen int der PowerShell-API angeben, verwenden Sie einen einzigen Backtick. Wenn Sie an der PowerShell-Eingabeaufforderung Literalzeichen angeben, verwenden Sie zwei Backticks.

Das folgende Muster enthält z. b. zwei eckige Klammern, die wörtlich genommen werden müssen.

Wenn Sie in der PowerShell-API verwendet wird, verwenden Sie:

- "John Smith \` [* ']"

Wenn Sie von der PowerShell-Eingabeaufforderung verwendet wird:

- "John Smith \` \` [* \` ']"

Dieses Muster entspricht "John Smith [Marketing]" oder "John Smith [Development]". Beispiel:

```
PS> "John Smith [Marketing]" -like "John Smith ``[*``]"
True

PS> "John Smith [Development]" -like "John Smith ``[*``]"
True
```

## <a name="cmdlet-output-and-wildcard-characters"></a>Cmdlet-Ausgabe und Platzhalter Zeichen

Wenn Cmdlet-Parameter Platzhalter Zeichen unterstützen, generiert der Vorgang normalerweise eine Array Ausgabe.
Gelegentlich ist es nicht sinnvoll, eine Array Ausgabe zu unterstützen, da der Benutzer möglicherweise nur ein einzelnes Element verwendet. Beispielsweise `Set-Location` unterstützt das Cmdlet die Array Ausgabe nicht, da der Benutzer nur einen einzigen Speicherort festlegt. In diesem Fall unterstützt das Cmdlet weiterhin Platzhalter Zeichen, aber es erzwingt die Auflösung an einem einzelnen Speicherort.

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)

[Wildcardpattern-Klasse](/dotnet/api/system.management.automation.wildcardpattern)
