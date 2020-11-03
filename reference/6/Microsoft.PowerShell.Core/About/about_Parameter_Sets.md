---
description: Beschreibt, wie Parametersätze in erweiterten Funktionen definiert und verwendet werden.
title: about_Parameter_Sets
ms.date: 02/11/2020
ms.openlocfilehash: e4cfbc13f981bcc93c8a0a3c799851e83df7746c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221439"
---
# <a name="about-parameter-sets"></a>Informationen zu Parametersätzen

## <a name="short-description"></a>KURZE BESCHREIBUNG
Beschreibt, wie Parametersätze in erweiterten Funktionen definiert und verwendet werden.

## <a name="long-description"></a>LANGE BESCHREIBUNG

PowerShell verwendet Parametersätze, damit Sie eine einzelne Funktion schreiben können, die verschiedene Aktionen für verschiedene Szenarien ausführen kann. Parametersätze ermöglichen es Ihnen, dem Benutzer verschiedene Parameter verfügbar zu machen. Und, um basierend auf den vom Benutzer angegebenen Parametern unterschiedliche Informationen zurückzugeben.

## <a name="parameter-set-requirements"></a>Parameter Satz Anforderungen

Die folgenden Anforderungen gelten für alle Parametersätze.

- Jeder Parametersatz muss mindestens einen eindeutigen Parameter aufweisen. Wenn möglich, machen Sie diesen Parameter zu einem obligatorischen Parameter.

- Ein Parametersatz, der mehrere Positions Parameter enthält, muss eindeutige Positionen für jeden Parameter definieren. Es können nicht zwei Positions Parameter dieselbe Position angeben.

- Nur ein Parameter in einer Menge kann das- `ValueFromPipeline` Schlüsselwort mit dem Wert deklarieren `true` . Mehrere Parameter können das `ValueFromPipelineByPropertyName` Schlüsselwort mit dem Wert definieren `true` .

- Wenn für einen Parameter kein Parametersatz angegeben ist, gehört der Parameter zu allen Parametersätzen.

> [!NOTE]
> Es gibt ein Limit von 32-Parametersätzen.

## <a name="default-parameter-sets"></a>Standardparameter Sätze

Wenn mehrere Parametersätze definiert werden, gibt das- `DefaultParameterSetName` Schlüsselwort des **cmdletbinding** -Attributs den Standardparameter Satz an.
PowerShell verwendet den Standardparameter Satz, wenn der festgelegte Parameter nicht anhand der Informationen bestimmt werden kann, die für den Befehl verwendet werden. Weitere Informationen zum **cmdletbinding** -Attribut finden Sie unter [about_functions_cmdletbindingattribute](about_functions_cmdletbindingattribute.md).

## <a name="declaring-parameter-sets"></a>Deklarieren von Parametersätzen

Um einen Parametersatz zu erstellen, müssen Sie das- `ParameterSetName` Schlüsselwort des **Parameter** -Attributs für jeden Parameter im Parametersatz angeben. Fügen Sie für Parameter, die mehreren Parametersätzen angehören, ein **Parameter** Attribut für jeden Parametersatz hinzu.

Mit dem **Parameter** -Attribut können Sie den-Parameter für jeden Parametersatz anders definieren. Beispielsweise können Sie einen Parameter in einem Satz als obligatorisch definieren und optional in einem anderen. Jeder Parametersatz muss jedoch mindestens einen eindeutigen Parameter enthalten.

Parameter, denen kein Parametersatz Name zugewiesen ist, gehören zu allen Parametersätzen.

### <a name="example"></a>Beispiel

Die folgende Beispiel Funktion zählt die Anzahl von Zeilen, Zeichen und Wörtern in einer Textdatei. Mithilfe von Parametern können Sie angeben, welche Werte zurückgegeben werden sollen und welche Dateien Sie messen möchten. Vier Parametersätze sind definiert:

- Pfad
- Pathall
- LiteralPath
- Literalpathall

