---
description: Beschreibt die Verwendung von Verteilung zum Übergeben von Parametern an Befehle in PowerShell.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_splatting?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Splatting
ms.openlocfilehash: a64cbbe5edd40bf4fc7f9b7347421988d225e666
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221983"
---
# <a name="about-splatting"></a>Informationen über splatting

## <a name="short-description"></a>Kurze Beschreibung

Beschreibt die Verwendung von Verteilung zum Übergeben von Parametern an Befehle in PowerShell.

## <a name="long-description"></a>Lange Beschreibung

Splatting ist eine Methode, eine Auflistung von Parameterwerten als Einheit an einen Befehl zu übergeben. PowerShell ordnet jedem Wert in der Auflistung einen Befehlsparameter zu. Splatted-Parameterwerte werden in benannten Verteilung-Variablen gespeichert, die wie Standardvariablen aussehen, aber mit einem at-Symbol ( `@` ) anstelle eines Dollar Zeichens ( `$` ) beginnen. Das at-Symbol weist PowerShell an, dass Sie eine Auflistung von Werten anstelle eines einzelnen Werts übergeben.

Splatting führt dazu, dass Ihre Befehle kürzer und leichter lesbar sind. Sie können die Verteilung-Werte in verschiedenen Befehls aufrufen wieder verwenden und Verteilung verwenden, um Parameterwerte aus der `$PSBoundParameters` automatischen Variablen an andere Skripts und Funktionen zu übergeben.

Ab Windows PowerShell 3,0 können Sie auch Verteilung verwenden, um alle Parameter eines Befehls darzustellen.

## <a name="syntax"></a>Syntax

```
<CommandName> <optional parameters> @<HashTable> <optional parameters>
<CommandName> <optional parameters> @<Array> <optional parameters>
```

Zum Bereitstellen von Parameterwerten für Positions Parameter, bei denen keine Parameternamen erforderlich sind, verwenden Sie die Array Syntax. Um Parameter Name-Wert-Paare anzugeben, verwenden Sie die Hash Tabellen Syntax. Der splatted-Wert kann an beliebiger Stelle in der Parameterliste angezeigt werden.

Wenn Sie splatting verwenden, müssen Sie keine Hash Tabelle oder ein Array verwenden, um alle Parameter zu übergeben. Sie können einige Parameter mithilfe von Verteilung übergeben und andere über die Position oder den Parameternamen übergeben. Außerdem können Sie mehrere Objekte in einem einzelnen Befehl splat, sodass Sie nicht mehr als einen Wert für jeden Parameter übergeben.

Ab PowerShell 7,1 können Sie einen splatted-Parameter überschreiben, indem Sie einen Parameter explizit in einem Befehl definieren.

## <a name="splatting-with-hash-tables"></a>Splatting mit Hash Tabellen

Verwenden Sie eine Hash Tabelle, um Parameter Name-Wert-Paare zu entfernen. Sie können dieses Format für alle Parametertypen verwenden, einschließlich Positions-und switchparametern.
Positions Parameter müssen anhand des Namens zugewiesen werden.

In den folgenden Beispielen werden zwei `Copy-Item` Befehle verglichen, mit denen die Test.txt Datei in die Test2.txt Datei im gleichen Verzeichnis kopiert wird.

Im ersten Beispiel wird das herkömmliche Format verwendet, in dem Parameternamen enthalten sind.

```powershell
Copy-Item -Path "test.txt" -Destination "test2.txt" -WhatIf
```

Im zweiten Beispiel wird Hash Tabellen-splatting verwendet. Der erste Befehl erstellt eine Hash Tabelle mit Parameter Name-und Parameter/Wert-Paaren und speichert Sie in der `$HashArguments` Variablen. Der zweite Befehl verwendet die- `$HashArguments` Variable in einem Befehl mit splatting. Das at-Symbol ( `@HashArguments` ) ersetzt das Dollarzeichen ( `$HashArguments` ) im Befehl.

Um einen Wert für den Parameter **WhatIf** Switch anzugeben, verwenden Sie `$True` oder `$False` .

