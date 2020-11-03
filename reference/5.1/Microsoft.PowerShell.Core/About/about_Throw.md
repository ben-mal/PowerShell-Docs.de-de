---
description: Beschreibt das Throw-Schlüsselwort, das einen Abbruchfehler generiert.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_throw?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Throw
ms.openlocfilehash: caac7679e2c7ecd21b4fa9e43ab76681ee3faed5
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222484"
---
# <a name="about-throw"></a>Informationen zu Throw

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt das Throw-Schlüsselwort, das einen Abbruchfehler generiert.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Das throw-Schlüsselwort verursacht einen abschließenden Fehler. Sie können das throw-Schlüsselwort verwenden, um die Verarbeitung eines Befehls, einer Funktion oder eines Skripts zu unterbinden.

Beispielsweise können Sie das throw-Schlüsselwort im Skriptblock einer if-Anweisung verwenden, um auf eine Bedingung oder den catch-Block einer try-catch-all-Anweisung zu antworten. Sie können auch das throw-Schlüsselwort in einer Parameter Deklaration verwenden, um einen Funktionsparameter als obligatorisch zu kennzeichnen.

Das throw-Schlüsselwort kann ein beliebiges Objekt auslösen, z. b. eine Zeichenfolge für eine Benutzer Nachricht oder das Objekt, das den Fehler

## <a name="syntax"></a>SYNTAX

Die Syntax des Throw-Schlüssel Worts lautet wie folgt:

```powershell
throw [<expression>]
```

Der Ausdruck in der Throw-Syntax ist optional. Wenn die throw-Anweisung nicht in einem catch-Block angezeigt wird und keinen Ausdruck enthält, generiert Sie einen Skript Fehler.

```powershell
C:\PS> throw

ScriptHalted
At line:1 char:6
+ throw <<<<
+ CategoryInfo          : OperationStopped: (:) [], RuntimeException
+ FullyQualifiedErrorId : ScriptHalted
```

Wenn das throw-Schlüsselwort in einem catch-Block ohne einen Ausdruck verwendet wird, wird die aktuelle RuntimeException erneut ausgelöst. Weitere Informationen finden Sie unter about_Try_Catch_Finally.

## <a name="throwing-a-string"></a>Auslösen einer Zeichenfolge

Der optionale Ausdruck in einer throw-Anweisung kann eine Zeichenfolge sein, wie im folgenden Beispiel gezeigt:

```powershell
C:\PS> throw "This is an error."

This is an error.
At line:1 char:6
+ throw <<<<  "This is an error."
+ CategoryInfo          : OperationStopped: (This is an error.:String) [], R
untimeException
+ FullyQualifiedErrorId : This is an error.
```

## <a name="throwing-other-objects"></a>auslösen anderer Objekte

Der Ausdruck kann auch ein Objekt sein, das das Objekt, das den PowerShell-Prozess darstellt, auslöst, wie im folgenden Beispiel gezeigt:

```powershell
C:\PS> throw (get-process PowerShell)

System.Diagnostics.Process (PowerShell)
At line:1 char:6
+ throw <<<<  (get-process PowerShell)
+ CategoryInfo          : OperationStopped: (System.Diagnostics.Process (Pow
erShell):Process) [],
RuntimeException
+ FullyQualifiedErrorId : System.Diagnostics.Process (PowerShell)
```

Sie können die TargetObject-Eigenschaft des ErrorRecord-Objekts in der $Error automatischen Variable verwenden, um den Fehler zu untersuchen.

```powershell
C:\PS> $error[0].targetobject

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
319      26    61016      70864   568     3.28   5548 PowerShell
```

Sie können auch ein ErrorRecord-Objekt oder eine Microsoft .NET Framework-Ausnahme auslösen. Im folgenden Beispiel wird das throw-Schlüsselwort verwendet, um ein System. FormatException-Objekt auszulösen.

```powershell
C:\PS> $formatError = new-object system.formatexception

C:\PS> throw $formatError

One of the identified items was in an invalid format.
At line:1 char:6
+ throw <<<<  $formatError
+ CategoryInfo          : OperationStopped: (:) [], FormatException
+ FullyQualifiedErrorId : One of the identified items was in an invalid
format.
```

## <a name="resulting-error"></a>Ergebnis Fehler

Das throw-Schlüsselwort kann ein ErrorRecord-Objekt generieren. Die Exception-Eigenschaft des ErrorRecord-Objekts enthält ein RuntimeException-Objekt. Der Rest des ErrorRecord-Objekts und das RuntimeException-Objekt variieren mit dem Objekt, das das throw-Schlüsselwort auslöst.

Das RuntimeException-Objekt ist in einem ErrorRecord-Objekt umschließt, und das ErrorRecord-Objekt wird automatisch in der $Error automatischen Variablen gespeichert.

## <a name="using-throw-to-create-a-mandatory-parameter"></a>Verwenden von Throw zum Erstellen eines obligatorischen Parameters

Sie können das throw-Schlüsselwort verwenden, um einen Funktionsparameter als obligatorisch zu kennzeichnen.

Dies ist eine Alternative zur Verwendung des obligatorischen Parameters des Parameter Schlüsselworts. Wenn Sie den obligatorischen Parameter verwenden, fordert das System den Benutzer zum erforderlichen Parameterwert auf. Wenn Sie das throw-Schlüsselwort verwenden, wird der Befehl beendet und der Fehler Daten Satz angezeigt.

Beispielsweise macht das throw-Schlüsselwort im Parameter Teil Ausdruck den path-Parameter zu einem erforderlichen Parameter in der Funktion.

In diesem Fall löst das throw-Schlüsselwort eine Meldungs Zeichenfolge aus, aber es ist das vorhanden sein des Throw-Schlüssel Worts, das den abschließenden Fehler generiert, wenn der path-Parameter nicht angegeben ist. Der Ausdruck, der auf throw folgt, ist optional.

```powershell
function Get-XMLFiles
{
  param ($path = $(throw "The Path parameter is required."))
  dir -path $path\*.xml -recurse |
    sort lastwritetime |
      ft lastwritetime, attributes, name  -auto
}
```

## <a name="see-also"></a>SIEHE AUCH

[about_Break](about_Break.md)

[about_Continue](about_Continue.md)

[about_Scopes](about_Scopes.md)

[about_Trap](about_Trap.md)

[about_Try_Catch_Finally](about_Try_Catch_Finally.md)