```powershell
function Measure-Lines {
    [CmdletBinding(DefaultParameterSetName = 'Path')]
    param (
        [Parameter(Mandatory = $true,
            ParameterSetName = 'Path',
            HelpMessage = 'Enter one or more filenames',
            Position = 0)]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'PathAll',
            Position = 0)]
        [string[]]$Path,

        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [Parameter(Mandatory = $true,
            ParameterSetName = 'LiteralPath',
            HelpMessage = 'Enter a single filename',
            ValueFromPipeline = $true)]
        [string]$LiteralPath,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Lines,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Words,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'LiteralPath')]
        [switch]$Characters,

        [Parameter(Mandatory = $true, ParameterSetName = 'PathAll')]
        [Parameter(Mandatory = $true, ParameterSetName = 'LiteralPathAll')]
        [switch]$All,

        [Parameter(ParameterSetName = 'Path')]
        [Parameter(ParameterSetName = 'PathAll')]
        [switch]$Recurse
    )

    begin {
        if ($All) {
            $Lines = $Words = $Characters = $true
        }
        elseif (($Words -eq $false) -and ($Characters -eq $false)) {
            $Lines = $true
        }

        if ($Path) {
            $Files = Get-ChildItem -Path $Path -Recurse:$Recurse
        }
        else {
            $Files = Get-ChildItem -LiteralPath $LiteralPath
        }
    }
    process {
        foreach ($file in $Files) {
            $result = [ordered]@{ }
            $result.Add('File', $file.fullname)

            $content = Get-Content -LiteralPath $file.fullname

            if ($Lines) { $result.Add('Lines', $content.Length) }

            if ($Words) {
                $wc = 0
                foreach ($line in $content) { $wc += $line.split(' ').Length }
                $result.Add('Words', $wc)
            }

            if ($Characters) {
                $cc = 0
                foreach ($line in $content) { $cc += $line.Length }
                $result.Add('Characters', $cc)
            }

            New-Object -TypeName psobject -Property $result
        }
    }
}
```

Jeder Parametersatz muss einen eindeutigen Parameter oder eine eindeutige Kombination von Parametern aufweisen. Der `Path` -Parameter und der- `PathAll` Parametersatz sind sehr ähnlich, aber der **all** -Parameter ist für den `PathAll` Parametersatz eindeutig. Dasselbe gilt für den `LiteralPath` -Parameter und den- `LiteralPathAll` Parametersatz. Obwohl sowohl der `PathAll` -Parameter als auch der- `LiteralPathAll` Parameter auf den **all** -Parameter festgelegt sind, unterscheiden sich die Parameter **path** und **literalpath** .

Verwenden `Get-Command -Syntax` zeigt die Syntax der einzelnen Parametersätze an. Der Name des Parameter Satzes wird jedoch nicht angezeigt. Im folgenden Beispiel wird gezeigt, welche Parameter in jedem Parametersatz verwendet werden können.

```powershell
(Get-Command Measure-Lines).ParameterSets |
  Select-Object -Property @{n='ParameterSetName';e={$_.name}},
    @{n='Parameters';e={$_.ToString()}}
```

```Output
ParameterSetName Parameters
---------------- ----------
Path             [-Path] <string[]> [-Lines] [-Words] [-Characters] [-Recurse] [<CommonParameters>]
PathAll          [-Path] <string[]> -All [-Recurse] [<CommonParameters>]
LiteralPath      -LiteralPath <string> [-Lines] [-Words] [-Characters] [<CommonParameters>]
LiteralPathAll   -LiteralPath <string> -All [<CommonParameters>]
```

### <a name="parameter-sets-in-action"></a>Parameter Sätze in Aktion

In diesem Beispiel verwenden wir den `PathAll` Parametersatz.

```powershell
Measure-Lines test* -All
```

```Output
File                       Lines Words Characters
----                       ----- ----- ----------
C:\temp\test\test.help.txt    31   562       2059
C:\temp\test\test.md          30  1527       3224
C:\temp\test\test.ps1          3     3         79
C:\temp\test\test[1].txt      31   562       2059
```
