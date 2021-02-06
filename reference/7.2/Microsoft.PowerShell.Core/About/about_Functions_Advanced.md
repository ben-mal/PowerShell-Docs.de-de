---
description: Führt erweiterte Funktionen ein, die eine Möglichkeit zum Erstellen von Cmdlets mithilfe von Skripts sind.
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: a0b8b027c91f2adedfcecd07bfc80392c1b1e071
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99598398"
---
# <a name="about-functions-advanced"></a>Informationen zu erweiterten Funktionen

## <a name="short-description"></a>KURZE BESCHREIBUNG
Führt erweiterte Funktionen ein, die eine Möglichkeit zum Erstellen von Cmdlets mithilfe von Skripts sind.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Ein Cmdlet ist ein einzelner Befehl, der an der Pipeline Semantik von PowerShell beteiligt ist. Dies schließt binäre Cmdlets, erweiterte Skriptfunktionen, cdxml und Workflows ein.

Erweiterte Funktionen ermöglichen es Ihnen, Cmdlets zu erstellen, die als PowerShell-Funktion geschrieben werden. Erweiterte Funktionen vereinfachen die Erstellung von Cmdlets, ohne ein binäres Cmdlet schreiben und kompilieren zu müssen. Binäre Cmdlets sind .NET-Klassen, die in einer .NET-Sprache geschrieben werden, z. b. c#.

Erweiterte Funktionen verwenden das- `CmdletBinding` Attribut, um Sie als Funktionen zu identifizieren, die wie Cmdlets fungieren. Das- `CmdletBinding` Attribut ähnelt dem Cmdlet-Attribut, das in kompilierten Cmdlet-Klassen verwendet wird, um die Klasse als Cmdlet zu identifizieren. Weitere Informationen zu diesem Attribut finden Sie unter [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).

Das folgende Beispiel zeigt eine Funktion, die einen Namen akzeptiert und dann eine Begrüßung mit dem angegebenen Namen ausgibt. Beachten Sie außerdem, dass diese Funktion einen Namen definiert, der ein Verb-(senden) und ein Substantiv-Paar (Gruß) wie das Verb-Substantiv-Paar eines kompilierten Cmdlets enthält. Es ist jedoch nicht erforderlich, dass für Funktionen ein Verb-Substantiv-Name vorhanden ist.

```powershell
function Send-Greeting
{
    [CmdletBinding()]
    Param(
        [Parameter(Mandatory=$true)]
        [string] $Name
    )

    Process
    {
        Write-Host ("Hello " + $Name + "!")
    }
}
```

Die Parameter der Funktion werden mithilfe des Parameter-Attributs deklariert.
Dieses Attribut kann allein verwendet werden, oder es kann mit dem Alias-Attribut oder mit mehreren anderen Parameter Validierungs Attributen kombiniert werden. Weitere Informationen zum Deklarieren von Parametern (einschließlich dynamischer Parameter, die zur Laufzeit hinzugefügt werden) finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

Die tatsächliche Arbeit der Previous-Funktion wird im Process-Block ausgeführt. Dies entspricht der processingrecord-Methode, die von den kompilierten Cmdlets verwendet wird, um die Daten zu verarbeiten, die an das Cmdlet übergeben werden. Dieser Block wird zusammen mit den BEGIN-und End-Blöcken im [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) Thema beschrieben.

Erweiterte Funktionen unterscheiden sich von den kompilierten Cmdlets wie folgt:

- Die erweiterte Funktionsparameter Bindung löst keine Ausnahme aus, wenn ein Array von Zeichen folgen an einen booleschen Parameter gebunden ist.
- Das validateset-Attribut und das validatepattern-Attribut können benannte Parameter nicht übergeben.
- Erweiterte Funktionen können nicht in Transaktionen verwendet werden.

## <a name="see-also"></a>SIEHE AUCH

[about_Functions](about_Functions.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)
