---
ms.date: 09/12/2016
ms.topic: reference
title: Ablegen der kommentarbasierten Hilfe in Funktionen
description: Ablegen der kommentarbasierten Hilfe in Funktionen
ms.openlocfilehash: 3bd72f0c71d8f6ad54c43c99f044423c072fdeeb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658199"
---
# <a name="placing-comment-based-help-in-functions"></a>Ablegen der kommentarbasierten Hilfe in Funktionen

In diesem Thema wird erläutert, wo Sie eine Kommentar basierte Hilfe für eine Funktion platzieren können, damit das `Get-Help` Cmdlet das Kommentar basierte Hilfethema der richtigen Funktion zuordnet.

## <a name="where-to-place-comment-based-help-for-a-function"></a>Speicherort Comment-Based Hilfe für eine Funktion

- Am Anfang des Funktions Texts.

- Am Ende des Funktions Texts.

- Vor dem- `Function` Schlüsselwort. Wenn sich die Funktion in einem Skript-oder Skript Modul befindet, darf zwischen der letzten Zeile der Kommentar basierten Hilfe und dem-Schlüsselwort nicht mehr als eine Leerzeile vorhanden sein `Function` . Andernfalls ordnet die `Get-Help` Hilfe dem Skript und nicht der-Funktion zu.

## <a name="examples-of-help-placement-in-a-function"></a>Beispiele für die Platzierung von Hilfe in einer Funktion

Die folgenden Beispiele zeigen jede der drei Platzierungs Optionen für die Kommentar basierte Hilfe für eine Funktion.

### <a name="help-at-the-beginning-of-a-function-body"></a>Hilfe am Anfang eines Funktions Texts

Das folgende Beispiel zeigt einen Kommentar basierten am Anfang eines Funktions Texts.

```powershell
function MyProcess
{
    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>

    Get-Process powershell
}
```

### <a name="help-at-the-end-of-a-function-body"></a>Hilfe am Ende eines Funktions Texts

 Das folgende Beispiel zeigt am Ende eines Funktions Texts einen Kommentar basierten Text.

```powershell
function MyFunction
{
    Get-Process powershell

    <#
       .Description
       The MyProcess function gets the Windows PowerShell process.
    #>
}
```

### <a name="help-before-the-function-keyword"></a>Hilfe vor dem Function-Schlüsselwort

 In den folgenden Beispielen wird die Kommentar basierte Zeile vor dem Function-Schlüsselwort gezeigt.

```powershell
<#
    .Description
    The MyProcess function gets the Windows PowerShell process.
#>
function MyFunction { Get-Process powershell}
```