```powershell
$HashArguments = @{
  Path = "test.txt"
  Destination = "test2.txt"
  WhatIf = $true
}
Copy-Item @HashArguments
```

> [!NOTE]
> Im ersten Befehl gibt das at-Symbol ( `@` ) eine Hash Tabelle und keinen splatted-Wert an. Die Syntax für Hash Tabellen in PowerShell lautet wie folgt: `@{<name>=<value>; <name>=<value>; ...}`

## <a name="splatting-with-arrays"></a>Splatting mit Arrays

Verwenden Sie ein Array, um Werte für Positions Parameter festzulegen, für die keine Parameternamen erforderlich sind. Die Werte müssen sich in der Reihenfolge der Positionsnummern im Array befinden.

In den folgenden Beispielen werden zwei `Copy-Item` Befehle verglichen, mit denen die Test.txt Datei in die Test2.txt Datei im gleichen Verzeichnis kopiert wird.

Im ersten Beispiel wird das herkömmliche Format verwendet, in dem Parameternamen ausgelassen werden. Die Parameterwerte werden im Befehl in der Positions Reihenfolge angezeigt.

```powershell
Copy-Item "test.txt" "test2.txt" -WhatIf
```

Im zweiten Beispiel wird das Array-splatting verwendet. Der erste Befehl erstellt ein Array der Parameterwerte und speichert es in der `$ArrayArguments` Variablen. Die Werte befinden sich in der Positions Reihenfolge im Array. Der zweite Befehl verwendet die- `$ArrayArguments` Variable in einem Befehl in splatting. Das at-Symbol ( `@ArrayArguments` ) ersetzt das Dollarzeichen ( `$ArrayArguments` ) im Befehl.

```powershell
$ArrayArguments = "test.txt", "test2.txt"
Copy-Item @ArrayArguments -WhatIf
```

### <a name="using-the-argumentlist-parameter"></a>Verwenden des Argument list-Parameters

Mehrere Cmdlets verfügen über einen Argument **List** -Parameter, der verwendet wird, um Parameterwerte an einen Skriptblock zu übergeben, der vom Cmdlet ausgeführt wird. Der Argument **List** -Parameter nimmt ein Array von Werten an, die an den Skriptblock übergeben werden. PowerShell verwendet in der Tat die Array-Verteilung, um die Werte an die Parameter des Skript Blocks zu binden. Wenn Sie bei Verwendung von Argument **List** ein Array als einzelnes Objekt übergeben müssen, das an einen einzelnen Parameter gebunden ist, müssen Sie das Array als einziges Element eines anderen Arrays einschließen.

Das folgende Beispiel enthält einen Skriptblock, der einen einzelnen Parameter annimmt, bei dem es sich um ein Array von Zeichen folgen handelt.

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
  } -ArgumentList $array
```
<!--
01234567890123456789012345678901234567890123456789012345678901234567890123456789
-->
In diesem Beispiel wird nur das erste Element in `$array` an den Skriptblock übermittelt.

```Output
Hello
```

```powershell
$array = 'Hello', 'World!'
Invoke-Command -ScriptBlock {
  param([string[]]$words) $words -join ' '
} -ArgumentList (,$array)
```

In diesem Beispiel `$array` ist in ein Array integriert, sodass das gesamte Array als einzelnes Objekt an den Skriptblock übermittelt wird.

```Output
Hello World!
```

## <a name="examples"></a>Beispiele

### <a name="example-1-reuse-splatted-parameters-in-different-commands"></a>Beispiel 1: wieder verwenden von splatted-Parametern in anderen Befehlen

Dieses Beispiel zeigt, wie Sie splatted-Werte in verschiedenen Befehlen wieder verwenden. Mit den Befehlen in diesem Beispiel wird das- `Write-Host` Cmdlet zum Schreiben von Nachrichten in die Konsole des Host Programms verwendet. Dabei werden die Vordergrund-und Hintergrundfarben verwendet.

Um die Farben aller Befehle zu ändern, ändern Sie einfach den Wert der `$Colors` Variablen.

Der erste Befehl erstellt eine Hash Tabelle mit Parameternamen und-Werten und speichert die Hash Tabelle in der `$Colors` Variablen.

```powershell
$Colors = @{ForegroundColor = "black"; BackgroundColor = "white"}
```

Der zweite und der dritte Befehl verwenden die- `$Colors` Variable für Verteilung in einem- `Write-Host` Befehl. Um das zu verwenden `$Colors variable` , ersetzen Sie das Dollarzeichen ( `$Colors` ) durch ein-Symbol ( `@Colors` ).

```powershell
#Write a message with the colors in $Colors
Write-Host "This is a test." @Colors

