---
description: Beschreibt das Attribut, mit dem eine Funktion wie ein kompiliertes Cmdlet funktioniert.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_CmdletBindingAttribute
ms.openlocfilehash: 816bee647702fca4a2b9196491b2525f0338ab31
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222287"
---
# <a name="about-functions-cmdletbindingattribute"></a>Informationen zu Funktionen cmdletbindingattribute

## <a name="short-description"></a>Kurze Beschreibung
Beschreibt das Attribut, mit dem eine Funktion wie ein kompiliertes Cmdlet funktioniert.

## <a name="long-description"></a>Lange Beschreibung

Das- `CmdletBinding` Attribut ist ein Attribut von Funktionen, das Sie wie in c# geschriebene kompilierte Cmdlets funktionsfähig macht. Sie ermöglicht den Zugriff auf die Features von Cmdlets.

PowerShell bindet die Parameter von Funktionen, die über das- `CmdletBinding` Attribut verfügen, auf dieselbe Weise, wie die Parameter der kompilierten Cmdlets gebunden werden. Die `$PSCmdlet` Automatische Variable ist für Funktionen mit dem- `CmdletBinding` Attribut verfügbar, aber die `$Args` Variable ist nicht verfügbar.

In Funktionen, die über das- `CmdletBinding` Attribut verfügen, führen unbekannte Parameter und Positions Argumente, die keine übereinstimmenden Positions Parameter aufweisen, zu einem Fehler bei der Parameter Bindung.

> [!NOTE]
> Kompilierte Cmdlets verwenden das erforderliche- `Cmdlet` Attribut, das dem `CmdletBinding` in diesem Thema beschriebenen-Attribut ähnelt.

## <a name="syntax"></a>Syntax

Das folgende Beispiel zeigt das Format einer Funktion, die alle optionalen Argumente des `CmdletBinding` Attributs angibt. Das folgende Beispiel zeigt eine kurze Beschreibung der einzelnen Argumente.

