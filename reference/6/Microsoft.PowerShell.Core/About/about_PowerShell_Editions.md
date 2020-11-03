---
description: Verschiedene Editionen von PowerShell werden auf unterschiedlichen zugrunde liegenden Laufzeiten ausgeführt.
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_editions?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Editions
ms.openlocfilehash: 4649c1b47a69423eb2f11a119583f441191882dd
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221375"
---
# <a name="about-powershell-editions"></a>Informationen zu PowerShell-Editionen

## <a name="short-description"></a>Kurze Beschreibung
Verschiedene Editionen von PowerShell werden auf unterschiedlichen zugrunde liegenden Laufzeiten ausgeführt.

## <a name="long-description"></a>Lange Beschreibung

In PowerShell 5,1 gibt es mehrere _Editionen_ von PowerShell, die jeweils in einer anderen .NET-Laufzeit ausgeführt werden. Ab PowerShell 6,2 gibt es zwei Editionen von PowerShell:

- **Desktop** , der auf .NET Framework ausgeführt wird. PowerShell 4 und niedriger als auch PowerShell 5,1 in voll funktionsfähigen Windows-Editionen wie Windows Desktop, Windows Server, Windows Server Core und die meisten anderen Windows-Betriebssysteme sind Desktop Edition. Dies ist die Original-PowerShell-Edition.
- **Core** , das unter .net Core ausgeführt wird. PowerShell 6,0 und höher sowie PowerShell 5,1 auf einigen reduzierten Windows-Editionen wie Windows Nano Server und Windows IOT, wo .NET Framework nicht verfügbar ist.

Da die Edition von PowerShell Ihrer .NET-Laufzeit entspricht, ist Sie der primäre Indikator für die Kompatibilität von .NET-API und PowerShell-Modulen. einige .NET-APIs,-Typen oder-Methoden sind nicht in .net-Laufzeiten verfügbar. Dies wirkt sich auf PowerShell-Skripts und-Module aus, die von ihnen abhängen.

## <a name="the-psedition-automatic-variable"></a>Die `$PSEdition` Automatische Variable.

In PowerShell 5,1 und höher können Sie herausfinden, welche Edition Sie mit der `$PSEdition` automatischen Variablen ausführen:

```powershell
$PSEdition
```

```Output
Core
```

In PowerShell 4 und niedriger ist die Variable nicht vorhanden. `$PSEdition` NULL sollte als identisch mit dem Wert behandelt werden `Desktop` .

### <a name="edition-in-psversiontable"></a>Edition in `$PSVersionTable`

Die `$PSVersionTable` Automatische Variable enthält auch Editions Informationen in PowerShell 5,1 und höher:

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      6.2.0-rc.1
PSEdition                      Core           # <-- Edition information
GitCommitId                    6.2.0-rc.1
OS                             Microsoft Windows 10.0.18865
Platform                       Win32NT
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
WSManStackVersion              3.0
```

Das `PSEdition` Feld hat denselben Wert wie die `$PSEdition` Automatische Variable.

## <a name="the-compatiblepseditions-module-manifest-field"></a>Das `CompatiblePSEditions` Modul Manifest-Feld

PowerShell-Module können mithilfe des- `CompatiblePSEditions` Felds des Modul Manifests deklarieren, mit welchen PowerShell-Editionen Sie kompatibel sind.

Ein Modul Manifest deklariert beispielsweise die Kompatibilität mit den `Desktop` `Core` Editionen und von PowerShell:

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop', 'Core')
}
```

Ein Beispiel für ein Modul Manifest mit nur `Desktop` Kompatibilität:

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop')
}
```

Das Weglassen des `CompatiblePSEditions` Felds aus einem Modul Manifest hat denselben Effekt wie das Festlegen von `Desktop` , da Module, die vor der Einführung dieses Felds erstellt wurden, implizit für diese Edition geschrieben wurden.

Für Module, die nicht als Teil von Windows ausgeliefert werden (d. h. Module, die Sie im Katalog schreiben oder installieren), ist dieses Feld nur Informationszwecken. PowerShell ändert das Verhalten nicht auf der Grundlage des `CompatiblePSEditions` Felds, sondern macht es für das `PSModuleInfo` Objekt, das von zurückgegeben wird, `Get-Module` für Ihre eigene Logik verfügbar:

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion '5.1'
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

> [!NOTE]
> Das `CompatiblePSEditions` Modul Feld ist nur mit PowerShell 5,1 und höher kompatibel. Das Einschließen dieses Felds führt dazu, dass ein Modul mit PowerShell 4 und niedriger inkompatibel ist. Da das Feld rein informativ ist, kann es in späteren PowerShell-Versionen sicher weggelassen werden.

In PowerShell 6,1 `Get-Module -ListAvailable` hat der Formatierer des Formatierers aktualisiert, um die Editions Kompatibilität der einzelnen Module anzuzeigen:

```PowerShell
Get-Module -ListAvailable
```

```Output

    Directory: C:\Users\me\Documents\PowerShell\Modules