#Write second message with same colors. The position of splatted
#hash table does not matter.
Write-Host @Colors "This is another test."
```

### <a name="example-2-forward-parameters-using-psboundparameters"></a>Beispiel 2: Weiterleiten von Parametern mithilfe von $PSBoundParameters

Dieses Beispiel zeigt, wie Sie Ihre Parameter mithilfe von Verteilung und der automatischen Variablen an andere Befehle weiterleiten können `$PSBoundParameters` .

Die `$PSBoundParameters` Automatische Variable ist ein Dictionary-Objekt (System. Collections. Generic. Dictionary), das alle Parameternamen und-Werte enthält, die beim Ausführen eines Skripts oder einer Funktion verwendet werden.

Im folgenden Beispiel verwenden wir die- `$PSBoundParameters` Variable, um die Parameterwerte weiterzuleiten, die an ein Skript oder eine Funktion von `Test2` der Funktion an die Funktion weitergegeben werden `Test1` . Beide Aufrufe der- `Test1` Funktion von `Test2` verwenden splatting.

```powershell
function Test1
{
    param($a, $b, $c)

    $a
    $b
    $c
}

function Test2
{
    param($a, $b, $c)

    #Call the Test1 function with $a, $b, and $c.
    Test1 @PsBoundParameters

    #Call the Test1 function with $b and $c, but not with $a
    $LimitedParameters = $PSBoundParameters
    $LimitedParameters.Remove("a") | Out-Null
    Test1 @LimitedParameters
}
```

```Output
Test2 -a 1 -b 2 -c 3
1
2
3
2
3
```

### <a name="example-3-override-splatted-parameters-with-explicitly-defined-parameters"></a>Beispiel 3: Überschreiben von splatted-Parametern mit explizit definierten Parametern

Dieses Beispiel zeigt, wie Sie einen splatted-Parameter mithilfe explizit definierter Parameter überschreiben. Dies ist hilfreich, wenn Sie keine neue Hash Tabelle erstellen oder einen Wert in der Hash Tabelle ändern möchten, den Sie für die Verwendung von splat verwenden.

`$commonParams`In der Variablen werden die Parameter zum Erstellen virtueller Maschinen am `East US` Speicherort gespeichert. Die `$allVms` Variable ist eine Liste der zu erstellenden virtuellen Computer. Wir durchlaufen die Liste und verwenden `$commonParams` , um die Parameter zu erstellen, um die einzelnen virtuellen Computer zu erstellen. Wir möchten jedoch `myVM2` in einer anderen Region als die anderen virtuellen Computer erstellt werden. Anstatt die `$commonParams` Hash Tabelle anzupassen, können Sie den **Location** -Parameter in explizit definieren, `New-AzVm` um den Wert des `Location` Schlüssels in zu ersetzen `$commonParams` .

```powershell
$commonParams = @{
    ResourceGroupName = "myResourceGroup"
    Location = "East US"
    VirtualNetworkName = "myVnet"
    SubnetName = "mySubnet"
    SecurityGroupName = "myNetworkSecurityGroup"
    PublicIpAddressName = "myPublicIpAddress"
}

$allVms = @('myVM1','myVM2','myVM3',)

