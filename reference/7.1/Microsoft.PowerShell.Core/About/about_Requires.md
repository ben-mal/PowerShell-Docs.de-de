---
description: Verhindert, dass ein Skript ohne die erforderlichen Elemente ausgeführt wird.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Requires
ms.openlocfilehash: 5c4eb4e272f214ffe906fd1a3f1c127824183d4a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223943"
---
# <a name="about-requires"></a>Informationen zu voraus

## <a name="short-description"></a>Kurze Beschreibung
Verhindert, dass ein Skript ohne die erforderlichen Elemente ausgeführt wird.

## <a name="long-description"></a>Lange Beschreibung

Mit der `#Requires` -Anweisung wird verhindert, dass ein Skript ausgeführt wird, es sei denn, die PowerShell-Version, die Module (und die Version) oder die Snap-Ins (und die-Version) und die Editions Voraussetzungen Wenn die Voraussetzungen nicht erfüllt sind, führt PowerShell das Skript nicht aus.

### <a name="syntax"></a>Syntax

```
#Requires -Assembly { <Path to .dll> | <.NET assembly specification> }
#Requires -Version <N>[.<n>]
#Requires -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -Modules { <Module-Name> | <Hashtable> }
#Requires -PSEdition <PSEdition-Name>
#Requires -ShellId <ShellId> -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -RunAsAdministrator
```

Weitere Informationen zur Syntax finden Sie unter [scriptrequirequirements](/dotnet/api/system.management.automation.language.scriptrequirements).

### <a name="rules-for-use"></a>Verwendungs Regeln

Ein Skript kann mehr als eine `#Requires` Anweisung enthalten. Die- `#Requires` Anweisungen können in einer beliebigen Zeile in einem Skript angezeigt werden.

Durch das Platzieren einer `#Requires` Anweisung innerhalb einer Funktion wird der Gültigkeitsbereich nicht eingeschränkt. Alle `#Requires` -Anweisungen werden immer global angewendet und müssen erfüllt werden, bevor das Skript ausgeführt werden kann.

> [!WARNING]
> Obwohl eine- `#Requires` Anweisung in einer Zeile in einem Skript angezeigt werden kann, wirkt sich die Position in einem Skript nicht auf die Abfolge der Anwendung aus. Der globale Status, den die- `#Requires` Anweisung darstellt, muss vor der Skriptausführung erfüllt werden.

Beispiel:

```powershell
Get-Module AzureRM.Netcore | Remove-Module
#Requires -Modules AzureRM.Netcore
```

Möglicherweise denken Sie daran, dass der obige Code nicht ausgeführt werden sollte, da das erforderliche Modul vor der Anweisung entfernt wurde `#Requires` . Der Zustand muss jedoch `#Requires` erfüllt sein, damit das Skript überhaupt ausgeführt werden kann. Anschließend hat die erste Zeile des Skripts den erforderlichen Zustand ungültig.

### <a name="parameters"></a>Parameter

#### <a name="-assembly-assembly-path--net-assembly-specification"></a>-Assembly \<Assembly path> |\<.NET assembly specification>

Gibt den Pfad zur DLL-Datei der Assembly oder einen .NET-Assemblynamen an. Der **Assembly** -Parameter wurde in PowerShell 5,0 eingeführt. Weitere Informationen zu .NET-Assemblys [Assembly names](/dotnet/standard/assembly/names)finden Sie unter Assemblynamen.

Beispiel:

```
#Requires -Assembly path\to\foo.dll
```

```
#Requires -Assembly "System.Management.Automation, Version=3.0.0.0,
  Culture=neutral, PublicKeyToken=31bf3856ad364e35"
```

#### <a name="-version-nn"></a>-Version \<N\> [. \<n\> ]

Gibt die mindestens erforderliche Version von PowerShell an, die für das Skript erforderlich ist. Geben Sie eine Hauptversionsnummer und optional eine neben Versionsnummer ein.

Beispiel:

```powershell
#Requires -Version 6.0
```

#### <a name="-pssnapin-pssnapin-name--version-nn"></a>-PSSnapIn \<PSSnapin-Name\> [-Version \<N\> [. \<n\> ]]

Gibt ein PowerShell-Snap-in an, das für das Skript erforderlich ist. Geben Sie den Snap-in-Namen und eine optionale Versionsnummer ein.

Beispiel:

```powershell
#Requires -PSSnapin DiskSnapin -Version 1.2
```

#### <a name="-modules-module-name--hashtable"></a>-Module \<Module-Name\> |\<Hashtable\>

Gibt die PowerShell-Module an, die das Skript erfordert. Geben Sie den Modulnamen und eine optionale Versionsnummer ein.