ModuleType Version    Name                   PSEdition ExportedCommands
---------- -------    ----                   --------- ----------------
Script     1.4.0      Az                     Core,Desk
Script     1.3.1      Az.Accounts            Core,Desk {Disable-AzDataCollection, Disable-AzContextAutosave, E...
Script     1.0.1      Az.Aks                 Core,Desk {Get-AzAks, New-AzAks, Remove-AzAks, Import-AzAksCreden...

...

Script     4.4.0      Pester                 Desk      {Describe, Context, It, Should...}
Script     1.18.0     PSScriptAnalyzer       Desk      {Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer, Invoke-...
Script     1.0.0      WindowsCompatibility   Core      {Initialize-WinSession, Add-WinFunction, Invoke-WinComm...

```

## <a name="edition-compatibility-for-modules-that-ship-as-part-of-windows"></a>Editions Kompatibilität für Module, die als Teil von Windows ausgeliefert werden

Bei Modulen, die Teil von Windows sind (oder als Teil einer Rolle oder eines Features installiert werden), wird das Feld von PowerShell 6,1 und höher `CompatiblePSEditions` anders behandelt. Solche Module befinden sich im Verzeichnis "Windows PowerShell-Systemmodule" ( `%windir%\System\WindowsPowerShell\v1.0\Modules` ).

Bei Modulen, die aus diesem Verzeichnis geladen oder darin enthalten sind, verwendet PowerShell 6,1 und höher das- `CompatiblePSEditions` Feld, um zu bestimmen, ob das Modul mit der aktuellen Sitzung kompatibel ist und sich entsprechend verhält.

Wenn `Import-Module` verwendet wird, wird ein Modul ohne `Core` in `CompatiblePSEditions` nicht importiert, und es wird ein Fehler angezeigt:

```powershell
Import-Module BitsTransfer
```

```Output
Import-Module : Module 'C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\BitsT
ransfer\BitsTransfer.psd1' does not support current PowerShell edition 'Core'.
Its supported editions are 'Desktop'. Use 'Import-Module -SkipEditionCheck' to i
gnore the compatibility of this module.
At line:1 char:1
+ Import-Module BitsTransfer
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : ResourceUnavailable: (C:\WINDOWS\system32\u2026r\BitsT
ransfer.psd1:String) [Import-Module], InvalidOperationException
+ FullyQualifiedErrorId : Modules_PSEditionNotSupported,Microsoft.PowerShell.Com
mands.ImportModuleCommand
```

Wenn `Get-Module -ListAvailable` verwendet wird, werden Module ohne `Core` in `CompatiblePSEditions` nicht angezeigt:

```powershell
Get-Module -ListAvailable BitsTransfer
```

```Output
# No output
```

In beiden Fällen kann der `-SkipEditionCheck` Switch-Parameter verwendet werden, um dieses Verhalten zu überschreiben:

```powershell
Get-Module -ListAvailable -SkipEditionCheck BitsTransfer
```

```Output
    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name             PSEdition ExportedCommands
---------- -------    ----             --------- ----------------
Manifest   2.0.0.0    BitsTransfer     Desk      {Add-BitsFile, Complete-BitsTransfer, Get-BitsTransfer,...
```

> [!WARNING]
> `Import-Module -SkipEditionCheck` scheint für ein Modul erfolgreich zu sein, aber die Verwendung dieses Moduls führt zu einem späteren Zeitpunkt das Risiko einer Inkompatibilität. während das Laden des Moduls anfänglich erfolgreich ist, kann ein Befehl später eine inkompatible API und einen Fehler auslösen.

## <a name="authoring-powershell-modules-for-edition-cross-compatibility"></a>Erstellen von PowerShell-Modulen für die Editions übergreifende Kompatibilität

Wenn Sie ein PowerShell-Modul schreiben, das sowohl `Desktop` als auch `Core` Editionen von PowerShell als Ziel hat, gibt es Dinge, die Sie tun können, um die übergreifende Kompatibilität sicherzustellen.

Die einzige echte Möglichkeit zum bestätigen und kontinuierlichen Validieren der Kompatibilität besteht darin, Tests für Ihr Skript oder Modul zu schreiben und Sie für alle Versionen und Editionen von PowerShell auszuführen, mit denen Sie Kompatibilität benötigen. Ein empfohlenes Test Framework hierfür ist [Pester][].

### <a name="powershell-script"></a>PowerShell-Skript

In der Sprache funktioniert PowerShell zwischen den Editionen. Dabei handelt es sich um die Cmdlets, Module und .NET-APIs, die von der Editions Kompatibilität betroffen sind.

Im Allgemeinen funktionieren Skripts, die in PowerShell 6,1 und höher funktionieren, mit Windows PowerShell 5,1, es gibt jedoch einige Ausnahmen.

Version 1.18.0 das [psscriptanalyzer][] -Modul verfügt über Regeln wie [psutarcompatiblecommands][] und [psutarcompatibletypes][] , die die möglicherweise nicht kompatible Verwendung von Befehlen und .NET-APIs in PowerShell-Skripts erkennen können.

### <a name="net-assemblies"></a>.NET-Assemblys

Wenn Sie ein binäres Modul oder ein Modul schreiben, das aus Quellcode generierte .NET-Assemblys (DLLs) enthält, sollten Sie eine Kompilierung für [.NET Standard][] und [PowerShell Standard][] zur Kompilierzeit-Kompatibilitäts Überprüfung von .net und PowerShell-API-Kompatibilität durchgeführt haben.

Obwohl diese Bibliotheken einige Kompatibilitäts Möglichkeiten zur Kompilierzeit überprüfen können, sind Sie nicht in der Lage, mögliche Verhaltensunterschiede zwischen den Editionen abzufangen.
Hierfür müssen Sie weiterhin Tests schreiben.

## <a name="see-also"></a>Weitere Informationen:

- [about_Automatic_Variables](about_Automatic_Variables.md)
- [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)
- [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)
- [Module mit kompatiblen PowerShell-Editionen](/powershell/scripting/gallery/concepts/module-psedition-support)

[Pester]: https://github.com/pester/Pester/wiki/Pester
[PSScriptAnalyzer]: https://github.com/PowerShell/PSScriptAnalyzer
[Psusetup compatiblecommands]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
[Psutarcompatibletypes]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell Standard]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