foreach ($vm in $allVms)
{
    if ($vm -eq 'myVM2')
    {
        New-AzVm @commonParams -Name $vm -Location "West US"
    }
    else
    {
        New-AzVm @commonParams -Name $vm
    }
}
```

## <a name="splatting-command-parameters"></a>Splatting-Befehlsparameter

Mithilfe von Verteilung können Sie die Parameter eines Befehls darstellen. Diese Technik ist hilfreich, wenn Sie eine Proxy Funktion erstellen, d. h. eine Funktion, die einen anderen Befehl aufruft. Diese Funktion wird in Windows PowerShell 3,0 eingeführt.

Um die Parameter eines Befehls zu übersetzen, verwenden `@Args` Sie, um die Befehlsparameter darzustellen. Diese Technik ist einfacher als das Auflisten von Befehlsparametern und funktioniert ohne Revision, auch wenn die Parameter des aufgerufenen Befehls geändert werden.

Die Funktion verwendet die `$Args` Automatische Variable, die alle nicht zugewiesenen Parameterwerte enthält.

Die folgende Funktion ruft z `Get-Process` . b. das Cmdlet auf. In dieser Funktion `@Args` stellt alle Parameter des `Get-Process` Cmdlets dar.

```powershell
function Get-MyProcess { Get-Process @Args }
```

Wenn Sie die `Get-MyProcess` -Funktion verwenden, werden alle nicht zugewiesenen Parameter und Parameterwerte an übergeben `@Args` , wie in den folgenden Befehlen gezeigt.

```powershell
Get-MyProcess -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    463      46   225484     237196   719    15.86   3228 powershell
```

```powershell
Get-MyProcess -Name PowerShell_Ise -FileVersionInfo
```

```Output
ProductVersion   FileVersion      FileName
--------------   -----------      --------
6.2.9200.16384   6.2.9200.1638... C:\Windows\system32\WindowsPowerShell\...
```

Sie können `@Args` in einer Funktion verwenden, die explizit deklarierte Parameter aufweist. Sie können Sie mehrmals in einer Funktion verwenden, aber alle Parameter, die Sie eingeben, werden an alle Instanzen von `@Args` , wie im folgenden Beispiel gezeigt, weitergegeben.

```powershell
function Get-MyCommand
{
    Param ([switch]$P, [switch]$C)
    if ($P) { Get-Process @Args }
    if ($C) { Get-Command @Args }
}

Get-MyCommand -P -C -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
408      28    75568      83176   620     1.33   1692 powershell

Path               : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Extension          : .exe
Definition         : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.e
Visibility         : Public
OutputType         : {System.String}
Name               : powershell.exe
CommandType        : Application
ModuleName         :
Module             :
RemotingCapability : PowerShell
Parameters         :
ParameterSets      :
HelpUri            :
FileVersionInfo    : File:             C:\Windows\System32\WindowsPowerShell
                     \v1.0\powershell.exe
                     InternalName:     POWERSHELL
                     OriginalFilename: PowerShell.EXE.MUI
                     FileVersion:      10.0.14393.0 (rs1_release.160715-1616
                     FileDescription:  Windows PowerShell
                     Product:          Microsoft Windows Operating System
                     ProductVersion:   10.0.14393.0
                     Debug:            False
                     Patched:          False
                     PreRelease:       False
                     PrivateBuild:     False
                     SpecialBuild:     False
                     Language:         English (United States)
```

## <a name="notes"></a>Notizen

Wenn Sie eine Funktion in einer erweiterten Funktion mithilfe der **cmdletbinding** -oder **Parameter** Attribute erstellen, ist die `$args` Automatische Variable nicht mehr in der Funktion verfügbar. Erweiterte Funktionen erfordern eine explizite Parameterdefinition.

PowerShell DSC (DSC) wurde nicht für die Verwendung von splatting konzipiert.
Sie können Verteilung nicht verwenden, um Werte an eine DSC-Ressource zu übergeben. Weitere Informationen finden Sie im Artikel über das [Pseudo splatting für DSC-Ressourcen](https://gaelcolas.com/2017/11/05/pseudo-splatting-dsc-resources/)im Artikel "Gael Colas".

## <a name="see-also"></a>Weitere Informationen:

[about_Arrays](about_Arrays.md)

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Hash_Tables](about_Hash_Tables.md)

[about_Parameters](about_Parameters.md)
