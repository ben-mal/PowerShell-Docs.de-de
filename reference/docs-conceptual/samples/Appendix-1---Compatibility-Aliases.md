---
ms.date: 08/03/2020
keywords: powershell,cmdlet
title: Anhang 1 – Kompatibilitätsaliase
ms.openlocfilehash: e5bd170fea6b6109d2ef4fd58863d6cc8a0e3ae1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87758498"
---
# <a name="appendix-1---compatibility-aliases"></a>Anhang 1: Kompatibilitätsaliase

PowerShell verfügt über mehrere Aliase, die **UNIX**- und **cmd.exe**-Benutzern ermöglichen, vertraute Befehle zu verwenden.
Die Befehle, das zugehörige PowerShell-Cmdlet und der PowerShell-Alias sind in der folgenden Tabelle aufgeführt:

|            Befehl „cmd. exe“            | UNIX-Befehl | PowerShell-Cmdlet | PowerShell-Alias |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| **cd**, **chdir**                     | **cd**       | `Set-Location`    | `sl`             |
| **cls**                               | **Löschen**    | `Clear-Host`      | `cls`            |
| **copy**                              | **cp**       | `Copy-Item`       | `cpi`            |
| **del**, **erase**, **rd**, **rmdir** | **rm**       | `Remove-Item`     | `ri`             |
| **dir**                               | **ls**       | `Get-ChildItem`   | `gci`            |
| **echo**                              | **echo**     | `Write-Output`    | `write`          |
| **md**                                | **mkdir**    | `New-Item`        | `ni`             |
| **move**                              | **mv**       | `Move-Item`       | `mi`             |
| **popd**                              | **popd**     | `Pop-Location`    | `popd`           |
| **pushd**                             | **pushd**    | `Push-Location`   | `pushd`          |
| **ren**                               | **mv**       | `Rename-Item`     | `rni`            |
| **type**                              | **cat**      | `Get-Content`     | `gc`             |

Verwenden Sie das [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias)-Cmdlet, um die PowerShell-Aliase zu ermitteln. Um die Aliase eines Cmdlets anzuzeigen, verwenden Sie den **Definition**-Parameter, und geben Sie den Namen des Cmdlets an.
Verwenden Sie alternativ den **Name**-Parameter, um den Cmdlet-Namen eines Alias zu suchen.

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
