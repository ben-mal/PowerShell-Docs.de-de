---
description: Beschreibt die Windows PowerShell-Kompatibilitäts Funktionalität für PowerShell 7.
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_Compatibility
ms.openlocfilehash: 777dab1cce4329958337a7c0857b0d712b4387a9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222380"
---
# <a name="about-windows-powershell-compatibility"></a>Informationen zur Windows PowerShell-Kompatibilität

## <a name="short-description"></a>KURZE BESCHREIBUNG

Beschreibt die Windows PowerShell-Kompatibilitäts Funktionalität für PowerShell 7.

## <a name="long-description"></a>LANGE BESCHREIBUNG

Wenn das Modul Manifest nicht anzeigt, dass das Modul mit PowerShell Core kompatibel ist, werden die Module im `%windir%\system32\WindowsPowerShell\v1.0\Modules` Ordner in Windows PowerShell 5,1 Process by Windows PowerShell Compatibility Feature geladen.

### <a name="using-the-compatibility-feature"></a>Verwenden des Kompatibilitäts Features

Wenn das erste Modul mithilfe der Windows PowerShell-Kompatibilitäts Funktion importiert wird, erstellt PowerShell eine Remote Sitzung mit dem Namen `WinPSCompatSession` , die in einem Windows PowerShell 5,1-Hintergrundprozess ausgeführt wird. Dieser Prozess wird erstellt, wenn die Kompatibilitäts Funktion das erste Modul importiert. Der Prozess wird geschlossen, wenn das letzte Modul entfernt wird (mithilfe von `Remove-Module` ) oder wenn der PowerShell-Prozess beendet wird.

Die in der Sitzung geladenen Module `WinPSCompatSession` werden über implizites Remoting verwendet und in der aktuellen PowerShell-Sitzung reflektiert. Dies ist die gleiche Transportmethode, die für PowerShell-Aufträge verwendet wird.

Wenn ein Modul in die Sitzung importiert wird `WinPSCompatSession` , generiert implizites Remoting ein Proxy Modul im Verzeichnis des Benutzers `$env:Temp` und importiert dieses Proxy Modul in die aktuelle PowerShell-Sitzung. Dadurch kann PowerShell erkennen, dass das Modul mithilfe der Windows PowerShell-Kompatibilitäts Funktion geladen wurde.

Nachdem die Sitzung erstellt wurde, kann Sie für Vorgänge verwendet werden, die für deserialisierte Objekte nicht ordnungsgemäß funktionieren. Die gesamte Pipeline wird in Windows PowerShell ausgeführt, und nur das endgültige Ergebnis wird zurückgegeben. Beispiel:

```powershell
$s = Get-PSSession -Name WinPSCompatSession
Invoke-Command -Session $s -ScriptBlock {
  "Running in Windows PowerShell version $($PSVersionTable.PSVersion)"
}
```

Die Kompatibilitäts Funktion kann auf zwei Arten aufgerufen werden:

- Explizites Importieren eines Moduls mit dem **usewindowspowershell** -Parameter

   ```powershell
   Import-Module -Name ScheduledTasks -UseWindowsPowerShell
   ```

- Implizites Importieren eines Windows PowerShell-Moduls nach Modulname,-Pfad oder-Authentifizierung über die Befehls Ermittlung.

   ```powershell
   Import-Module -Name ServerManager
   Get-AppLockerPolicy -Local
   ```

   Wenn das AppLocker-Modul nicht bereits geladen ist, wird es bei der Durchführung von authentifidiert  `Get-AppLockerPolicy` .

Windows PowerShell-Kompatibilität blockiert das Laden von Modulen, die in der- `WindowsPowerShellCompatibilityModuleDenyList` Einstellung in der PowerShell-Konfigurationsdatei aufgeführt sind.

Der Standardwert dieser Einstellung lautet:

```json
"WindowsPowerShellCompatibilityModuleDenyList":  [
   "PSScheduledJob","BestPractices","UpdateServices"
]
```

### <a name="managing-implicit-module-loading"></a>Verwalten des impliziten Ladevorgangs von Modulen

Verwenden Sie die `DisableImplicitWinCompat` Einstellung in einer PowerShell-Konfigurationsdatei, um implizites Import Verhalten des Windows PowerShell-Kompatibilitäts Features zu deaktivieren. Diese Einstellung kann der Datei hinzugefügt werden `powershell.config.json` . Weitere Informationen finden Sie unter [about_powershell_config](about_powershell_config.md).

In diesem Beispiel wird gezeigt, wie eine Konfigurationsdatei erstellt wird, die das implizite Modul Lade Feature der Windows PowerShell-Kompatibilität deaktiviert.

```powershell
$ConfigPath = "$PSHOME\DisableWinCompat.powershell.config.json"
$ConfigJSON = ConvertTo-Json -InputObject @{
  "DisableImplicitWinCompat" = $true
  "Microsoft.PowerShell:ExecutionPolicy" = "RemoteSigned"
}
$ConfigJSON | Out-File -Force $ConfigPath
pwsh -settingsFile $ConfigPath
```

Weitere Informationen zur Modul Kompatibilität finden Sie in der [PowerShell 7-Modul Kompatibilitäts](https://aka.ms/PSModuleCompat) Liste.

### <a name="managing-cmdlet-clobbering"></a>Verwalten der Cmdlet-schreiben

Das Windows PowerShell-Kompatibilitäts Feature verwendet implizites Remoting zum Laden von Modulen im Kompatibilitätsmodus. Das Ergebnis ist, dass Befehle, die vom Modul exportiert werden, Vorrang vor Befehlen desselben Namens in der aktuellen PowerShell 7-Sitzung haben. In der PowerShell-7.0.0-Version umfasste dies die Kernmodule, die mit PowerShell ausgeliefert werden.

In PowerShell 7,1 wurde das Verhalten so geändert, dass die folgenden PowerShell-Kernmodule nicht gemarshallt werden:

- Microsoft. PowerShell. ConsoleHost
- Microsoft.PowerShell.Diagnostics
- Microsoft.PowerShell.Host
- Microsoft.PowerShell.Management
- Microsoft.PowerShell.Security
- Microsoft.PowerShell.Utility
- Microsoft.WSMan.Management

PowerShell 7,1 hat außerdem die Möglichkeit zum Auflisten zusätzlicher Module hinzugefügt, die nicht durch den Kompatibilitätsmodus verdeckt werden sollten.

Sie können die `WindowsPowerShellCompatibilityNoClobberModuleList` Einstellung der PowerShell-Konfigurationsdatei hinzufügen. Der Wert dieser Einstellung ist eine durch Trennzeichen getrennte Liste von Modulnamen. Der Standardwert dieser Einstellung lautet:

```json
"WindowsPowerShellCompatibilityNoClobberModuleList": [ ]
```

## <a name="limitations"></a>Einschränkungen

Windows PowerShell-Kompatibilitäts Funktion:

1. Funktioniert nur lokal auf Windows-Computern
1. Erfordert Windows PowerShell 5,1
1. Arbeitet mit serialisierten Cmdlet-Parametern und Rückgabe Werten, nicht mit Live-Objekten.
1. Alle Module, die in die Windows PowerShell-Remoting-Sitzung importiert werden, verwenden denselben Runspace.

## <a name="keywords"></a>Keywords

about_Windows_PowerShell_Compatibility

## <a name="see-also"></a>Weitere Informationen:

[about_Modules](about_Modules.md)

[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)
