---
description: Beschreibt das Throw-Schlüsselwort, das einen Abbruchfehler generiert.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: d4bf0ea00145c03522d4db952be201c877c9d50c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222871"
---
# <a name="about-throw"></a>Informationen zu Throw

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt das Throw-Schlüsselwort, das einen Abbruchfehler generiert.

## <a name="long-description"></a>Lange Beschreibung

Das throw-Schlüsselwort verursacht einen abschließenden Fehler. Sie können das throw-Schlüsselwort verwenden, um die Verarbeitung eines Befehls, einer Funktion oder eines Skripts zu unterbinden.

Beispielsweise können Sie das throw-Schlüsselwort im Skriptblock einer if-Anweisung verwenden, um auf eine Bedingung oder den catch-Block einer try-catch-all-Anweisung zu antworten. Sie können auch das throw-Schlüsselwort in einer Parameter Deklaration verwenden, um einen Funktionsparameter als obligatorisch zu kennzeichnen.

Das throw-Schlüsselwort kann ein beliebiges Objekt auslösen, z. b. eine Zeichenfolge für eine Benutzer Nachricht oder das Objekt, das den Fehler

## <a name="syntax"></a>Syntax

Die Syntax des Throw-Schlüssel Worts lautet wie folgt:

```powershell
throw [<expression>]
```

Der Ausdruck in der Throw-Syntax ist optional. Wenn die throw-Anweisung nicht in einem catch-Block angezeigt wird und keinen Ausdruck enthält, generiert Sie einen Skript Fehler.

```powershell
C:\PS> throw

Exception: ScriptHalted
```

Wenn das throw-Schlüsselwort in einem catch-Block ohne einen Ausdruck verwendet wird, wird die aktuelle RuntimeException erneut ausgelöst. Weitere Informationen finden Sie unter about_Try_Catch_Finally.

## <a name="throwing-a-string"></a>Auslösen einer Zeichenfolge

Der optionale Ausdruck in einer throw-Anweisung kann eine Zeichenfolge sein, wie im folgenden Beispiel gezeigt:

```powershell
C:\PS> throw "This is an error."

Exception: This is an error.
```

## <a name="throwing-other-objects"></a>Auslösen anderer Objekte

Der Ausdruck kann auch ein Objekt sein, das das Objekt, das den PowerShell-Prozess darstellt, auslöst, wie im folgenden Beispiel gezeigt:

```powershell
C:\PS> throw (get-process Pwsh)

Exception: System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh) System.Diagnostics.Process (pwsh)
```

Sie können die TargetObject-Eigenschaft des ErrorRecord-Objekts in der $Error automatischen Variable verwenden, um den Fehler zu untersuchen.

```powershell
C:\PS> $error[0].targetobject

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    125   174.44     229.57      23.61    1548   2 pwsh
     63    44.07      81.95       1.75    1732   2 pwsh
     63    43.32      77.65       1.48    9092   2 pwsh
```

Sie können auch ein ErrorRecord-Objekt oder eine .NET-Ausnahme auslösen. Im folgenden Beispiel wird das throw-Schlüsselwort verwendet, um ein System. FormatException-Objekt auszulösen.

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

OperationStopped: One of the identified items was in an invalid format.
```

## <a name="the-resulting-error"></a>Der resultierende Fehler

Das throw-Schlüsselwort kann ein ErrorRecord-Objekt generieren. Die Exception-Eigenschaft des ErrorRecord-Objekts enthält ein RuntimeException-Objekt. Der Rest des ErrorRecord-Objekts und das RuntimeException-Objekt variieren mit dem Objekt, das das throw-Schlüsselwort auslöst.

Das RuntimeException-Objekt ist in einem ErrorRecord-Objekt umschließt, und das ErrorRecord-Objekt wird automatisch in der $Error automatischen Variablen gespeichert.

## <a name="using-throw-to-create-a-mandatory-parameter"></a>Verwenden von Throw zum Erstellen eines obligatorischen Parameters

Verwenden Sie im Gegensatz zu früheren Versionen von PowerShell nicht das throw-Schlüsselwort für die Parameter Validierung. Die richtige Vorgehensweise finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md) .

## <a name="see-also"></a>Weitere Informationen:

- [about_Break](about_Break.md)
- [about_Continue](about_Continue.md)
- [about_Scopes](about_Scopes.md)
- [about_Trap](about_Trap.md)
- [about_Try_Catch_Finally](about_Try_Catch_Finally.md)