```powershell
{
    [CmdletBinding(ConfirmImpact=<String>,
    DefaultParameterSetName=<String>,
    HelpURI=<URI>,
    SupportsPaging=<Boolean>,
    SupportsShouldProcess=<Boolean>,
    PositionalBinding=<Boolean>)]

    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

## <a name="confirmimpact"></a>ConfirmImpact

Das **confirmimpact** -Argument gibt an, **wann die Aktion** der Funktion durch einen-aufrufungstyp bestätigt werden soll. **Der Aufrufe der Methode "** zugsmethode" zeigt nur dann eine Bestätigungsaufforderung an, wenn das " **confirmimpact** "-Argument größer oder gleich dem Wert der "Preference"- `$ConfirmPreference` Variablen ist. (Der Standardwert des Arguments ist " **Medium** ".) Geben Sie dieses Argument nur an, wenn das **supportsrechtdprocess** -Argument ebenfalls angegeben ist.

Weitere Informationen zu Bestätigungs Anforderungen finden Sie unter [Anfordern einer Bestätigung](/powershell/scripting/developer/cmdlet/requesting-confirmation).

## <a name="defaultparametersetname"></a>DefaultParameterSetName

Das **defaultparametersetname** -Argument gibt den Namen des Parameter Satzes an, den PowerShell verwenden soll, wenn er nicht ermitteln kann, welcher Parameter verwendet werden soll. Sie können dieses Problem vermeiden, indem Sie den Unique-Parameter jedes Parameters für einen obligatorischen Parameter festlegen.

## <a name="helpuri"></a>HelpURI

Das **HelpUri** -Argument gibt die Internetadresse der Online Version des Hilfe Themas an, das die Funktion beschreibt. Der Wert des **HelpUri** -Arguments muss mit "http" oder "https" beginnen.

Der **HelpUri** -Argument Wert wird für den Wert der **HelpUri** -Eigenschaft des **CommandInfo** -Objekts verwendet, das `Get-Command` für die Funktion zurückgibt.

Wenn jedoch Hilfedateien auf dem Computer installiert sind und der Wert des ersten Links im Abschnitt **relatedLinks** der Hilfedatei ein URI ist oder der Wert der ersten `.Link` Anweisung in der Kommentar basierten Hilfe ein URI ist, wird der URI in der Hilfedatei als Wert der **HelpUri** -Eigenschaft der Funktion verwendet.

Das `Get-Help` -Cmdlet verwendet den Wert der **HelpUri** -Eigenschaft, um die Online Version des Hilfe Themas der Funktion zu finden, wenn der **Online-** Parameter von `Get-Help` in einem Befehl angegeben wird.

## <a name="supportspaging"></a>Supportspaging

Das **supportspaging** -Argument fügt der Funktion die Parameter " **First** ", " **Skip** " und " **IncludeTotalCount** " hinzu. Diese Parameter ermöglichen es Benutzern, die Ausgabe eines sehr großen Resultsets auszuwählen. Dieses Argument wurde für Cmdlets und Funktionen entwickelt, die Daten aus großen Daten speichern zurückgeben, die die Datenauswahl unterstützen, z. b. eine SQL-Datenbank.

Dieses Argument wurde in Windows PowerShell 3,0 eingeführt.

- **First** : Ruft nur die ersten ' n '-Objekte ab.
- **Skip** : ignoriert die ersten ' n '-Objekte und ruft dann die übrigen Objekte ab.
- **Incluabtotalcount** : gibt die Anzahl der-Objekte im DataSet (eine ganze Zahl) an, gefolgt von den-Objekten. Wenn das Cmdlet die Gesamtanzahl nicht ermitteln kann, wird "unbekannte Gesamtanzahl" zurückgegeben.

PowerShell enthält **newtotalcount** , eine Hilfsmethode, die den zurück zugebende Gesamtzahl Wert abruft und eine Schätzung der Genauigkeit des Gesamtanzahl Werts enthält.

Die folgende Beispiel Funktion zeigt, wie Sie eine Unterstützung für die Paging-Parameter einer erweiterten Funktion hinzufügen.

```powershell
function Get-Numbers {
    [CmdletBinding(SupportsPaging = $true)]
    param()

    $FirstNumber = [Math]::Min($PSCmdlet.PagingParameters.Skip, 100)
    $LastNumber = [Math]::Min($PSCmdlet.PagingParameters.First +
      $FirstNumber - 1, 100)

    if ($PSCmdlet.PagingParameters.IncludeTotalCount) {
        $TotalCountAccuracy = 1.0
        $TotalCount = $PSCmdlet.PagingParameters.NewTotalCount(100,
          $TotalCountAccuracy)
        Write-Output $TotalCount
    }
    $FirstNumber .. $LastNumber | Write-Output
}
```

## <a name="supportsshouldprocess"></a>SupportsShouldProcess

Das **supportsschulter dprocess** -Argument fügt der Funktion die Parameter **Confirm** und **WhatIf** hinzu. Der **Confirm** -Parameter fordert den Benutzer auf, bevor er den Befehl für jedes Objekt in der Pipeline ausführt. Der Parameter **WhatIf** listet die Änderungen auf, die der Befehl durchführen würde, anstatt den Befehl zu ausführen.

## <a name="positionalbinding"></a>PositionalBinding

Das **positionalbinding** -Argument bestimmt, ob Parameter in der Funktion standardmäßig Positionswerte sind. Der Standardwert ist `$True`. Sie können das **positionalbinding** -Argument mit einem Wert von verwenden `$False` , um die Positions Bindung zu deaktivieren.

Das **positionalbinding** -Argument wird in Windows PowerShell 3,0 eingeführt.

Wenn Parameter Positionswerte sind, ist der Parameter Name optional.
PowerShell ordnet unbenannte Parameterwerte den Funktionsparametern entsprechend der Reihenfolge oder Position der unbenannten Parameterwerte im Funktionsbefehl zu.

Wenn Parameter nicht Positions fähig sind (Sie sind "named"), ist der Parameter Name (oder eine Abkürzung oder ein Alias des Namens) im Befehl erforderlich.

Wenn **positionalbinding** ist `$True` , sind Funktionsparameter standardmäßig Positions fähig. PowerShell weist den Parametern die Positionsnummer in der Reihenfolge zu, in der Sie in der Funktion deklariert werden.

Wenn **positionalbinding** ist `$False` , sind Funktionsparameter standardmäßig nicht Positions fähig. Wenn das **Positions** Argument des **Parameter** Attributs nicht für den Parameter deklariert ist, muss der Parameter Name (oder ein Alias oder eine Abkürzung) eingeschlossen werden, wenn der Parameter in einer Funktion verwendet wird.

Das **Positions** Argument des **Parameter** Attributs hat Vorrang vor dem Standardwert **positionalbinding** . Sie können das **Positions** Argument verwenden, um einen Positionswert für einen Parameter anzugeben. Weitere Informationen zum **Positions** Argument finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).

## <a name="notes"></a>Notizen

Das **supportstransactions** -Argument wird in erweiterten Funktionen nicht unterstützt.

## <a name="keywords"></a>Keywords

about_Functions_CmdletBinding_Attribute

## <a name="see-also"></a>Weitere Informationen:

[about_Functions](about_Functions.md)

[about_Functions_Advanced](about_Functions_Advanced.md)

[about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md)

[about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)

[about_Functions_OutputTypeAttribute](about_Functions_OutputTypeAttribute.md)