Wenn die erforderlichen Module nicht in der aktuellen Sitzung sind, importiert PowerShell Sie.
Wenn die Module nicht importiert werden können, löst PowerShell einen Fehler mit Abbruch aus.

Geben Sie für jedes Modul den Modulnamen ( \<String\> ) oder eine Hash Tabelle ein. Der Wert kann eine Kombination aus Zeichen folgen und Hash Tabellen sein. Die Hash Tabelle verfügt über die folgenden Schlüssel.

- `ModuleName` - **Erforderlich** Gibt den Namen des Moduls an.
- `GUID` - **Optional** Gibt die GUID des Moduls an.
- Es ist auch **erforderlich** , einen der drei folgenden Schlüssel anzugeben. Diese Schlüssel können nicht gleichzeitig verwendet werden.
  - `ModuleVersion` : Gibt eine zulässige Mindestversion des Moduls an.
  - `RequiredVersion` : Gibt eine exakte, erforderliche Version des Moduls an.
  - `MaximumVersion` : Gibt die maximal zulässige Version des Moduls an.

> [!NOTE]
> `RequiredVersion` wurde in Windows PowerShell 5,0 hinzugefügt.
> `MaximumVersion` wurde in Windows PowerShell 5,1 hinzugefügt.

Beispiel:

Erfordert, dass `AzureRM.Netcore` (Version `0.12.0` oder höher) installiert ist.

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; ModuleVersion="0.12.0" }
```

Erfordert, dass `AzureRM.Netcore` ( **nur** Version `0.12.0` ) installiert ist.

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12.0" }
```

Erfordert, dass `AzureRM.Netcore` (Version `0.12.0` oder weniger) installiert ist.

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; MaximumVersion="0.12.0" }
```

Erfordert, dass eine beliebige Version von `AzureRM.Netcore` und `PowerShellGet` installiert ist.

```powershell
#Requires -Modules AzureRM.Netcore, PowerShellGet
```

Wenn Sie den `RequiredVersion` Schlüssel verwenden, stellen Sie sicher, dass die Versions Zeichenfolge exakt der benötigten Versions Zeichenfolge entspricht

```powershell
Get-Module AzureRM.Netcore -ListAvailable
```

```Output
    Directory: /home/azureuser/.local/share/powershell/Modules

ModuleType Version Name            PSEdition ExportedCommands
---------- ------- ----            --------- ----------------
Script     0.12.0  AzureRM.Netcore Core
```

Das folgende Beispiel schlägt fehl, da **0,12** nicht exakt mit **0.12.0** übereinstimmt.

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12" }
```

#### <a name="-psedition-psedition-name"></a>-P* dition \<PSEdition-Name\>

Gibt eine PowerShell-Edition an, die für das Skript erforderlich ist. Gültige Werte sind **Core** für PowerShell Core und **Desktop** für Windows PowerShell.

Beispiel:

```powershell
#Requires -PSEdition Core
```

#### <a name="-shellid"></a>-Shellid

Gibt die Shell an, die für das Skript erforderlich ist. Geben Sie die Shell-ID ein. Wenn Sie den **shellid-** Parameter verwenden, müssen Sie auch den **PSSnapIn** -Parameter einschließen.
Sie können die aktuelle **shellid** ermitteln, indem Sie die `$ShellId` Automatische Variable Abfragen.

Beispiel:

```powershell
#Requires -ShellId MyLocalShell -PSSnapin Microsoft.PowerShell.Core
```

> [!NOTE]
> Dieser Parameter ist für die Verwendung in Mini Shells vorgesehen, die veraltet sind.

#### <a name="-runasadministrator"></a>-Runasadministrator

Wenn dieser Switch-Parameter der-Anweisung hinzugefügt wird `#Requires` , gibt er an, dass die PowerShell-Sitzung, in der das Skript ausgeführt wird, mit erhöhten Benutzerrechten gestartet werden muss. Der Parameter **runasadministrator** wird bei einem nicht-Windows-Betriebssystem ignoriert. Der **runasadministrator** -Parameter wurde in PowerShell 4,0 eingeführt.

Beispiel:

```powershell
#Requires -RunAsAdministrator
```

### <a name="examples"></a>Beispiele

Das folgende Skript verfügt über zwei- `#Requires` Anweisungen. Wenn die in beiden Anweisungen angegebenen Anforderungen nicht erfüllt sind, wird das Skript nicht ausgeführt. Jede `#Requires` Anweisung muss das erste Element in einer Zeile sein:

```powershell
#Requires -Modules AzureRM.Netcore
#Requires -Version 6.0
Param
(
    [parameter(Mandatory=$true)]
    [String[]]
    $Path
)
...
```

## <a name="see-also"></a>Weitere Informationen:

[about_Automatic_Variables](about_Automatic_Variables.md)

[about_Language_Keywords](about_Language_Keywords.md)

